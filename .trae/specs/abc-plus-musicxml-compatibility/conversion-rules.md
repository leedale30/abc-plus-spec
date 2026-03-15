# ABC+ to MusicXML Conversion Rules for Complex Notations

## 1. Introduction

This document provides detailed conversion rules for complex musical notations between ABC+ and MusicXML formats. The goal is to ensure that complex musical elements are accurately preserved during conversion, maintaining the musical integrity of the original notation.

## 2. General Conversion Principles

### 2.1 Preservation of Musical Content
- All musical information must be preserved during conversion, including pitch, rhythm, dynamics, and articulation.
- The semantic meaning of the notation should be maintained, even if the structural representation differs.

### 2.2 Backward Compatibility
- Conversions should maintain backward compatibility with existing ABC+ documents.
- Existing ABC+ syntax should continue to work as expected.

### 2.3 Graceful Degradation
- If an element cannot be directly mapped, it should be represented in the closest possible equivalent.
- When degradation is necessary, the most important musical information should be preserved.

## 3. Conversion Rules for Specific Elements

### 3.1 Articulations

#### 3.1.1 Simple Articulations
| ABC+ Decoration | MusicXML Element | Rule |
|-----------------|------------------|------|
| `!staccato!` | `<articulations><staccato>` | Direct mapping |
| `!accent!` | `<articulations><accent>` | Direct mapping |
| `!marcato!` | `<articulations><strong-accent>` | Direct mapping |
| `!soft-accent!` | `<articulations><soft-accent>` | Direct mapping |
| `!caesura!` | `<articulations><caesura>` | Direct mapping |

#### 3.1.2 Complex Articulations
| ABC+ Decoration | MusicXML Element | Rule |
|-----------------|------------------|------|
| `!hammer-on(!` | `<technical><hammer-on type="start">` | Direct mapping for start |
| `!hammer-on)!` | `<technical><hammer-on type="stop">` | Direct mapping for stop |
| `!pull-off(!` | `<technical><pull-off type="start">` | Direct mapping for start |
| `!pull-off)!` | `<technical><pull-off type="stop">` | Direct mapping for stop |
| Multiple articulations | Multiple `<articulations>` elements | Use multiple ABC+ decorations in sequence |

### 3.2 Effects

#### 3.2.1 Basic Effects
| ABC+ Directive | MusicXML Element | Rule |
|---------------|------------------|------|
| `%%fx name="reverb"` | `<effect name="reverb">` | Direct mapping |
| `%%fx name="delay"` | `<effect name="delay">` | Direct mapping |

#### 3.2.2 Complex Effects
| ABC+ Directive | MusicXML Element | Rule |
|---------------|------------------|------|
| `%%fx name="effect" speed="value"` | `<effect name="effect" speed="value">` | Map attributes to MusicXML attributes |
| Custom effects | `<effect name="custom">` | Use descriptive name in `%%fx` directive |

### 3.3 Layout Directives

#### 3.3.1 Page and System Layout
| ABC+ Directive | MusicXML Element | Rule |
|---------------|------------------|------|
| `%%newpage` | `<print new-page="yes">` | Direct mapping |
| `%%newline` | `<print new-system="yes">` | Direct mapping |
| `%%vskip 20` | `<system-distance>20</system-distance>` | Direct mapping |

#### 3.3.2 Measure and Rehearsal Marks
| ABC+ Directive | MusicXML Element | Rule |
|---------------|------------------|------|
| `%%marker Chorus` | `<rehearsal>Chorus</rehearsal>` | Direct mapping |
| `%%measurenumbering yes` | `<measure-numbering>yes</measure-numbering>` | Direct mapping |

### 3.4 Harmony Elements

#### 3.4.1 Chord Frames
| ABC+ Directive | MusicXML Element | Rule |
|---------------|------------------|------|
| `%%frame C (0)x32010` | `<harmony><frame><fret>0</fret><string>x32010</string></frame></harmony>` | Map to frame element with appropriate attributes |

#### 3.4.2 Figured Bass
| ABC+ Directive | MusicXML Element | Rule |
|---------------|------------------|------|
| `%%fb 6 4 3` | `<figured-bass><figure>6</figure><figure>4</figure><figure>3</figure></figured-bass>` | Map each figure to a separate figure element |

### 3.5 Percussion Mapping

| ABC+ Directive | MusicXML Element | Rule |
|---------------|------------------|------|
| `I:percmap ^c' E5 42 x` | `<score-instrument id="P1"><instrument-name>Hi-hat</instrument-name></score-instrument><midi-instrument id="P1"><midi-channel>10</midi-channel><midi-program>42</midi-program></midi-instrument>` | Map to score-instrument and midi-instrument elements |

### 3.6 Lyric Extensions

| ABC+ Element | MusicXML Element | Rule |
|-------------|------------------|------|
| `w: ^CT ^P ^CT` | `<lyric><text type="analysis">CT</text></lyric><lyric><text type="analysis">P</text></lyric><lyric><text type="analysis">CT</text></lyric>` | Map analysis annotations to text elements with type attribute |
| `melisma*` | `<lyric><syllabic>middle</syllabic></lyric>` | Map to syllabic element with appropriate value |

### 3.7 Game and Interactive Elements

| ABC+ Directive | MusicXML Element | Rule |
|---------------|------------------|------|
| `%%game_state state="value"` | `<direction><words type="game-state">value</words></direction>` | Map to direction element with type attribute |
| `%%loop safe="true"` | `<barline><repeat direction="forward"/></barline>` | Map to repeat element with appropriate attributes |

### 3.8 Advanced Notation

