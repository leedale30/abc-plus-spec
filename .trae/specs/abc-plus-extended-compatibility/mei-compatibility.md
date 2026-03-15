# ABC+ to MEI Compatibility Analysis

## 1. Introduction

This document analyzes the compatibility between ABC+ notation and MEI (Music Encoding Initiative) format. MEI is a music notation format designed for musicology and digital humanities research, providing a comprehensive framework for encoding musical information. The goal is to provide a comprehensive mapping and conversion framework for integrating MEI support into the ABC+ to MusicXML converter app.

## 2. MEI Overview

MEI (Music Encoding Initiative) is an XML-based markup language for the representation of music notation documents. It is designed to facilitate the encoding, processing, and retrieval of musical information for scholarly and educational purposes.

### 2.1 Key MEI Concepts
- **XML-based**: Uses XML syntax for encoding musical information
- **Comprehensive**: Supports a wide range of musical notation features
- **Scholarly focus**: Designed for musicological research and analysis
- **Extensible**: Allows for custom extensions and annotations
- **File format**: .mei (XML-based)

## 3. ABC+ to MEI Mapping

### 3.1 Basic Elements

| ABC+ Element | MEI | Notes |
|-------------|-----|-------|
| T: (title) | `<title>` | Mapped to title element |
| C: (composer) | `<composer>` | Mapped to composer element |
| A: (arranger) | `<arranger>` | Mapped to arranger element |
| O: (lyricist) | `<lyricist>` | Mapped to lyricist element |
| G: (copyright) | `<rights>` | Mapped to rights element |
| M: (meter) | `<meter>` | Mapped to meter element |
| L: (unit note length) | `<noteLength>` | Mapped to note length element |
| Q: (tempo) | `<tempo>` | Mapped to tempo element |
| K: (key) | `<keySig>` | Mapped to key signature element |
| V: (voice) | `<voice>` | Mapped to voice element |
| w: (lyrics) | `<lyric>` | Mapped to lyric element |
| Chords (e.g., "C") | `<harm>` | Mapped to harmony element |
| Notes (e.g., C, D, E) | `<note>` | Mapped to note element |
| Rests | `<rest>` | Mapped to rest element |
| Slurs (e.g., ( | `<slur>` | Mapped to slur element |
| Barlines | `<barLine>` | Mapped to barline element |

### 3.2 ABC+ Extensions

| ABC+ Element | MEI | Notes |
|-------------|-----|-------|
| `%%dir` | `<dir>` | Mapped to direction element |
| `%%fx` | `<effect>` | Mapped to effect element |
| `%%analysis` | `<analysis>` | Mapped to analysis element |
| `%%game_state` | `<annot>` | Mapped to annotation element |
| `%%loop` | `<repeat>` | Mapped to repeat element |
| `%%art` | `<artic>` | Mapped to articulation element |
| `!fingering(N)!` | `<fingering>` | Mapped to fingering element |
| `!fret(N)!` | `<fret>` | Mapped to fret element |
| `!string(N)!` | `<string>` | Mapped to string element |
| `!@above text("...")!` | `<dir place="above">` | Mapped to direction with placement |
| `!@below text("...")!` | `<dir place="below">` | Mapped to direction with placement |
| `!staccato!` | `<artic artic="staccato">` | Mapped to staccato articulation |
| `!accent!` | `<artic artic="accent">` | Mapped to accent articulation |
| `!marcato!` | `<artic artic="marcato">` | Mapped to marcato articulation |
| `!soft-accent!` | `<artic artic="softAccent">` | Mapped to soft accent articulation |
| `!caesura!` | `<artic artic="caesura">` | Mapped to caesura articulation |
| `!bend!` | `<bend>` | Mapped to bend element |
| `!hammer-on(!` | `<slide type="hammerOn">` | Mapped to hammer-on slide |
| `!pull-off(!` | `<slide type="pullOff">` | Mapped to pull-off slide |
| `%%marker` | `<label>` | Mapped to label element |
| `%%measurenumbering` | `<measureNumbering>` | Mapped to measure numbering element |
| `%%vskip` | `<space>` | Mapped to space element |
| `%%sep` | `<divider>` | Mapped to divider element |
| `%%swing` | `<tempo swing="yes">` | Mapped to tempo with swing attribute |
| `%%mute` | `<mute>` | Mapped to mute element |
| `%%frame` | `<chordDiagram>` | Mapped to chord diagram element |
| `%%fb` | `<figuredBass>` | Mapped to figured bass element |
| `I:percmap` | `<percussion>` | Mapped to percussion element |

## 4. MEI to ABC+ Mapping

### 4.1 Basic Elements

| MEI Element | ABC+ Element | Notes |
|-------------|--------------|-------|
| `<title>` | `T: (title)` | Mapped to title directive |
| `<composer>` | `C: (composer)` | Mapped to composer directive |
| `<arranger>` | `A: (arranger)` | Mapped to arranger directive |
| `<lyricist>` | `O: (lyricist)` | Mapped to lyricist directive |
| `<rights>` | `G: (copyright)` | Mapped to copyright directive |
| `<meter>` | `M: (meter)` | Mapped to time signature directive |
| `<noteLength>` | `L: (unit note length)` | Mapped to unit note length directive |
| `<tempo>` | `Q: (tempo)` | Mapped to tempo directive |
| `<keySig>` | `K: (key)` | Mapped to key signature directive |
| `<voice>` | `V: (voice)` | Mapped to voice directive |
| `<lyric>` | `w: (lyrics)` | Mapped to lyrics directive |
| `<harm>` | Chords (e.g., "C") | Mapped to chord symbols |
| `<note>` | Notes (e.g., C, D, E) | Mapped to note notation |
| `<rest>` | Rests | Mapped to rest notation |
| `<slur>` | Slurs (e.g., ( | Mapped to slur notation |
| `<barLine>` | Barlines | Mapped to barline notation |

### 4.2 Advanced Elements

| MEI Element | ABC+ Element | Notes |
|-------------|--------------|-------|
| `<dir>` | `%%dir` | Mapped to direction directive |
| `<effect>` | `%%fx` | Mapped to effect directive |
| `<analysis>` | `%%analysis` | Mapped to analysis directive |
| `<annot>` | `%%dir` | Mapped to direction directive |
| `<repeat>` | `%%loop` | Mapped to loop directive |
| `<artic>` | `!decoration!` | Mapped to decoration |
| `<fingering>` | `!fingering(N)!` | Mapped to fingering decoration |
| `<fret>` | `!fret(N)!` | Mapped to fret decoration |
| `<string>` | `!string(N)!` | Mapped to string decoration |
| `<label>` | `%%marker` | Mapped to marker directive |
| `<space>` | `%%vskip` | Mapped to vskip directive |
| `<divider>` | `%%sep` | Mapped to sep directive |
| `<tempo swing="yes">` | `%%swing` | Mapped to swing directive |
| `<mute>` | `%%mute` | Mapped to mute directive |
| `<chordDiagram>` | `%%frame` | Mapped to frame directive |
| `<figuredBass>` | `%%fb` | Mapped to figured bass directive |
| `<percussion>` | `I:percmap` | Mapped to percmap directive |

## 5. Conversion Rules

### 5.1 ABC+ to MEI Conversion

1. **Header Processing**
   - Extract header information and map to MEI header elements
   - Set up basic MEI structure

2. **Music Processing**
   - Map notes, rests, and chords to MEI elements
   - Handle rhythm and timing
   - Map slurs and ties

3. **Directive Processing**
   - Map ABC+ directives to appropriate MEI elements
   - Handle layout and performance directives

4. **Decoration Processing**
   - Map ABC+ decorations to MEI articulations and technical elements
   - Handle positioned text and other decorations

### 5.2 MEI to ABC+ Conversion

1. **Header Processing**
   - Extract header information from MEI and map to ABC+ directives
   - Set up basic ABC+ header

2. **Music Processing**
   - Extract notes, rests, and chords from MEI
   - Calculate note durations
   - Handle voices and staffs

3. **Directive Processing**
   - Extract MEI directives and map to ABC+ directives
   - Handle layout and performance directives

4. **Decoration Processing**
   - Extract MEI articulations and technical elements
   - Map to ABC+ decorations

## 6. Gaps and Limitations

### 6.1 ABC+ to MEI Gaps

| Element | Limitation | Reason |
|---------|------------|--------|
| Game state markers | Limited support | MEI has annotation support but not specific game state elements |
| Some effects | Limited support | MEI has different effect handling |

### 6.2 MEI to ABC+ Gaps

| Element | Limitation | Reason |
|---------|------------|--------|
| Complex scholarly annotations | Limited support | ABC+ has limited annotation capabilities |
| Detailed musicological analysis | Limited support | ABC+ is focused on practical notation, not scholarly analysis |
| Advanced editorial markup | Limited support | ABC+ has limited support for editorial markup |
| Multiple editorial layers | Limited support | ABC+ doesn't support multiple editorial layers |

## 7. Implementation Considerations

### 7.1 ABC+ to MEI Conversion

- **XML Structure**: MEI uses a more complex XML structure than ABC+
- **Scholarly Features**: MEI has many scholarly features that ABC+ doesn't support
- **Extensibility**: MEI's extensibility allows for custom annotations and extensions

### 7.2 MEI to ABC+ Conversion

- **Simplification**: Some MEI features may need to be simplified for ABC+
- **Focus on Performance**: ABC+ is more focused on performance than scholarly analysis
- **Limited Annotations**: ABC+ has limited support for the detailed annotations possible in MEI

## 8. Conclusion

MEI provides a comprehensive framework for encoding musical information, with strong support for scholarly research and analysis. While there are some gaps in the mapping, particularly for scholarly features, the core musical information can be effectively converted between ABC+ and MEI.

For the ABC+ to MusicXML converter app, MEI support would be valuable for users who need to work with musicological research data or digital humanities projects. The conversion would allow for the exchange of musical information between practical notation systems (ABC+) and scholarly encoding systems (MEI).