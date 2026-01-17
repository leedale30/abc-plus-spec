# ABC+ Changelog

All notable changes to the ABC+ specification will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.2.0] - 2026-01-17

### Added

- MusicXML 4.0 Playback Controls:
  - `%%swing` / `%%swing-off` - Toggle swing playback (maps to `<sound swing="yes"/>`)
  - `%%mute` / `%%mute-off` - Toggle instrument muting (maps to `<sound mute="yes"/>`)
- Layout Refinements:
  - `%%vskip <number>` - Fixed direct implementation via `<system-layout>` in `<print>`
  - `%%sep` - Added horizontal system separators
- Advanced Ornaments & Technical Marks:
  - Support for `!vertical-turn!`, `!shake!`, `!schleifer!`, `!haydn!`
  - Guitar/String technical marks: `!hammer-on!`, `!pull-off!`, `!bend!`, `!tap!`, `!fingernails!`, `!golpe!`
  - Organ/Keyboard marks: `!heel!`, `!toe!`
- Robustness:
  - Fixed `NoneType` errors in `staffDecos` when processing global directives before the first measure.
  - Corrected `addDirection` argument handling for figured bass and other notations.

## [1.1.0] - 2026-01-17

### Added

- MusicXML 4.0 Layout Controls:
  - `%%measurenumbering yes|no` - Toggle bar numbering
  - `%%vskip <number>` - Vertical system distance
  - `%%sep` - Horizontal separator
- Advanced Notations:
  - `%%marker <text>` - Rehearsal marks
  - `%%frame <chord> <frets>` - Guitar chord diagrams
  - `%%fb <figures>` - Figured bass notation
- Improved Decoration Support:
  - Grouped sub-containers for `<articulations>`, `<ornaments>`, and `<technical>`
  - Parameterized decorations: `fingering(1)`, `fret(5)`, `string(6)`
  - Cleaned up XML output (removed diagnostic comments)

## [1.0.0] - 2026-01-17

### Added

- Initial ABC+ specification release
- Core directives:
  - `%%dir` - Performance directions
  - `%%fx` - Audio effects
  - `%%analysis` - Harmonic analysis markers
  - `%%game_state` - Game audio synchronization
  - `%%loop` - Loop point markers
  - `%%art` - Note articulations
- Extended decoration syntax for named slurs and tuplets
- Percussion mapping via `I:percmap`
- Lyric analysis abbreviations (`^CT`, `^P`, etc.)
- MusicXML mapping documentation
- JSON schema for directive validation

### Compatibility

- Full backward compatibility with ABC 2.1
- Tested with abc2xml converter v239
