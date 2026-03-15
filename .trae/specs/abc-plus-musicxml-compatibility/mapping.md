# ABC+ to MusicXML Comprehensive Mapping Document

## 1. Introduction

This document provides a comprehensive bidirectional mapping between ABC+ notation and MusicXML 4.0 format. The goal is to enable seamless conversion between the two formats, ensuring that all musical information is preserved accurately.

## 2. Mapping Conventions

- **ABC+ to MusicXML**: Shows how ABC+ elements are mapped to MusicXML elements
- **MusicXML to ABC+**: Shows how MusicXML elements are mapped to ABC+ elements
- **Notes**: Additional information about the mapping
- **Examples**: Sample code demonstrating the mapping

## 3. Standard ABC 2.1 Elements

### 3.1 Header Elements

| ABC Element | MusicXML Element | Notes |
|-------------|------------------|-------|
| `X: (reference number)` | N/A | Not mapped to MusicXML |
| `T: (title)` | `<work><work-title>` | Mapped in score-partwise/work/work-title |
| `C: (composer)` | `<creator type="composer">` | Mapped in identification/creator |
| `A: (arranger)` | `<creator type="arranger">` | Mapped in identification/creator |
| `O: (lyricist)` | `<creator type="lyricist">` | Mapped in identification/creator |
| `Z: (translator)` | `<creator type="translator">` | Mapped in identification/creator |
| `G: (copyright)` | `<rights>` | Mapped in identification/rights |
| `M: (meter)` | `<time><beats><beat-type>` | Mapped in attributes/time |
| `L: (unit note length)` | N/A | Used to calculate durations |
| `Q: (tempo)` | `<metronome><beat-unit><per-minute>` and `<sound tempo>` | Mapped in direction/direction-type/metronome and direction/sound |
| `K: (key)` | `<key><fifths><mode>` | Mapped in attributes/key |
| `V: (voice)` | `<voice>` | Mapped in note/voice |

### 3.2 Music Elements

