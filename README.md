# ABC+ Notation Specification

![ABC+ Spec Banner](assets/banner.png)

**ABC+** is a professional evolution of the [ABC notation](https://abcnotation.com/) standard. It introduces high-fidelity musical directives designed for modern music applications, game audio orchestration, and advanced MusicXML 4.0 interchange. ABC+ now supports compatibility with a wide range of music notation formats, including MEI, Dorico, Flat.io, TuxGuitar, StaffPad, and NoteWorthy Composer.

## Quick Start

```abc
X:1
T:Example Song
M:4/4
L:1/8
K:C
%%dir mood="energetic"
"C"C2DE F2GA | "G"B2AG "C"c4 |
w: Hel-lo world, this is ABC+!
```

## Features

- ✅ Full ABC notation compatibility
- ✅ Custom directives (`%%dir`, `%%fx`, `%%loop`)
- ✅ Enhanced articulation, ornaments, and dynamics
- ✅ Playback control (`%%swing`, `%%mute`)
- ✅ Advanced layout (`%%vskip`, `%%sep`, `%%measurenumbering`)
- ✅ Game audio integration (`%%game_state`)
- ✅ MusicXML 4.0 export support
- ✅ MEI (Music Encoding Initiative) compatibility
- ✅ Support for multiple notation formats (Dorico, Flat.io, TuxGuitar, StaffPad, NoteWorthy Composer)
- ✅ Comprehensive compatibility mapping

## Documentation

| Document | Description |
| :--- | :--- |
| [SPECIFICATION.md](SPECIFICATION.md) | Complete syntax reference with MEI mapping |
| [CHANGELOG.md](CHANGELOG.md) | Version history |
| [CHECKLIST.md](CHECKLIST.md) | Detailed MusicXML element coverage |
| [examples/](examples/) | Sample ABC+ files |
| [Compatibility Analysis](.trae/specs/abc-plus-extended-compatibility/) | Detailed compatibility analysis for various formats |

## Format Compatibility

ABC+ has been analyzed for compatibility with the following music notation formats:

### High Compatibility
- **MusicXML** - Highest compatibility, primary interchange format
- **LilyPond** - Very high compatibility for notation and layout
- **MEI** - Very high compatibility for scholarly features
- **Dorico** - Very high compatibility with professional notation
- **StaffPad** - Very high compatibility with touch-based notation
- **Guitar Pro** - High compatibility for guitar-specific features
- **Finale/Sibelius/MuseScore** - High compatibility with core elements

### Medium Compatibility
- **MIDI 1.0/2.0** - Good for core musical elements
- **Noteflight** - Good compatibility with core elements
- **Flat.io** - Good compatibility with web-based notation
- **TuxGuitar** - Good compatibility for string instruments
- **NoteWorthy Composer** - Good compatibility with affordable notation software
- **Band-in-a-Box** - Good for chord progressions and accompaniment

## Installation

ABC+ is a notation format. To use it:

1. **Write ABC+ files** using any text editor
2. **Convert to MusicXML** using the [ABC+ Web Converter](https://github.com/leedale30/abc-to-xml-converter)
3. **Import into** notation software (MuseScore 4, Sibelius, Finale, Dorico, StaffPad, etc.)

## Version

Current specification version: **1.4.0**

## License

MIT License - See [LICENSE](LICENSE) for details.

## Related Projects

- [abc-to-xml-converter](https://github.com/leedale30/abc-to-xml-converter) - ABC+ to MusicXML converter app
