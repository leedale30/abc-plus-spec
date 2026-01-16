# ABC+ Changelog

All notable changes to the ABC+ specification will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

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
