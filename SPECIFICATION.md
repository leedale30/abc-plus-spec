# ABC+ Specification

Version: 1.2.0  
Status: Draft  
Last Updated: 2026-01-17

---

## 1. Overview

ABC+ extends standard ABC notation with custom directives for enhanced music applications. It maintains full backward compatibility with ABC 2.1 while adding support for:

- Custom performance directives
- Game/interactive audio markers
- Enhanced articulation control
- Playback and Layout refinement
- Structured metadata

---

## 2. Standard ABC Compatibility

ABC+ supports all standard ABC 2.1 notation. See [ABC Notation Standard](https://abcnotation.com/wiki/abc:standard:v2.1) for the base specification.

---

## 3. ABC+ Custom Directives

Custom directives use the `%%` prefix followed by the directive name and attributes.

### 3.1 Direction Directive (`%%dir`)

Adds performance directions that map to MusicXML `<direction>` elements.

**Syntax:** `%%dir attribute="value" [attribute2="value2" ...]`

**Attributes:** mood, intensity.

**Example:** `%%dir mood="melancholic" intensity="0.7"`

---

### 3.2 Effects Directive (`%%fx`)

Defines audio effects or processing instructions.

**Syntax:** `%%fx name="effect_name" [speed="value"]`

---

### 3.3 Analysis Directive (`%%analysis`)

Marks harmonic or structural analysis points.

**Syntax:** `%%analysis function="value"`

---

### 3.4 Game State Directive (`%%game_state`)

Marks synchronization points for game/interactive audio.

**Syntax:** `%%game_state state="value"`

---

### 3.5 Loop Directive (`%%loop`)

Marks loop points for audio playback.

**Syntax:** `%%loop safe="true|false"`

---

### 3.6 Articulation Directive (`%%art`)

Applies articulation to the following note(s).

**Syntax:** `%%art type="articulation_type"`

---

## 4. Enhanced Decorations

ABC+ supports extended decoration syntax using `!decoration!` notation.

### 4.1 Parameterized Notations

```abc
!fingering(1)! !fret(5)! !string(6)! C |  % Maps to <technical> elements
```

### 4.2 Positioned Text

```abc
!@above text("Custom positioned text")! C |  % Use @above or @below
```

---

## 5. Layout & Formatting Directives

### 5.1 Rehearsal Marks (`%%marker`)

Adds a rehearsal mark (e.g., A, B, Chorus) to the score.

```abc
%%marker Chorus
```

### 5.2 Measure Numbering (`%%measurenumbering`)

Toggles measure numbering for the system or score.

```abc
%%measurenumbering yes
```

### 5.3 Vertical Spacing (`%%vskip`)

Adjusts vertical distance between systems in MusicXML tenths.

```abc
%%vskip 20
```

### 5.4 Separators (`%%sep`)

Adds a horizontal separator line between systems.

```abc
%%sep
```

---

## 6. Playback Control Directives

### 6.1 Swing (`%%swing`, `%%swing-off`)

Toggles swing playback interpretation.

```abc
%%swing
%%swing-off
```

### 6.2 Mute (`%%mute`, `%%mute-off`)

Toggles instrument muting for playback.

```abc
%%mute
%%mute-off
```

---

## 7. Harmony & Bass Directives

### 7.1 Guitar Chord Frames (`%%frame`)

**Syntax:** `%%frame <name> (<fret>)<pattern>`

```abc
%%frame C (0)x32010
```

### 7.2 Figured Bass (`%%fb`)

**Syntax:** `%%fb <figures>`

```abc
%%fb 6 4 3
```

---

## 8. Percussion Mapping

### 8.1 I:percmap Directive

Maps ABC pitches to percussion sounds and noteheads.

```abc
I:percmap ^c' E5 42 x        % Hi-hat
```

---

## 9. Lyric Extensions

### 9.1 Analysis Abbreviations

Lyrics starting with `^` are expanded as analysis annotations.

**Example:** `w: ^CT ^P ^CT`

### 9.2 Melisma Control

Use `_` for melisma or `extend` for structured lyrics.

---

## 10. MusicXML Mapping Reference

| ABC+ Element | MusicXML Element |
|--------------|------------------|
| `%%dir` | `<direction><words>` |
| `%%swing` | `<sound swing="yes"/>` |
| `%%mute` | `<sound mute="yes"/>` |
| `%%vskip` | `<system-distance>` |
| `%%marker` | `<rehearsal>` |
| `!fingering(N)!` | `<technical><fingering>` |

---

## 11. Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.2.0 | 2026-01-17 | Added playback and advanced layout directives |
| 1.1.0 | 2026-01-17 | Added chord frames and figured bass |
| 1.0.0 | 2026-01-16 | Initial specification |

---

## 12. References

- [ABC Notation Standard v2.1](https://abcnotation.com/wiki/abc:standard:v2.1)
- [MusicXML 4.0 Specification](https://www.w3.org/2021/06/musicxml40/)
