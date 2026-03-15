# ABC+ Format Compatibility Chart

## 1. Introduction

This chart provides a comprehensive overview of the compatibility between ABC+ notation and various music notation formats. It highlights which elements are compatible, partially compatible, or incompatible across different formats.

## 2. Compatibility Matrix

### 2.1 Core Elements

| Element | ABC+ | MusicXML | MIDI 1.0 | MIDI 2.0 | LilyPond | Guitar Pro | Finale | Sibelius | MuseScore | Noteflight | CMN | Band-in-a-Box | MEI | Dorico | Flat.io | TuxGuitar | StaffPad | NoteWorthy Composer |
|---------|------|----------|----------|----------|----------|------------|--------|----------|-----------|-----------|-----|---------------|-----|--------|--------|-----------|----------|---------------------|
| Notes | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Rests | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Chords | ✓ | ✓ | ✗ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Key signature | ✓ | ✓ | ✗ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Time signature | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Tempo | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Lyrics | ✓ | ✓ | ✗ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ |
| Voices | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Slurs | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Ties | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |

### 2.2 ABC+ Extensions

| Element | ABC+ | MusicXML | MIDI 1.0 | MIDI 2.0 | LilyPond | Guitar Pro | Finale | Sibelius | MuseScore | Noteflight | CMN | Band-in-a-Box | MEI | Dorico | Flat.io | TuxGuitar | StaffPad | NoteWorthy Composer |
|---------|------|----------|----------|----------|----------|------------|--------|----------|-----------|-----------|-----|---------------|-----|--------|--------|-----------|----------|---------------------|
| `%%dir` | ✓ | ✓ | ✗ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ |
| `%%fx` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ~ | ~ | ✓ | ~ |
| `%%analysis` | ✓ | ✓ | ✗ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ~ | ✗ | ~ | ~ |
| `%%game_state` | ✓ | ✓ | ✗ | ✗ | ✓ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ~ | ~ | ✗ | ✗ | ~ | ~ |
| `%%loop` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ~ | ✓ | ✓ | ✓ |
| `%%art` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `!fingering(N)!` | ✓ | ✓ | ✗ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `!fret(N)!` | ✓ | ✓ | ✗ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `!string(N)!` | ✓ | ✓ | ✗ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `!@above text("...")!` | ✓ | ✓ | ✗ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ |
| `!staccato!` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `!accent!` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `!marcato!` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `!soft-accent!` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ |
| `!caesura!` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ✓ | ~ | ✓ | ~ |
| `!bend!` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `!hammer-on(!` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `!pull-off(!` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `%%marker` | ✓ | ✓ | ✗ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `%%measurenumbering` | ✓ | ✓ | ✗ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✗ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ |
| `%%vskip` | ✓ | ✓ | ✗ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✗ | ✓ | ✓ | ~ | ✗ | ✓ | ~ |
| `%%sep` | ✓ | ✓ | ✗ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✗ | ✓ | ✓ | ~ | ✗ | ✓ | ~ |
| `%%swing` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ |
| `%%mute` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ~ | ✓ | ✓ |
| `%%frame` | ✓ | ✓ | ✗ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `%%fb` | ✓ | ✓ | ✗ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ✓ | ~ | ✓ | ~ |
| `I:percmap` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ~ | ~ | ✓ | ~ |

### 2.3 Format-Specific Features

