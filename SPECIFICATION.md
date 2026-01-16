# ABC+ Specification

Version: 1.0.0  
Status: Draft  
Last Updated: 2026-01-17

---

## 1. Overview

ABC+ extends standard ABC notation with custom directives for enhanced music applications. It maintains full backward compatibility with ABC 2.1 while adding support for:

- Custom performance directives
- Game/interactive audio markers
- Enhanced articulation control
- Structured metadata

---

## 2. Standard ABC Compatibility

ABC+ supports all standard ABC 2.1 notation. See [ABC Notation Standard](https://abcnotation.com/wiki/abc:standard:v2.1) for the base specification.

---

## 3. ABC+ Custom Directives

Custom directives use the `%%` prefix followed by the directive name and attributes.

### 3.1 Direction Directive (`%%dir`)

Adds performance directions that map to MusicXML `<direction>` elements.

**Syntax:**

```
%%dir attribute="value" [attribute2="value2" ...]
```

**Attributes:**

| Attribute | Type | Description |
|-----------|------|-------------|
| `mood` | string | Performance mood (e.g., "joyful", "aggressive") |
| `intensity` | float | Intensity level 0.0-1.0 |

**Example:**

```abc
%%dir mood="melancholic" intensity="0.7"
C2DE F2GA |
```

**MusicXML Mapping:**

```xml
<direction placement="above">
  <direction-type>
    <words>dir: mood='melancholic' intensity='0.7'</words>
  </direction-type>
</direction>
```

---

### 3.2 Effects Directive (`%%fx`)

Defines audio effects or processing instructions.

**Syntax:**

```
%%fx name="effect_name" [speed="value"]
```

**Attributes:**

| Attribute | Type | Description |
|-----------|------|-------------|
| `name` | string | Effect name (e.g., "reverb", "distortion") |
| `speed` | string | Effect speed/rate |

**Example:**

```abc
%%fx name="tremolo" speed="fast"
```

---

### 3.3 Analysis Directive (`%%analysis`)

Marks harmonic or structural analysis points.

**Syntax:**

```
%%analysis function="value"
```

**Attributes:**

| Attribute | Type | Description |
|-----------|------|-------------|
| `function` | string | Harmonic function (e.g., "I", "V7", "ii") |

**Example:**

```abc
%%analysis function="V7/IV"
```

---

### 3.4 Game State Directive (`%%game_state`)

Marks synchronization points for game/interactive audio.

**Syntax:**

```
%%game_state state="value"
```

**Attributes:**

| Attribute | Type | Description |
|-----------|------|-------------|
| `state` | string | Game state identifier |

**Example:**

```abc
%%game_state state="boss_fight_intro"
```

**MusicXML Mapping:** None (stripped during conversion, used by game engines)

---

### 3.5 Loop Directive (`%%loop`)

Marks loop points for audio playback.

**Syntax:**

```
%%loop safe="true|false"
```

**Attributes:**

| Attribute | Type | Description |
|-----------|------|-------------|
| `safe` | boolean | Whether loop point is musically safe |

**Example:**

```abc
%%loop safe="true"
```

**MusicXML Mapping:** None (metadata only)

---

### 3.6 Articulation Directive (`%%art`)

Applies articulation to the following note(s).

**Syntax:**

```
%%art type="articulation_type"
```

**Attributes:**

| Attribute | Type | Description |
|-----------|------|-------------|
| `type` | string | Articulation type (e.g., "staccato", "accent") |

**Example:**

```abc
%%art type="staccato"
C D E F |
```

**MusicXML Mapping:**

```xml
<notations>
  <articulations>
    <staccato/>
  </articulations>
</notations>
```

---

## 4. Enhanced Decorations

ABC+ supports extended decoration syntax using `!decoration!` notation.

### 4.1 Custom Slurs

```abc
!1slur-start! C D E !1slur-end! F |  % Named slur
```

### 4.2 Custom Tuplets

```abc
!3:2 tuplet-start! C D E !tuplet-end! |
```

### 4.3 Positioned Text

```abc
!@x,y text("Custom positioned text")! C |
```

---

## 5. Percussion Mapping

### 5.1 I:percmap Directive

Maps ABC pitches to percussion sounds.

**Syntax:**

```
I:percmap pitch [display-step] [midi-number] [notehead]
```

**Example:**

```abc
I:percmap ^c' E5 42 x        % Hi-hat
I:percmap _B, D4 36 normal   % Bass drum
```

### 5.2 %%drummap Directive (Legacy)

```abc
%%drummap C bass_drum
%%drummap E snare
%%drummap ^G hihat_closed
```

---

## 6. Lyric Extensions

### 6.1 Analysis Abbreviations

Lyrics starting with `^` are expanded as analysis annotations:

| Abbreviation | Expansion |
|--------------|-----------|
| `^CT` | Chord Tone |
| `^P` | Passing Tone |
| `^N` | Neighbor Tone |
| `^Sus` | Suspension |
| `^App` | Appoggiatura |
| `^Ant` | Anticipation |
| `^Esc` | Escape Tone |
| `^Ped` | Pedal Point |

**Example:**

```abc
C E G c |
w: ^CT ^P ^CT ^CT
```

### 6.2 Melisma Control

```abc
C D E F |
w: word _melisma-start * * _melisma-end next
```

---

## 7. MusicXML Mapping Reference

| ABC+ Element | MusicXML Element |
|--------------|------------------|
| `%%dir` | `<direction><words>` |
| `%%fx` | `<direction><words>` |
| `%%analysis` | `<direction><words>` |
| `%%art` | `<notations><articulations>` |
| `%%game_state` | *(stripped)* |
| `%%loop` | *(stripped)* |
| `I:percmap` | `<unpitched>` |

---

## 8. Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0.0 | 2026-01-17 | Initial specification |

---

## 9. References

- [ABC Notation Standard v2.1](https://abcnotation.com/wiki/abc:standard:v2.1)
- [MusicXML 4.0 Specification](https://www.w3.org/2021/06/musicxml40/)
- [abc2xml Converter](https://wim.vree.org/svgParse/abc2xml.html)
