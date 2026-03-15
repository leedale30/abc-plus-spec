# NoteWorthy Composer Compatibility Analysis

## 1. Introduction

This document analyzes the compatibility between ABC+ notation and NoteWorthy Composer, a music notation software known for its simplicity and affordability.

## 2. NoteWorthy Composer Overview

NoteWorthy Composer is a music notation software that allows users to create, edit, and print sheet music. It is known for its user-friendly interface and support for MIDI playback.

### 2.1 Key Features
- Music notation and composition
- MIDI playback
- Support for various musical symbols and articulations
- Import/export capabilities
- Affordable pricing

## 3. ABC+ to NoteWorthy Composer Mapping

### 3.1 Basic Elements

| ABC+ Element | NoteWorthy Composer | Notes |
|-------------|---------------------|-------|
| T: (title) | Title field | Mapped to score title |
| C: (composer) | Composer field | Mapped to composer field |
| A: (arranger) | Arranger field | Mapped to arranger field |
| O: (lyricist) | Lyricist field | Mapped to lyricist field |
| G: (copyright) | Copyright field | Mapped to copyright field |
| M: (meter) | Time signature | Mapped to time signature |
| L: (unit note length) | Default note length | Mapped to default note length |
| Q: (tempo) | Tempo marking | Mapped to tempo marking |
| K: (key) | Key signature | Mapped to key signature |
| V: (voice) | Staff | Mapped to staff |
| w: (lyrics) | Lyrics | Mapped to lyrics |
| Chords (e.g., "C") | Chord symbols | Mapped to chord symbols |
| Notes (e.g., C, D, E) | Notes | Mapped to notes |
| Rests | Rests | Mapped to rests |
| Slurs (e.g., ( | Slurs | Mapped to slurs |
| Barlines | Barlines | Mapped to barlines |

### 3.2 ABC+ Extensions

| ABC+ Element | NoteWorthy Composer | Notes |
|-------------|---------------------|-------|
| `%%dir` | Text directions | Mapped to text directions |
| `%%fx` | Effects | Mapped to effects |
| `%%analysis` | Text annotations | Mapped to text annotations |
| `%%game_state` | Text annotations | Mapped to text annotations |
| `%%loop` | Repeat markings | Mapped to repeat markings |
| `%%art` | Articulations | Mapped to articulations |
| `!fingering(N)!` | Fingering | Mapped to fingering |
| `!fret(N)!` | Fret numbers | Mapped to fret numbers |
| `!string(N)!` | String numbers | Mapped to string numbers |
| `!@above text("...")!` | Text above staff | Mapped to text above staff |
| `!@below text("...")!` | Text below staff | Mapped to text below staff |
| `!staccato!` | Staccato | Mapped to staccato |
| `!accent!` | Accent | Mapped to accent |
| `!marcato!` | Marcato | Mapped to marcato |
| `!soft-accent!` | Soft accent | Mapped to soft accent |
| `!caesura!` | Caesura | Mapped to caesura |
| `!bend!` | Bend | Mapped to bend |
| `!hammer-on(!` | Hammer-on | Mapped to hammer-on |
| `!pull-off(!` | Pull-off | Mapped to pull-off |
| `%%marker` | Rehearsal marks | Mapped to rehearsal marks |
| `%%measurenumbering` | Measure numbering | Mapped to measure numbering |
| `%%vskip` | Vertical spacing | Mapped to vertical spacing |
| `%%sep` | Separators | Mapped to separators |
| `%%swing` | Swing playback | Mapped to swing playback |
| `%%mute` | Mute | Mapped to mute |
| `%%frame` | Chord diagrams | Mapped to chord diagrams |
| `%%fb` | Figured bass | Mapped to figured bass |
| `I:percmap` | Percussion mapping | Mapped to percussion mapping |

## 4. Conversion Rules

### 4.1 ABC+ to NoteWorthy Composer Conversion

1. **Header Processing**
   - Extract header information and map to NoteWorthy Composer fields
   - Set up basic score structure

2. **Music Processing**
   - Map notes, rests, and chords to NoteWorthy Composer elements
   - Handle rhythm and timing
   - Map slurs and ties

3. **Directive Processing**
   - Map ABC+ directives to appropriate NoteWorthy Composer elements
   - Handle layout and performance directives

4. **Decoration Processing**
   - Map ABC+ decorations to NoteWorthy Composer articulations and technical elements
   - Handle positioned text and other decorations

### 4.2 NoteWorthy Composer to ABC+ Conversion

1. **Header Processing**
   - Extract header information from NoteWorthy Composer and map to ABC+ directives
   - Set up basic ABC+ header

2. **Music Processing**
   - Extract notes, rests, and chords from NoteWorthy Composer
   - Calculate note durations
   - Handle voices and staffs

3. **Directive Processing**
   - Extract NoteWorthy Composer directives and map to ABC+ directives
   - Handle layout and performance directives

4. **Decoration Processing**
   - Extract NoteWorthy Composer articulations and technical elements
   - Map to ABC+ decorations

## 5. Gaps and Limitations

### 5.1 ABC+ to NoteWorthy Composer Gaps

| Element | Limitation | Reason |
|---------|------------|--------|
| Some advanced articulations | Limited support | NoteWorthy Composer has limited support for some advanced articulations |
| Complex layout directives | Limited support | NoteWorthy Composer has limited support for complex layout directives |

### 5.2 NoteWorthy Composer to ABC+ Gaps

| Element | Limitation | Reason |
|---------|------------|--------|
| Some NoteWorthy-specific features | Limited support | Some NoteWorthy-specific features may not have direct equivalents in ABC+ |

## 6. Implementation Considerations

### 6.1 ABC+ to NoteWorthy Composer Conversion

- **File Format**: NoteWorthy Composer uses its own .nwc file format
- **MIDI Support**: NoteWorthy Composer has good MIDI support, which can be leveraged for conversion
- **Layout**: NoteWorthy Composer has its own layout system that may require adjustments

### 6.2 NoteWorthy Composer to ABC+ Conversion

- **Extraction**: May require parsing NoteWorthy Composer files or using export features
- **Simplification**: Some NoteWorthy-specific features may need to be simplified for ABC+
- **Mapping**: Careful mapping of NoteWorthy Composer elements to ABC+ equivalents

## 7. Conclusion

NoteWorthy Composer provides a solid foundation for music notation and has good compatibility with ABC+ for core musical elements. While there may be some limitations with advanced features, the core musical information can be effectively converted between the two formats.

For the ABC+ to MusicXML converter app, NoteWorthy Composer support would be valuable for users who prefer this software for its simplicity and affordability. The conversion would allow for the exchange of musical information between ABC+ and NoteWorthy Composer, expanding the utility of the converter app.