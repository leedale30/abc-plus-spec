# ABC+ to MusicXML Conversion Exceptions

## 1. Introduction

This document documents all exceptions for elements that cannot be directly converted between ABC+ and MusicXML formats. The goal is to provide clear justification for each exception and ensure that users understand the limitations of the conversion process.

## 2. Exceptions by Category

### 2.1 Elements with No Direct Equivalent

#### 2.1.1 ABC+ Elements with No MusicXML Equivalent

| Element | Reason for Exception | Justification |
|---------|---------------------|---------------|
| `X: (reference number)` | Not present in MusicXML | MusicXML does not use reference numbers for tunes. This element is typically used for administrative purposes and does not affect the musical content. |
| `L: (unit note length)` | Not present in MusicXML | MusicXML calculates note lengths from divisions and duration values instead of using a unit note length. This can be calculated during conversion. |

#### 2.1.2 MusicXML Elements with No ABC+ Equivalent

| Element | Reason for Exception | Justification |
|---------|---------------------|---------------|
| Advanced layout elements | Not supported in ABC+ | ABC+ has limited layout control compared to MusicXML. While basic layout directives are supported, advanced layout elements like `<page-layout>`, `<system-layout>`, etc. are not directly supported. |
| Advanced notation elements | Not supported in ABC+ | ABC+ has limited support for advanced notation compared to MusicXML. While basic articulations and decorations are supported, some advanced notation elements may not be directly supported. |
| Some MIDI elements | Not directly supported in ABC+ | ABC+ has limited MIDI support compared to MusicXML. While basic MIDI mapping is supported through `I:percmap`, detailed MIDI control elements may not be directly supported. |

### 2.2 Elements with Partial Mapping

| Element | Limitations | Justification |
|---------|-------------|---------------|
| `%%game_state` | Mapped to direction with type attribute, but full game state functionality may not be preserved | MusicXML does not have a dedicated game state element, so the best approach is to map it to a direction element with a type attribute. However, this may not preserve all game-specific functionality. |
| `%%loop` | Mapped to repeat element, but advanced loop functionality may not be preserved | MusicXML's repeat element provides basic loop functionality, but it may not support all the advanced loop features available in ABC+. |
| Complex articulations | May be simplified in ABC+ | ABC+ has limited support for complex articulations compared to MusicXML. Complex articulations with multiple components may need to be simplified during conversion. |
| Complex effects | May be simplified in ABC+ | ABC+ has limited support for effects compared to MusicXML. Complex effects may need to be simplified during conversion. |
| Advanced harmony elements | May be simplified in ABC+ | ABC+ has limited support for advanced harmony compared to MusicXML. Advanced harmony elements may need to be simplified during conversion. |

### 2.3 Structural Differences

| Area | Limitations | Justification |
|------|-------------|---------------|
| Hierarchical structure | MusicXML has a more hierarchical structure than ABC+ | ABC+ uses a flatter structure with directives and inline notation, while MusicXML uses a highly hierarchical structure with nested elements. This structural difference may require some elements to be represented differently during conversion. |
| Attribute handling | MusicXML uses more attributes than ABC+ | ABC+ uses directives and inline notation with limited attributes, while MusicXML uses extensive attributes to control element behavior. This difference may require some attributes to be mapped to different structures during conversion. |
| Encoding of musical information | MusicXML encodes some musical information differently than ABC+ | ABC+ and MusicXML encode some musical information differently, which may require special handling during conversion to ensure semantic equivalence. |

## 3. Exception Handling

### 3.1 ABC+ to MusicXML Conversion

#### 3.1.1 Elements with No MusicXML Equivalent
- **`X: (reference number)`**: Ignore during conversion or store as a custom attribute in the MusicXML file.
- **`L: (unit note length)`**: Calculate divisions based on the unit note length and use that for MusicXML duration values.

#### 3.1.2 Elements with Partial Mapping
- **`%%game_state`**: Map to `<direction><words type="game-state">` and preserve the state value as text content.
- **`%%loop`**: Map to `<repeat>` element and use appropriate attributes to preserve loop information.
- **Complex articulations**: Use multiple ABC+ decorations to represent complex articulations, or simplify if necessary.
- **Complex effects**: Use `%%fx` directive with descriptive names to represent complex effects.
- **Advanced harmony elements**: Use closest available ABC+ harmony directives to represent advanced harmony elements.

### 3.2 MusicXML to ABC+ Conversion

#### 3.2.1 Elements with No ABC+ Equivalent
- **Advanced layout elements**: Use closest available ABC+ layout directives or ignore layout details.
- **Advanced notation elements**: Use closest available ABC+ decorations or ignore advanced notation.
- **Some MIDI elements**: Store as custom directives or ignore during conversion.

#### 3.2.2 Elements with Partial Mapping
- **Complex articulations**: Simplify to closest available ABC+ decorations.
- **Complex effects**: Simplify to `%%fx` directives with descriptive names.
- **Advanced harmony elements**: Simplify to closest available ABC+ harmony directives.

## 4. Impact Assessment

### 4.1 High Impact Exceptions
- No high impact exceptions identified

### 4.2 Medium Impact Exceptions
- Advanced layout elements
- Advanced notation elements
- Complex articulations
- Complex effects
- Advanced harmony elements
- Game state functionality
- Loop functionality
- Structural differences

### 4.3 Low Impact Exceptions
- Reference number
- Unit note length
- MIDI elements

## 5. Recommendations

### 5.1 For ABC+ Specification Updates
- Add support for more advanced notation elements
- Enhance layout control capabilities
- Improve harmony representation
- Add support for complex articulations and effects

### 5.2 For Conversion Implementation
- Implement fallback mechanisms for unsupported elements
- Use descriptive directives for elements with no direct equivalent
- Ensure semantic equivalence even when structural differences exist
- Document all conversion limitations and workarounds

### 5.3 For Future Development
- Consider extending ABC+ to better support MusicXML features
- Develop a more comprehensive mapping for complex elements
- Create validation tools to verify conversion accuracy

## 6. Conclusion

While there are some exceptions to the conversion between ABC+ and MusicXML, most elements can be mapped with reasonable fidelity. The exceptions identified in this document are primarily related to advanced features that may not be essential for basic musical representation.

By understanding these exceptions and implementing the recommended workarounds, developers can create robust conversion tools that handle the majority of use cases effectively. As both formats continue to evolve, these exceptions may change, and the mapping can be updated to reflect new features and capabilities.