| ABC Element | MusicXML Element | Notes |
|-------------|------------------|-------|
| `w: (lyrics)` | `<lyric><syllabic><text>` | Mapped in note/lyric |
| Chords (e.g., "C") | `<harmony><root><kind>` | Mapped in harmony element |
| Notes (e.g., C, D, E) | `<note><pitch><step><octave>` | Mapped in note/pitch |
| Rests | `<note><rest>` | Mapped in note/rest |
| Slurs (e.g., ( | `<slur type="start/stop">` | Mapped in note/notations/slur |
| Barlines | `<barline><bar-style>` | Mapped in barline element |

## 4. ABC+ Extension Elements

### 4.1 Custom Directives

| ABC+ Element | MusicXML Element | Notes |
|--------------|------------------|-------|
| `%%dir` | `<direction><words>` | Mapped to direction element |
| `%%fx` | `<effect>` | Mapped to direction/direction-type/effect |
| `%%analysis` | `<harmony><function>` | Mapped to harmony/function element |
| `%%game_state` | `<direction><words type="game-state">` | Mapped to direction with type attribute |
| `%%loop` | `<repeat>` | Mapped to barline/repeat element |
| `%%art` | `<articulations>` | Mapped to note/notations/articulations |

### 4.2 Enhanced Decorations

| ABC+ Element | MusicXML Element | Notes |
|--------------|------------------|-------|
| `!fingering(N)!` | `<technical><fingering>` | Mapped in note/notations/technical/fingering |
| `!fret(N)!` | `<technical><fret>` | Mapped in note/notations/technical/fret |
| `!string(N)!` | `<technical><string>` | Mapped in note/notations/technical/string |
| `!@above text("...")!` | `<direction><words placement="above">` | Mapped to direction with placement attribute |
| `!@below text("...")!` | `<direction><words placement="below">` | Mapped to direction with placement attribute |
| `!p!` | `<dynamics><p>` | Mapped in direction/direction-type/dynamics/p |
| `!pp!` | `<dynamics><pp>` | Mapped in direction/direction-type/dynamics/pp |
| `!f!` | `<dynamics><f>` | Mapped in direction/direction-type/dynamics/f |
| `!ff!` | `<dynamics><ff>` | Mapped in direction/direction-type/dynamics/ff |
| `!n!` | `<dynamics><n>` | Mapped in direction/direction-type/dynamics/n |
| `!pppp!` | `<dynamics><pppp>` | Mapped in direction/direction-type/dynamics/pppp |
| `!ffff!` | `<dynamics><ffff>` | Mapped in direction/direction-type/dynamics/ffff |
| `!ffffff!` | `<dynamics><ffffff>` | Mapped in direction/direction-type/dynamics/ffffff |
| `!sfp!` | `<dynamics><sfp>` | Mapped in direction/direction-type/dynamics/sfp |
| `!sfz!` | `<dynamics><sfz>` | Mapped in direction/direction-type/dynamics/sfz |
| `!fp!` | `<dynamics><fp>` | Mapped in direction/direction-type/dynamics/fp |
| `!staccato!` | `<articulations><staccato>` | Mapped in note/notations/articulations/staccato |
| `!accent!` | `<articulations><accent>` | Mapped in note/notations/articulations/accent |
| `!marcato!` | `<articulations><strong-accent>` | Mapped in note/notations/articulations/strong-accent |
| `!soft-accent!` | `<articulations><soft-accent>` | Mapped in note/notations/articulations/soft-accent |
| `!caesura!` | `<articulations><caesura>` | Mapped in note/notations/articulations/caesura |
| `!delayed-turn!` | `<ornaments><delayed-turn>` | Mapped in note/notations/ornaments/delayed-turn |
| `!shake!` | `<ornaments><shake>` | Mapped in note/notations/ornaments/shake |
| `!schleifer!` | `<ornaments><schleifer>` | Mapped in note/notations/ornaments/schleifer |
| `!haydn!` | `<ornaments><haydn>` | Mapped in note/notations/ornaments/haydn |
| `!hammer-on(!` | `<technical><hammer-on type="start">` | Mapped in note/notations/technical/hammer-on |
| `!hammer-on)!` | `<technical><hammer-on type="stop">` | Mapped in note/notations/technical/hammer-on |
| `!pull-off(!` | `<technical><pull-off type="start">` | Mapped in note/notations/technical/pull-off |
| `!pull-off)!` | `<technical><pull-off type="stop">` | Mapped in note/notations/technical/pull-off |
| `!bend!` | `<technical><bend>` | Mapped in note/notations/technical/bend |
| `!tap!` | `<technical><tap>` | Mapped in note/notations/technical/tap |
| `!heel!` | `<technical><heel>` | Mapped in note/notations/technical/heel |
| `!toe!` | `<technical><toe>` | Mapped in note/notations/technical/toe |
| `!fingernails!` | `<technical><fingernails>` | Mapped in note/notations/technical/fingernails |
| `!golpe!` | `<technical><golpe>` | Mapped in note/notations/technical/golpe |
| `!double-tongue!` | `<technical><double-tongue>` | Mapped in note/notations/technical/double-tongue |
| `!triple-tongue!` | `<technical><triple-tongue>` | Mapped in note/notations/technical/triple-tongue |
| `!handbell!` | `<technical><handbell>` | Mapped in note/notations/technical/handbell |
| `!hole!` | `<technical><hole>` | Mapped in note/notations/technical/hole |
| `!arrow!` | `<technical><arrow>` | Mapped in note/notations/technical/arrow |
| `!brass-bend!` | `<technical><brass-bend>` | Mapped in note/notations/technical/brass-bend |
| `!snap!` | `<technical><snap-pizzicato>` | Mapped in note/notations/technical/snap-pizzicato |
| `!soft-pizzicato!` | `<technical><soft-pizzicato>` | Mapped in note/notations/technical/soft-pizzicato |
| `!scordatura!` | `<technical><scordatura>` | Mapped in note/notations/technical/scordatura |
| `!with-tongue!` | `<technical><with-tongue>` | Mapped in note/notations/technical/with-tongue |
| `!hihat!` | `<percussion><other-percussion name="hihat">` | Mapped in note/notations/technical/percussion |
| `!snare!` | `<percussion><other-percussion name="snare">` | Mapped in note/notations/technical/percussion |
| `!kick!` | `<percussion><other-percussion name="kick">` | Mapped in note/notations/technical/percussion |
| `!crash!` | `<percussion><other-percussion name="crash">` | Mapped in note/notations/technical/percussion |

### 4.3 Layout & Formatting Directives

| ABC+ Element | MusicXML Element | Notes |
|--------------|------------------|-------|
| `%%marker` | `<rehearsal>` | Mapped in direction/direction-type/rehearsal |
| `%%measurenumbering` | `<measure-numbering>` | Mapped in print/measure-numbering |
| `%%vskip` | `<system-distance>` | Mapped in system-distance element |
| `%%sep` | `<system-dividers>` | Mapped in system-layout/system-dividers |
| `%%newpage` | `<print new-page="yes">` | Mapped in print element with new-page attribute |
| `%%newline` | `<print new-system="yes">` | Mapped in print element with new-system attribute |
| `%%measurenb` | `<measure number>` | Mapped in measure element with number attribute |

### 4.4 Playback Control Directives

| ABC+ Element | MusicXML Element | Notes |
|--------------|------------------|-------|
| `%%swing` | `<sound swing="yes"/>` | Mapped in direction/sound with swing attribute |
| `%%swing-off` | `<sound swing="no"/>` | Mapped in direction/sound with swing attribute |
| `%%mute` | `<sound mute="yes"/>` | Mapped in direction/sound with mute attribute |
| `%%mute-off` | `<sound mute="no"/>` | Mapped in direction/sound with mute attribute |

### 4.5 Harmony & Bass Directives

| ABC+ Element | MusicXML Element | Notes |
|--------------|------------------|-------|
| `%%frame` | `<harmony><frame>` | Mapped in harmony/frame element |
| `%%fb` | `<figured-bass><figure>` | Mapped in figured-bass element |

### 4.6 Percussion Mapping

| ABC+ Element | MusicXML Element | Notes |
|--------------|------------------|-------|
| `I:percmap` | `<score-instrument>` and `<midi-instrument>` | Mapped in part-list/score-part/score-instrument and midi-instrument |

### 4.7 Lyric Extensions

| ABC+ Element | MusicXML Element | Notes |
|--------------|------------------|-------|
| `w: ^CT` | `<lyric><text type="analysis">CT</text>` | Mapped in lyric/text with type attribute |
| `melisma*` | `<lyric><syllabic>middle</syllabic>` | Mapped in lyric/syllabic element |

## 5. MusicXML to ABC+ Mapping

### 5.1 Core Elements

| MusicXML Element | ABC+ Element | Notes |
|------------------|-------------|-------|
| `<work><work-title>` | `T: (title)` | Mapped from score-partwise/work/work-title |
| `<creator type="composer">` | `C: (composer)` | Mapped from identification/creator |
| `<creator type="arranger">` | `A: (arranger)` | Mapped from identification/creator |
| `<creator type="lyricist">` | `O: (lyricist)` | Mapped from identification/creator |
| `<creator type="translator">` | `Z: (translator)` | Mapped from identification/creator |
| `<rights>` | `G: (copyright)` | Mapped from identification/rights |
| `<time><beats><beat-type>` | `M: (meter)` | Mapped from attributes/time |
| `<metronome><beat-unit><per-minute>` | `Q: (tempo)` | Mapped from direction/direction-type/metronome |
| `<key><fifths><mode>` | `K: (key)` | Mapped from attributes/key |
| `<voice>` | `V: (voice)` | Mapped from note/voice |
| `<lyric><syllabic><text>` | `w: (lyrics)` | Mapped from note/lyric |
| `<harmony><root><kind>` | Chords (e.g., "C") | Mapped from harmony element |
| `<note><pitch><step><octave>` | Notes (e.g., C, D, E) | Mapped from note/pitch |
| `<note><rest>` | Rests | Mapped from note/rest |
| `<slur type="start/stop">` | Slurs (e.g., ( | Mapped from note/notations/slur |
| `<barline><bar-style>` | Barlines | Mapped from barline element |

### 5.2 Direction Elements

| MusicXML Element | ABC+ Element | Notes |
|------------------|-------------|-------|
| `<direction><words>` | `%%dir` | Mapped to %%dir directive |
| `<direction><direction-type><effect>` | `%%fx` | Mapped to %%fx directive |
| `<direction><direction-type><rehearsal>` | `%%marker` | Mapped to %%marker directive |
| `<direction><sound swing="yes"/>` | `%%swing` | Mapped to %%swing directive |
| `<direction><sound swing="no"/>` | `%%swing-off` | Mapped to %%swing-off directive |
| `<direction><sound mute="yes"/>` | `%%mute` | Mapped to %%mute directive |
| `<direction><sound mute="no"/>` | `%%mute-off` | Mapped to %%mute-off directive |

### 5.3 Notation Elements

| MusicXML Element | ABC+ Element | Notes |
|------------------|-------------|-------|
| `<note><notations><technical><fingering>` | `!fingering(N)!` | Mapped to !fingering! decoration |
| `<note><notations><technical><fret>` | `!fret(N)!` | Mapped to !fret! decoration |
| `<note><notations><technical><string>` | `!string(N)!` | Mapped to !string! decoration |
| `<note><notations><articulations><staccato>` | `!staccato!` | Mapped to !staccato! decoration |
| `<note><notations><articulations><accent>` | `!accent!` | Mapped to !accent! decoration |
| `<note><notations><articulations><strong-accent>` | `!marcato!` | Mapped to !marcato! decoration |
| `<note><notations><articulations><soft-accent>` | `!soft-accent!` | Mapped to !soft-accent! decoration |
| `<note><notations><technical><hammer-on type="start">` | `!hammer-on(!` | Mapped to !hammer-on(! decoration |
| `<note><notations><technical><hammer-on type="stop">` | `!hammer-on)!` | Mapped to !hammer-on)! decoration |
| `<note><notations><technical><pull-off type="start">` | `!pull-off(!` | Mapped to !pull-off(! decoration |
| `<note><notations><technical><pull-off type="stop">` | `!pull-off)!` | Mapped to !pull-off)! decoration |

### 5.4 Layout Elements

| MusicXML Element | ABC+ Element | Notes |
|------------------|-------------|-------|
| `<system-distance>` | `%%vskip` | Mapped to %%vskip directive |
| `<print new-page="yes">` | `%%newpage` | Mapped to %%newpage directive |
| `<print new-system="yes">` | `%%newline` | Mapped to %%newline directive |
| `<measure number>` | `%%measurenb` | Mapped to %%measurenb directive |

## 6. Conversion Rules

### 6.1 General Rules

1. **Preservation of Musical Content**: All musical information must be preserved during conversion, including pitch, rhythm, dynamics, and articulation.

2. **Backward Compatibility**: Conversions should maintain backward compatibility with existing ABC+ documents.

3. **Semantic Equivalence**: The converted notation should have the same musical meaning as the original.

4. **Graceful Degradation**: If an element cannot be directly mapped, it should be represented in the closest possible equivalent or noted as an exception.

### 6.2 Complex Notations

#### 6.2.1 Articulations
- Articulations should be mapped to their closest ABC+ decoration equivalent.
- For complex articulations with multiple components, use multiple ABC+ decorations.

#### 6.2.2 Effects
- Effects should be mapped to the `%%fx` directive with appropriate attributes.
- If an effect has no direct equivalent, use a descriptive name in the `%%fx` directive.

#### 6.2.3 Layout Directives
- Layout directives should be mapped to their corresponding ABC+ directives.
- For layout elements with no direct ABC+ equivalent, use the closest available directive or note as an exception.

#### 6.2.4 Percussion
- Percussion mappings should use the `I:percmap` directive to map ABC pitches to percussion sounds.
- For complex percussion notation, use additional `%%fx` directives to specify sound details.

## 7. Exceptions

### 7.1 Elements with No Direct Equivalent

| Element | Reason for Exception |
|---------|---------------------|
| `X: (reference number)` | Not present in MusicXML |
| `L: (unit note length)` | Not present in MusicXML (calculated from other elements) |
| Some advanced MusicXML layout elements | Not supported in ABC+ |
| Some advanced MusicXML notation elements | Not supported in ABC+ |

### 7.2 Elements with Partial Mapping

| Element | Limitations |
|---------|-------------|
| `%%game_state` | Mapped to direction with type attribute, but full game state functionality may not be preserved |
| `%%loop` | Mapped to repeat element, but advanced loop functionality may not be preserved |
| Complex MusicXML articulations | May be simplified in ABC+ |

## 8. Validation Criteria

### 8.1 Successful Conversion Criteria

1. **Musical Content**: All musical notes, rhythms, and expressions are preserved.

2. **Structure**: The overall structure of the piece is maintained.

3. **Semantics**: The musical meaning is preserved.

4. **Readability**: The converted notation is readable and follows standard conventions.

5. **Backward Compatibility**: The converted notation is compatible with existing software.

### 8.2 Verification Process

1. **Visual Inspection**: Compare the original and converted notation visually.

2. **Playback Comparison**: Compare the playback of both versions.

3. **Structural Comparison**: Verify that the structure is preserved.

4. **Edge Case Testing**: Test with complex notations and edge cases.

## 9. Conclusion

This comprehensive mapping document provides a foundation for bidirectional conversion between ABC+ and MusicXML formats. While some elements may require exceptions or partial mapping, the goal is to ensure that all musical information is preserved as accurately as possible.

The mapping will continue to evolve as both formats develop, and additional elements may be added in future versions of the ABC+ specification.