#### 3.8.1 Ornaments
| ABC+ Decoration | MusicXML Element | Rule |
|-----------------|------------------|------|
| `!delayed-turn!` | `<ornaments><delayed-turn>` | Direct mapping |
| `!shake!` | `<ornaments><shake>` | Direct mapping |
| `!schleifer!` | `<ornaments><schleifer>` | Direct mapping |
| `!haydn!` | `<ornaments><haydn>` | Direct mapping |

#### 3.8.2 Technical Elements
| ABC+ Decoration | MusicXML Element | Rule |
|-----------------|------------------|------|
| `!bend!` | `<technical><bend>` | Direct mapping |
| `!tap!` | `<technical><tap>` | Direct mapping |
| `!heel!` | `<technical><heel>` | Direct mapping |
| `!toe!` | `<technical><toe>` | Direct mapping |
| `!fingernails!` | `<technical><fingernails>` | Direct mapping |
| `!golpe!` | `<technical><golpe>` | Direct mapping |
| `!double-tongue!` | `<technical><double-tongue>` | Direct mapping |
| `!triple-tongue!` | `<technical><triple-tongue>` | Direct mapping |
| `!handbell!` | `<technical><handbell>` | Direct mapping |
| `!hole!` | `<technical><hole>` | Direct mapping |
| `!arrow!` | `<technical><arrow>` | Direct mapping |
| `!brass-bend!` | `<technical><brass-bend>` | Direct mapping |
| `!snap!` | `<technical><snap-pizzicato>` | Direct mapping |
| `!soft-pizzicato!` | `<technical><soft-pizzicato>` | Direct mapping |
| `!scordatura!` | `<technical><scordatura>` | Direct mapping |
| `!with-tongue!` | `<technical><with-tongue>` | Direct mapping |

### 3.9 Dynamics

| ABC+ Decoration | MusicXML Element | Rule |
|-----------------|------------------|------|
| `!p!` | `<dynamics><p>` | Direct mapping |
| `!pp!` | `<dynamics><pp>` | Direct mapping |
| `!f!` | `<dynamics><f>` | Direct mapping |
| `!ff!` | `<dynamics><ff>` | Direct mapping |
| `!n!` | `<dynamics><n>` | Direct mapping |
| `!pppp!` | `<dynamics><pppp>` | Direct mapping |
| `!ffff!` | `<dynamics><ffff>` | Direct mapping |
| `!ffffff!` | `<dynamics><ffffff>` | Direct mapping |
| `!sfp!` | `<dynamics><sfp>` | Direct mapping |
| `!sfz!` | `<dynamics><sfz>` | Direct mapping |
| `!fp!` | `<dynamics><fp>` | Direct mapping |

## 4. Conversion Workflows

### 4.1 ABC+ to MusicXML Conversion

1. **Header Processing**
   - Map ABC+ header elements to MusicXML identification and work elements
   - Calculate divisions based on L: directive

2. **Music Processing**
   - Map notes, rests, and chords to MusicXML note elements
   - Map slurs and ties to MusicXML notations elements
   - Map articulations and decorations to appropriate MusicXML elements

3. **Directive Processing**
   - Map layout directives to MusicXML print elements
   - Map playback directives to MusicXML sound elements
   - Map harmony directives to MusicXML harmony elements

4. **Post-Processing**
   - Validate the resulting MusicXML
   - Ensure all musical information is preserved

### 4.2 MusicXML to ABC+ Conversion

1. **Header Processing**
   - Map MusicXML identification and work elements to ABC+ header elements
   - Calculate unit note length based on divisions

2. **Music Processing**
   - Map MusicXML note elements to ABC+ notes, rests, and chords
   - Map MusicXML notations elements to ABC+ slurs and decorations
   - Map articulations and technical elements to ABC+ decorations

3. **Directive Processing**
   - Map MusicXML print elements to ABC+ layout directives
   - Map MusicXML sound elements to ABC+ playback directives
   - Map MusicXML harmony elements to ABC+ harmony directives

4. **Post-Processing**
   - Validate the resulting ABC+
   - Ensure all musical information is preserved

## 5. Edge Cases and Special Considerations

### 5.1 Complex Rhythms
- **ABC+**: Uses tuplets and dotted notes
- **MusicXML**: Uses tuplet elements and duration values
- **Rule**: Map tuplets to MusicXML tuplet elements, preserving the ratio of actual to normal notes

### 5.2 Multiple Voices
- **ABC+**: Uses V: directives to separate voices
- **MusicXML**: Uses voice elements within notes
- **Rule**: Map each ABC+ voice to a separate MusicXML voice element

### 5.3 Percussion Notation
- **ABC+**: Uses I:percmap to map pitches to percussion sounds
- **MusicXML**: Uses unpitched elements with percussion details
- **Rule**: Map I:percmap entries to appropriate MusicXML percussion elements

### 5.4 Microtonal Notation
- **ABC+**: Uses accidental symbols and microtonal extensions
- **MusicXML**: Uses accidental elements with alter attributes
- **Rule**: Map microtonal accidentals to appropriate MusicXML accidental elements with alter values

## 6. Validation Rules

### 6.1 ABC+ to MusicXML Validation
- The resulting MusicXML should be valid according to the MusicXML 4.0 schema
- All musical information should be preserved
- The structure should be semantically equivalent to the original ABC+

### 6.2 MusicXML to ABC+ Validation
- The resulting ABC+ should be valid according to the ABC+ specification
- All musical information should be preserved
- The structure should be semantically equivalent to the original MusicXML

## 7. Conclusion

These conversion rules provide a comprehensive framework for converting complex musical notations between ABC+ and MusicXML formats. By following these rules, developers can ensure that complex musical elements are accurately preserved during conversion, maintaining the musical integrity of the original notation.

The rules will continue to evolve as both formats develop, and additional rules may be added in future versions to address new features and edge cases.