| Feature | ABC+ | MusicXML | MIDI 1.0 | MIDI 2.0 | LilyPond | Guitar Pro | Finale | Sibelius | MuseScore | Noteflight | CMN | Band-in-a-Box | MEI | Dorico | Flat.io | TuxGuitar | StaffPad | NoteWorthy Composer |
|---------|------|----------|----------|----------|----------|------------|--------|----------|-----------|-----------|-----|---------------|-----|--------|--------|-----------|----------|---------------------|
| Tablature | ✓ | ✓ | ✗ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Drum mapping | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ~ |
| Microtonal notation | ✓ | ✓ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✗ | ✓ | ✓ | ✓ | ✗ | ✓ | ~ |
| Advanced layout | ✓ | ✓ | ✗ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✗ | ✓ | ✗ | ✓ | ✓ | ~ | ✗ | ✓ | ~ |
| Performance directions | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ | ~ | ~ | ✓ | ✓ |
| MIDI control | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✗ | ✓ | ~ | ✓ | ~ | ~ | ✓ | ✓ |
| Game state | ✓ | ✓ | ✗ | ✗ | ✓ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ~ | ~ | ✗ | ✗ | ~ | ~ |
| Style selection | ✓ | ✓ | ✗ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ~ | ✓ | ✓ |
| Accompaniment generation | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✓ | ✗ | ~ | ✗ | ✗ | ~ | ~ |
| Scholarly annotations | ✗ | ~ | ✗ | ✗ | ~ | ✗ | ~ | ~ | ~ | ~ | ~ | ✗ | ✓ | ~ | ~ | ✗ | ~ | ~ |
| Musicological analysis | ✗ | ~ | ✗ | ✗ | ~ | ✗ | ~ | ~ | ~ | ~ | ~ | ✗ | ✓ | ~ | ~ | ✗ | ~ | ~ |
| Editorial markup | ✗ | ~ | ✗ | ✗ | ~ | ✗ | ~ | ~ | ~ | ~ | ~ | ✗ | ✓ | ~ | ~ | ✗ | ~ | ~ |
| Handwriting recognition | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✓ | ✗ |
| Collaborative editing | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ~ | ✓ | ✗ | ✗ | ✗ | ✗ | ✓ | ✗ | ~ | ✗ |

## 3. Compatibility Legend

- **✓**: Fully compatible
- **✗**: Incompatible
- **~**: Partially compatible

## 4. Summary

### 4.1 High Compatibility Formats

- **MusicXML**: Highest compatibility with ABC+, as it was the primary target for the original mapping
- **LilyPond**: Very high compatibility, especially for notation and layout
- **MEI**: Very high compatibility, especially for scholarly features and detailed notation
- **Dorico**: Very high compatibility, similar to other professional notation software
- **StaffPad**: Very high compatibility, with support for most ABC+ features
- **Guitar Pro**: High compatibility, especially for guitar-specific features
- **Finale/Sibelius/MuseScore**: High compatibility with core elements

### 4.2 Medium Compatibility Formats

- **MIDI 1.0**: Good compatibility for core musical elements, limited for text-based elements
- **MIDI 2.0**: Better compatibility than MIDI 1.0, especially for expressiveness
- **Noteflight**: Good compatibility with core elements, limited for advanced features
- **Flat.io**: Good compatibility with core elements, limited support for some advanced features
- **TuxGuitar**: Good compatibility for guitar-specific features, limited support for some notation elements
- **NoteWorthy Composer**: Good compatibility with core elements, limited support for some advanced features
- **Band-in-a-Box**: Good compatibility for chord progressions and basic song structure, limited for detailed notation

### 4.3 Low Compatibility Areas

- **Game state markers**: Only supported in ABC+, MusicXML, and LilyPond
- **Advanced layout**: Limited support in some web-based formats and Band-in-a-Box
- **Text-based elements**: Limited support in MIDI formats
- **Detailed notation**: Limited support in Band-in-a-Box

## 5. Implementation Recommendations

1. **Primary Targets**: Focus on MusicXML, LilyPond, and MIDI 2.0 for the highest compatibility

2. **Intermediate Format**: Use MusicXML as the intermediate format for converting to other formats

3. **Priority Features**: Prioritize core musical elements (notes, rests, chords, articulations) for all formats

4. **Format-Specific Features**: Implement format-specific features for each format where appropriate

5. **Fallback Mechanisms**: Implement fallback mechanisms for incompatible elements

## 6. Conclusion

ABC+ has excellent compatibility with most common music notation formats, especially for core musical elements. The highest compatibility is with MusicXML, LilyPond, MEI, Dorico, StaffPad, and other professional notation software like Finale and Sibelius.

While there are some format-specific features that may not map directly, the core musical information can be effectively converted between most formats. By using MusicXML as an intermediate format, the ABC+ to MusicXML converter app can support a wide range of music notation formats with minimal additional development effort.

The addition of Dorico, Flat.io, TuxGuitar, StaffPad, and NoteWorthy Composer to the compatibility analysis further demonstrates the versatility of ABC+ as a notation format that can bridge the gap between different music notation systems, from professional software to web-based platforms, specialized tools for string instruments, and affordable notation software for casual users.