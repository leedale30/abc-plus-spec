# ABC+ to MIDI Compatibility Analysis

## 1. Introduction

This document analyzes the compatibility between ABC+ notation and MIDI (Musical Instrument Digital Interface) formats, including both MIDI 1.0 and MIDI 2.0. The goal is to provide a comprehensive mapping and conversion framework for integrating MIDI support into the ABC+ to MusicXML converter app.

## 2. MIDI 1.0 Overview

MIDI 1.0 is a standard protocol for communicating musical information between electronic musical instruments, computers, and other devices. It uses a set of messages to represent musical events such as note on/off, pitch bend, and control changes.

### 2.1 Key MIDI 1.0 Concepts
- **Channels**: 16 channels per MIDI port
- **Notes**: 128 possible notes (0-127)
- **Velocity**: Note on/off velocity (0-127)
- **Control Change**: Various control parameters (0-127)
- **Program Change**: Instrument selection (0-127)
- **Pitch Bend**: Pitch modification (-8192 to +8191)

## 3. MIDI 2.0 Overview

MIDI 2.0 is the latest version of the MIDI standard, offering enhanced capabilities over MIDI 1.0:

### 3.1 Key MIDI 2.0 Enhancements
- **32-bit resolution** for controllers and pitch bend
- **16-bit note numbers** (16384 possible notes)
- **Per-note controllers** for more expressive control
- **Property exchange** for device configuration
- **Universal MIDI Packet (UMP)** format

## 4. ABC+ to MIDI Mapping

### 4.1 Basic Elements

| ABC+ Element | MIDI 1.0 | MIDI 2.0 | Notes |
|-------------|----------|----------|-------|
| Notes (e.g., C, D, E) | Note On/Off messages | Note On/Off messages | Map ABC+ pitch to MIDI note number |
| Rests | No direct equivalent | No direct equivalent | Represented by absence of note messages |
| Velocity | Note On velocity (default) | Note On velocity (default) | Can be set via ABC+ decorations |
| Duration | Note On/Off timing | Note On/Off timing | Calculated from ABC+ note length |
| Tempo | Set Tempo message | Set Tempo message | Mapped from Q: directive |
| Time signature | Time Signature message | Time Signature message | Mapped from M: directive |
| Key signature | No direct equivalent | No direct equivalent | Can be inferred from key |
| Voices | MIDI channels | MIDI channels | Each voice mapped to a different channel |

### 4.2 ABC+ Extensions

| ABC+ Element | MIDI 1.0 | MIDI 2.0 | Notes |
|-------------|----------|----------|-------|
| `%%swing` | No direct equivalent | No direct equivalent | Can be implemented in playback logic |
| `%%mute` | All Sound Off message | All Sound Off message | Mapped to appropriate control message |
| `!staccato!` | Shorter note duration | Shorter note duration | Implemented via timing adjustments |
| `!accent!` | Higher velocity | Higher velocity | Mapped to velocity increase |
| `!bend!` | Pitch Bend message | Pitch Bend message | Mapped to pitch bend events |
| `!hammer-on(!` | Legato playing | Legato playing | Implemented via note timing |
| `!pull-off(!` | Legato playing | Legato playing | Implemented via note timing |
| `%%fx` | Control Change messages | Control Change messages | Mapped to appropriate control parameters |
| `I:percmap` | Program Change messages | Program Change messages | Maps ABC+ percussion to MIDI drum sounds |

## 5. MIDI to ABC+ Mapping

### 5.1 Basic Elements

| MIDI Element | ABC+ Element | Notes |
|-------------|-------------|-------|
| Note On/Off | Notes | Mapped to ABC+ note notation |
| Velocity | Note decorations | Can be mapped to accents or other dynamics |
| Pitch Bend | `!bend!` decoration | Mapped to bend decoration |
| Program Change | Instrument directive | Mapped to instrument specification |
| Control Change | `%%fx` directive | Mapped to effect directives |
| Tempo Change | `Q:` directive | Mapped to tempo directive |
| Time Signature | `M:` directive | Mapped to time signature directive |

## 6. Conversion Rules

### 6.1 ABC+ to MIDI Conversion

1. **Note Mapping**
   - Map ABC+ pitch to MIDI note number
   - Calculate note duration based on L: directive and note length
   - Set velocity based on dynamics or default value

2. **Timing**
   - Calculate MIDI ticks based on tempo and note duration
   - Handle swing feel if `%%swing` is present

3. **Expressiveness**
   - Map articulations to appropriate MIDI messages
   - Handle pitch bends and other expressive controls

4. **Percussion**
   - Use `I:percmap` to map ABC+ percussion to MIDI drum sounds
   - Set appropriate MIDI channel (typically 10 for drums)

### 6.2 MIDI to ABC+ Conversion

1. **Note Extraction**
   - Extract note on/off events and map to ABC+ notes
   - Calculate note lengths based on timing

2. **Dynamics**
   - Map velocity to dynamics markings
   - Extract control changes for effects

3. **Structure**
   - Detect time signature changes
   - Detect tempo changes
   - Group notes into measures

## 7. Gaps and Limitations

### 7.1 ABC+ to MIDI Gaps

| Element | Limitation | Reason |
|---------|------------|--------|
| Lyrics | No direct MIDI equivalent | MIDI doesn't support text lyrics |
| Chord symbols | No direct MIDI equivalent | MIDI doesn't support chord symbols |
| Layout directives | No direct MIDI equivalent | MIDI doesn't support visual layout |
| Game state markers | No direct MIDI equivalent | MIDI doesn't support game state information |

### 7.2 MIDI to ABC+ Gaps

| Element | Limitation | Reason |
|---------|------------|--------|
| Polyphonic aftertouch | No direct ABC+ equivalent | ABC+ doesn't support per-note pressure |
| Channel pressure | No direct ABC+ equivalent | ABC+ doesn't support channel pressure |
| SysEx messages | No direct ABC+ equivalent | ABC+ doesn't support system exclusive messages |
| MIDI clock | No direct ABC+ equivalent | ABC+ doesn't support real-time clock information |

## 8. MIDI 2.0 Specific Considerations

### 8.1 Enhanced Capabilities

| MIDI 2.0 Feature | ABC+ Mapping | Notes |
|-----------------|-------------|-------|
| 32-bit controllers | `%%fx` with higher resolution | Map to extended effect parameters |
| 16-bit note numbers | Extended pitch range | Support microtonal notation |
| Per-note controllers | `!decoration!` per note | Enhanced expressiveness |
| Property exchange | Metadata mapping | Map device properties to ABC+ metadata |

### 8.2 Implementation Challenges

- **Backward Compatibility**: Ensure support for both MIDI 1.0 and 2.0
- **Increased Resolution**: Handle higher resolution data in ABC+
- **Complex Messages**: Parse and generate UMP format messages

## 9. Conclusion

MIDI (both 1.0 and 2.0) provides a good foundation for representing ABC+ musical content, particularly for playback purposes. While there are some gaps in the mapping, particularly for text-based elements and visual layout, the core musical information can be effectively converted between the formats.

MIDI 2.0 offers enhanced capabilities that can be leveraged to support more expressive and nuanced musical performances, which can be mapped to ABC+ extensions where possible.

For the ABC+ to MusicXML converter app, MIDI support would be valuable for playback functionality and for interfacing with electronic musical instruments and software.