# ABC+ to LilyPond Compatibility Analysis

## 1. Introduction

This document analyzes the compatibility between ABC+ notation and LilyPond format. LilyPond is a powerful music engraving program that produces high-quality sheet music. The goal is to provide a comprehensive mapping and conversion framework for integrating LilyPond support into the ABC+ to MusicXML converter app.

## 2. LilyPond Overview

LilyPond is a text-based music notation system that uses a declarative syntax to describe musical scores. It is known for producing professional-quality typesetting and supports a wide range of musical notation features.

### 2.1 Key LilyPond Concepts
- **Syntax**: Text-based with a lisp-like syntax
- **Hierarchical structure**: Scores are organized in a hierarchical structure
- **Extensive notation support**: Supports a wide range of musical notations
- **Customizability**: Highly customizable through its syntax

## 3. ABC+ to LilyPond Mapping

### 3.1 Basic Elements

| ABC+ Element | LilyPond | Notes |
|-------------|----------|-------|
| X: (reference number) | N/A | Not used in LilyPond |
| T: (title) | `\header { title = "..." }` | Mapped to header section |
| C: (composer) | `\header { composer = "..." }` | Mapped to header section |
| A: (arranger) | `\header { arranger = "..." }` | Mapped to header section |
| O: (lyricist) | `\header { poet = "..." }` | Mapped to header section |
| G: (copyright) | `\header { copyright = "..." }` | Mapped to header section |
| M: (meter) | `\time` | Mapped to time signature |
| L: (unit note length) | N/A | Calculated from note durations |
| Q: (tempo) | `\tempo` | Mapped to tempo marking |
| K: (key) | `\key` | Mapped to key signature |
| V: (voice) | `\voiceOne`, `\voiceTwo`, etc. | Mapped to voice contexts |
| w: (lyrics) | `\lyricmode` | Mapped to lyric contexts |
| Chords (e.g., "C") | Chord notation | Mapped to LilyPond chord syntax |
| Notes (e.g., C, D, E) | Note notation | Mapped to LilyPond note syntax |
| Rests | Rest notation | Mapped to LilyPond rest syntax |
| Slurs (e.g., ( | `(` and `)` | Mapped to LilyPond slur syntax |
| Barlines | Barline notation | Mapped to LilyPond barline syntax |

### 3.2 ABC+ Extensions

| ABC+ Element | LilyPond | Notes |
|-------------|----------|-------|
| `%%dir` | `\markup` | Mapped to text markup |
| `%%fx` | `\override` or `\once \override` | Mapped to LilyPond overrides |
| `%%analysis` | `\markup` | Mapped to text markup |
| `%%game_state` | `\markup` | Mapped to text markup |
| `%%loop` | `\repeat` | Mapped to LilyPond repeat syntax |
| `%%art` | Articulation notation | Mapped to LilyPond articulation syntax |
| `!fingering(N)!` | `\finger` | Mapped to LilyPond fingerings |
| `!fret(N)!` | `\fret` | Mapped to LilyPond tablature fret numbers |
| `!string(N)!` | `\stringNumber` | Mapped to LilyPond string numbers |
| `!@above text("...")!` | `\markup \above` | Mapped to positioned markup |
| `!@below text("...")!` | `\markup \below` | Mapped to positioned markup |
| `!staccato!` | `.` | Mapped to LilyPond staccato dot |
| `!accent!` | `>` | Mapped to LilyPond accent |
| `!marcato!` | `^` | Mapped to LilyPond marcato |
| `!soft-accent!` | `_` | Mapped to LilyPond soft accent |
| `!caesura!` | `\caesura` | Mapped to LilyPond caesura |
| `!bend!` | `\bendAfter` | Mapped to LilyPond bend notation |
| `!hammer-on(!` | `-!` | Mapped to LilyPond hammer-on |
| `!pull-off(!` | `!-` | Mapped to LilyPond pull-off |
| `%%marker` | `\mark` | Mapped to LilyPond rehearsal mark |
| `%%measurenumbering` | `\set Score.measureNumberVisibility` | Mapped to measure number visibility |
| `%%vskip` | `\vskip` | Mapped to vertical skip |
| `%%sep` | `\hrule` | Mapped to horizontal rule |
| `%%swing` | `\swing` | Mapped to LilyPond swing notation |
| `%%mute` | `\mute` | Mapped to LilyPond mute notation |
| `%%frame` | Chord diagram markup | Mapped to LilyPond chord diagrams |
| `%%fb` | Figured bass notation | Mapped to LilyPond figured bass |

## 4. LilyPond to ABC+ Mapping

### 4.1 Basic Elements

| LilyPond Element | ABC+ Element | Notes |
|-----------------|-------------|-------|
| `\header { title = "..." }` | `T: (title)` | Mapped to title directive |
| `\header { composer = "..." }` | `C: (composer)` | Mapped to composer directive |
| `\header { arranger = "..." }` | `A: (arranger)` | Mapped to arranger directive |
| `\header { poet = "..." }` | `O: (lyricist)` | Mapped to lyricist directive |
| `\header { copyright = "..." }` | `G: (copyright)` | Mapped to copyright directive |
| `\time` | `M: (meter)` | Mapped to time signature directive |
| `\tempo` | `Q: (tempo)` | Mapped to tempo directive |
| `\key` | `K: (key)` | Mapped to key signature directive |
| `\voiceOne`, `\voiceTwo` | `V: (voice)` | Mapped to voice directive |
| `\lyricmode` | `w: (lyrics)` | Mapped to lyrics directive |
| Chord notation | Chords (e.g., "C") | Mapped to ABC+ chord syntax |
| Note notation | Notes (e.g., C, D, E) | Mapped to ABC+ note syntax |
| Rest notation | Rests | Mapped to ABC+ rest syntax |
| `(` and `)` | Slurs (e.g., ( | Mapped to ABC+ slur syntax |
| Barline notation | Barlines | Mapped to ABC+ barline syntax |

### 4.2 Advanced Elements

| LilyPond Element | ABC+ Element | Notes |
|-----------------|-------------|-------|
| `\markup` | `%%dir` or `!@above text("...")!` | Mapped to text directives or decorations |
| `\override` | `%%fx` | Mapped to effect directive |
| `\repeat` | `%%loop` | Mapped to loop directive |
| Articulation notation | `!decoration!` | Mapped to ABC+ decorations |
| `\finger` | `!fingering(N)!` | Mapped to fingering decoration |
| `\fret` | `!fret(N)!` | Mapped to fret decoration |
| `\stringNumber` | `!string(N)!` | Mapped to string decoration |
| `\mark` | `%%marker` | Mapped to marker directive |
| `\swing` | `%%swing` | Mapped to swing directive |
| `\mute` | `%%mute` | Mapped to mute directive |

## 5. Conversion Rules

### 5.1 ABC+ to LilyPond Conversion

1. **Header Processing**
   - Map ABC+ header elements to LilyPond header section
   - Set up score structure with appropriate contexts

2. **Music Processing**
   - Map notes, rests, and chords to LilyPond syntax
   - Handle rhythm and timing
   - Map slurs and ties

3. **Directive Processing**
   - Map layout directives to LilyPond layout commands
   - Map playback directives to LilyPond performance commands
   - Map harmony directives to LilyPond harmony syntax

4. **Decoration Processing**
   - Map articulations to LilyPond articulation syntax
   - Map technical annotations to LilyPond markup

### 5.2 LilyPond to ABC+ Conversion

1. **Header Processing**
   - Extract header information and map to ABC+ directives
   - Determine key and time signature

2. **Music Processing**
   - Extract notes, rests, and chords
   - Calculate note durations
   - Handle voices and staffs

3. **Directive Processing**
   - Extract layout commands and map to ABC+ directives
   - Extract performance commands and map to ABC+ directives

4. **Decoration Processing**
   - Extract articulations and map to ABC+ decorations
   - Extract technical annotations and map to ABC+ decorations

## 6. Gaps and Limitations

### 6.1 ABC+ to LilyPond Gaps

| Element | Limitation | Reason |
|---------|------------|--------|
| Game state markers | No direct LilyPond equivalent | LilyPond doesn't support game state information |
| Some effects | Limited support | LilyPond has different effect handling |

### 6.2 LilyPond to ABC+ Gaps

| Element | Limitation | Reason |
|---------|------------|--------|
| Complex polyphony | Limited support | ABC+ has simpler voice handling |
| Advanced layout control | Limited support | ABC+ has simpler layout directives |
| Custom markup | Limited support | ABC+ has simpler text handling |
| Microtonal notation | Limited support | ABC+ has limited microtonal support |

## 7. Implementation Considerations

### 7.1 ABC+ to LilyPond Conversion

- **Syntax Differences**: LilyPond has a more complex syntax than ABC+
- **Hierarchical Structure**: LilyPond uses a hierarchical structure that may require flattening for ABC+
- **Notation Support**: LilyPond supports more advanced notation than ABC+

### 7.2 LilyPond to ABC+ Conversion

- **Simplification**: Some LilyPond features may need to be simplified for ABC+
- **Layout Information**: LilyPond's detailed layout information may not map directly to ABC+
- **Custom Extensions**: LilyPond's custom extensions may not have ABC+ equivalents

## 8. Conclusion

LilyPond provides a comprehensive notation system that can represent most ABC+ elements with high fidelity. While there are some gaps in the mapping, particularly for advanced layout control and custom extensions, the core musical information can be effectively converted between the formats.

For the ABC+ to MusicXML converter app, LilyPond support would be valuable for producing high-quality engraved scores and for interfacing with the LilyPond ecosystem.