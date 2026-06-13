# ABC+ Specification

Version: 1.6.0  
Status: Draft  
Last Updated: 2026-06-12

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

### 4.3 Pedal, Octave & Glissando Lines

Real, **playback-capable** spanners. Attach the decoration to the next note with **no space**.
Use these rather than text annotations (`"^Ped."`, `"^8va"`, `"^gliss."`), which render only as
cosmetic `<words>` and do **not** play back.

```abc
!ped(!C !ped-change!E !ped)!G |   % sustain-pedal LINE with a re-pedal notch (line style)
!ped!C  E  G  !ped-up!c |         % sustain pedal, ASTERISK style ("Ped." ... "*")
!8va!c d e !8va)!f |              % octave line up (close with ")")
!gliss(!C !gliss)!G |             % glissando slide
```

For continuous re-pedalling use one `!ped(!` … `!ped)!` line with `!ped-change!` at each harmony
change; a run of bare `!ped!` signs merges into a single held pedal in most renderers.

> **Pedal decoration vs. pedal directive.** The `!ped...!` decorations above are the visible,
> score-level pedal marks that also play back (`<pedal>`). They are distinct from the global
> *sound* directives `%%damper-pedal` / `%%soft-pedal` / `%%sostenuto-pedal` (§6.6), which set
> `<sound damper-pedal="...">` for playback only, with no visible mark. Soft pedal (una corda)
> has no useful playback rendering, so it is written as text (`"_una corda"` / `"_tre corde"`).

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

### 5.5 Advanced Page Layout (`%%pagelayout`)

Defines precise page layout parameters, mapped directly to MusicXML `<page-layout>`. Values are given in tenths.

**Syntax:** `%%pagelayout [margins="top,bottom,left,right"] [scale="X"]`

```abc
%%pagelayout margins="100,100,50,50" scale="40"
```

### 5.6 Advanced System Layout (`%%systemlayout`)

Defines system-specific layout adjustments, mapped to MusicXML `<system-layout>`.

**Syntax:** `%%systemlayout [left-margin="X"] [right-margin="X"] [top-system-distance="X"]`

```abc
%%systemlayout left-margin="20" right-margin="20" top-system-distance="100"
```

### 5.7 Advanced Staff Layout (`%%stafflayout`)

Defines distance between staves in a multi-staff system, mapped to MusicXML `<staff-layout>`.

**Syntax:** `%%stafflayout [number="N"] [staff-distance="X"]`

```abc
%%stafflayout number="2" staff-distance="65"
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

### 6.3 Note Velocity (`!vel:XX!`)

Applies a specific MIDI velocity (volume) to the single following note. Velocity ranges from 1 to 127. The velocity effect is reset immediately after the note is played.

**Syntax:** `!vel:XX!`

```abc
!vel:30! C !vel:90! D !vel:120! E
```

### 6.4 MIDI Instrument Parameters (`%%midi`)

Configures standard MIDI instrument parameters for playback mapping.

**Syntax:** 
`%%midi program [channel] <program_number>`
`%%midi-bank <bank_number>`
`%%midi-vol <volume_0-127>`
`%%midi-pan <pan>`

```abc
%%midi program 1
%%midi-bank 1
%%midi-vol 100
%%midi-pan -50
```

### 6.5 Playback Navigation

Controls playback flow through structural navigation markers.

**Syntax:**
`%%segno <name>`
`%%dalsegno <name>`
`%%tocoda <name>`
`%%coda <name>`
`%%dacapo`
`%%fine`

```abc
%%segno Segno1
C D E F |
%%tocoda Coda1
G A B c |
%%dalsegno Segno1
%%coda Coda1
c B A G |
```

### 6.6 Pedal Control

Controls piano pedal playback behavior.

**Syntax:**
`%%damper-pedal <yes|no>`
`%%soft-pedal <on|off>`
`%%sostenuto-pedal <yes|no>`

```abc
%%damper-pedal yes
C D E F |
%%damper-pedal no
```

### 6.7 Per-Note Performance Tags (`@{...}`)

Attaches playback nuance to a **single note or chord**, written immediately after the
note (after any duration) with no space. Multiple keys are comma-separated.

**Syntax:** `<note>@{key=value[,key=value]}`

| Key | Range | Meaning |
|-----|-------|---------|
| `v` | 1–127 | MIDI velocity for this note (chords: applied to every chord note) |
| `t` | ±2000 | Timing offset in milliseconds (negative = ahead of the beat) |

```abc
C2@{v=85} D2@{v=110,t=-12} [FAce]4@{v=60,t=18}
```

Unlike `!vel:XX!` (§6.3), a performance tag can carry several parameters at once and is
defined to survive into MusicXML as standard per-note playback attributes:
`v` → `dynamics` (percent-of-forte, forte = velocity 90) and `t` → `attack`
(in divisions at the current tempo). Consumers that do not recognise the attributes
simply ignore them; the engraving is unaffected.

Tags are transparent to validation: beat-count and range checking strip `@{...}`
before analysis, so a tagged score validates identically to an untagged one.
Reference implementation: `abc_perf.py` in
[abcplus-tools](https://github.com/leedale30/abcplus-tools) (modes: `check`,
`compile`, `strip`).

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

## 8. Advanced Instrumentation

### 8.1 Harp Pedals (`%%harp`)

Defines the tuning for harp pedals in standard order (D, C, B, E, F, G, A).
Use `#` for sharp, `b` for flat, and standard notes for natural.

**Syntax:** `%%harp <D> <C> <B> <E> <F> <G> <A>`

```abc
%%harp D# C B E F G A
```

### 8.2 Accordion Registration (`%%accordion`)

Defines accordion registers by specifying the number of reeds in high, middle, and low octave ranges.

**Syntax:** `%%accordion high=N middle=N low=N`

```abc
%%accordion high=1 middle=2 low=1
```

---

## 9. Percussion Mapping

### 9.1 I:percmap Directive

Maps ABC pitches to percussion sounds and noteheads.

```abc
I:percmap ^c' E5 42 x        % Hi-hat
```

---

## 10. Lyric Extensions

### 10.1 Analysis Abbreviations

Lyrics starting with `^` are expanded as analysis annotations.

**Example:** `w: ^CT ^P ^CT`

### 10.2 Melisma Control

Use `_` for melisma or `extend` for structured lyrics.

---

## 11. Source Conventions & Validation

### 11.1 Measure-Block Markers (`% M<n>`)

A comment line of the form `% M<n>` asserts that **the next block of voice lines begins
measure n**. Markers are ordinary ABC comments — converters and renderers ignore them —
but validators use them to verify voice alignment: at each marker, every voice that has
appeared so far must have completed exactly n−1 measures. A skipped or duplicated voice
line is therefore reported **at the measure where the drift first occurs**, instead of as
an opaque bar-count mismatch at the end of the score.

**Syntax:** a comment line containing only `% M` followed by the 1-based measure number.

```abc
% M9
[V:1] c5 d e c | "Bbmin7" e2 d c "Ab7" B2 A G |
[V:2] [F,A,E]2 [F,A,E]2 [F,A,E]2 [F,A,E]2 | [B,DA]2 [B,DA]2 [A,C_G]2 [A,C_G]2 |
% M11
[V:1] "Db7" F2 E2 D2 C B, |
[V:2] [D,F,=B,]2 [D,F,=B,]2 [D,F,=B,]2 [D,F,=B,]2 |
```

Markers are optional; a score without them validates exactly as before. Reference
implementation: `abc_audit.py` in
[abcplus-tools](https://github.com/leedale30/abcplus-tools), which also validates beat
counts per bar, bar-count consistency across voices, empty voices, and chord use in
monophonic instruments.

---

## 12. MusicXML Mapping Reference

### 12.1 Standard ABC 2.1 Elements

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
| `w: (lyrics)` | `<lyric><syllabic><text>` | Mapped in note/lyric |
| Chords (e.g., "C") | `<harmony><root><kind>` | Mapped in harmony element |
| Notes (e.g., C, D, E) | `<note><pitch><step><octave>` | Mapped in note/pitch |
| Rests | `<note><rest>` | Mapped in note/rest |
| Slurs (e.g., ( | `<slur type="start/stop">` | Mapped in note/notations/slur |
| Barlines | `<barline><bar-style>` | Mapped in barline element |

### 12.2 ABC+ Extension Elements

#### 11.2.1 Custom Directives

| ABC+ Element | MusicXML Element | Notes |
|--------------|------------------|-------|
| `%%dir` | `<direction><words>` | Mapped to direction element |
| `%%fx` | `<effect>` | Mapped to direction/direction-type/effect |
| `%%analysis` | `<harmony><function>` | Mapped to harmony/function element |
| `%%game_state` | `<direction><words type="game-state">` | Mapped to direction with type attribute |
| `%%loop` | `<repeat>` | Mapped to barline/repeat element |
| `%%art` | `<articulations>` | Mapped to note/notations/articulations |

#### 11.2.2 Enhanced Decorations

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
| `!ped!` / `!ped-up!` | `<pedal line="no" sign="yes">` | Sustain pedal, asterisk style (`Ped.` … `*`); start/stop |
| `!ped(!` / `!ped)!` | `<pedal line="yes" sign="no">` | Sustain pedal, line/bracket style; start/stop |
| `!ped-change!` | `<pedal type="change" line="yes">` | Re-pedal (lift-and-recatch) notch inside a pedal line |
| `!8va!` / `!8va)!` | `<octave-shift>` | Octave line (also `!8vb!` `!15ma!` `!15mb!` `!22ma!` `!22mb!`); close with `)` |
| `!gliss(!` / `!gliss)!` | `<glissando>` | Glissando slide (spell `gliss`, not `glissando`) |

#### 11.2.3 Layout & Formatting Directives

| ABC+ Element | MusicXML Element | Notes |
|--------------|------------------|-------|
| `%%marker` | `<rehearsal>` | Mapped in direction/direction-type/rehearsal |
| `%%measurenumbering` | `<measure-numbering>` | Mapped in print/measure-numbering |
| `%%vskip` | `<system-distance>` | Mapped in system-distance element |
| `%%sep` | `<system-dividers>` | Mapped in system-layout/system-dividers |
| `%%newpage` | `<print new-page="yes">` | Mapped in print element with new-page attribute |
| `%%newline` | `<print new-system="yes">` | Mapped in print element with new-system attribute |
| `%%measurenb` | `<measure number>` | Mapped in measure element with number attribute |

#### 11.2.4 Playback Control Directives

| ABC+ Element | MusicXML Element | Notes |
|--------------|------------------|-------|
| `%%swing` | `<sound swing="yes"/>` | Mapped in direction/sound with swing attribute |
| `%%swing-off` | `<sound swing="no"/>` | Mapped in direction/sound with swing attribute |
| `%%mute` | `<sound mute="yes"/>` | Mapped in direction/sound with mute attribute |
| `%%mute-off` | `<sound mute="no"/>` | Mapped in direction/sound with mute attribute |
| `%%midi program` | `<midi-program>` | Mapped in midi-instrument element |
| `%%midi-bank` | `<midi-bank>` | Mapped in midi-instrument element |
| `%%midi-vol` | `<volume>` | Mapped in midi-instrument element |
| `%%midi-pan` | `<pan>` | Mapped in midi-instrument element |
| `%%segno` | `<sound segno="name"/>` | Mapped in direction/sound element |
| `%%dalsegno` | `<sound dalsegno="name"/>` | Mapped in direction/sound element |
| `%%tocoda` | `<sound tocoda="name"/>` | Mapped in direction/sound element |
| `%%coda` | `<sound coda="name"/>` | Mapped in direction/sound element |
| `%%dacapo` | `<sound dacapo="yes"/>` | Mapped in direction/sound element |
| `%%fine` | `<sound fine="yes"/>` | Mapped in direction/sound element |
| `%%damper-pedal` | `<sound damper-pedal="yes/no"/>` | Mapped in direction/sound element |
| `%%soft-pedal` | `<sound soft-pedal="yes/no"/>` | Mapped in direction/sound element |
| `%%sostenuto-pedal` | `<sound sostenuto-pedal="yes/no"/>` | Mapped in direction/sound element |

#### 11.2.5 Harmony & Bass Directives

| ABC+ Element | MusicXML Element | Notes |
|--------------|------------------|-------|
| `%%frame` | `<harmony><frame>` | Mapped in harmony/frame element |
| `%%fb` | `<figured-bass><figure>` | Mapped in figured-bass element |

#### 11.2.6 Percussion Mapping

| ABC+ Element | MusicXML Element | Notes |
|--------------|------------------|-------|
| `I:percmap` | `<score-instrument>` and `<midi-instrument>` | Mapped in part-list/score-part/score-instrument and midi-instrument |

#### 11.2.7 Lyric Extensions

| ABC+ Element | MusicXML Element | Notes |
|--------------|------------------|-------|
| `w: ^CT` | `<lyric><text type="analysis">CT</text>` | Mapped in lyric/text with type attribute |
| `melisma*` | `<lyric><syllabic>middle</syllabic>` | Mapped in lyric/syllabic element |

---

## 13. MEI Mapping Reference

### 13.1 Standard ABC 2.1 Elements

| ABC Element | MEI Element | Notes |
|-------------|-------------|-------|
| `T: (title)` | `<title>` | Mapped to title element |
| `C: (composer)` | `<composer>` | Mapped to composer element |
| `A: (arranger)` | `<arranger>` | Mapped to arranger element |
| `O: (lyricist)` | `<lyricist>` | Mapped to lyricist element |
| `G: (copyright)` | `<rights>` | Mapped to rights element |
| `M: (meter)` | `<meter>` | Mapped to meter element |
| `L: (unit note length)` | `<noteLength>` | Mapped to note length element |
| `Q: (tempo)` | `<tempo>` | Mapped to tempo element |
| `K: (key)` | `<keySig>` | Mapped to key signature element |
| `V: (voice)` | `<voice>` | Mapped to voice element |
| `w: (lyrics)` | `<lyric>` | Mapped to lyric element |
| Chords (e.g., "C") | `<harm>` | Mapped to harmony element |
| Notes (e.g., C, D, E) | `<note>` | Mapped to note element |
| Rests | `<rest>` | Mapped to rest element |
| Slurs (e.g., ( | `<slur>` | Mapped to slur element |
| Barlines | `<barLine>` | Mapped to barline element |

### 13.2 ABC+ Extension Elements

#### 12.2.1 Custom Directives

| ABC+ Element | MEI Element | Notes |
|--------------|-------------|-------|
| `%%dir` | `<dir>` | Mapped to direction element |
| `%%fx` | `<effect>` | Mapped to effect element |
| `%%analysis` | `<analysis>` | Mapped to analysis element |
| `%%game_state` | `<annot>` | Mapped to annotation element |
| `%%loop` | `<repeat>` | Mapped to repeat element |
| `%%art` | `<artic>` | Mapped to articulation element |

#### 12.2.2 Enhanced Decorations

| ABC+ Element | MEI Element | Notes |
|--------------|-------------|-------|
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

#### 12.2.3 Layout & Formatting Directives

| ABC+ Element | MEI Element | Notes |
|--------------|-------------|-------|
| `%%marker` | `<label>` | Mapped to label element |
| `%%measurenumbering` | `<measureNumbering>` | Mapped to measure numbering element |
| `%%vskip` | `<space>` | Mapped to space element |
| `%%sep` | `<divider>` | Mapped to divider element |

#### 12.2.4 Playback Control Directives

| ABC+ Element | MEI Element | Notes |
|--------------|-------------|-------|
| `%%swing` | `<tempo swing="yes">` | Mapped to tempo with swing attribute |
| `%%mute` | `<mute>` | Mapped to mute element |

#### 12.2.5 Harmony & Bass Directives

| ABC+ Element | MEI Element | Notes |
|--------------|-------------|-------|
| `%%frame` | `<chordDiagram>` | Mapped to chord diagram element |
| `%%fb` | `<figuredBass>` | Mapped to figured bass element |

#### 12.2.6 Percussion Mapping

| ABC+ Element | MEI Element | Notes |
|--------------|-------------|-------|
| `I:percmap` | `<percussion>` | Mapped to percussion element |

---

## 14. Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.7.0 | 2026-06-13 | Added Pedal, Octave & Glissando line decorations (4.3): `!ped!`/`!ped-up!` (asterisk), `!ped(!`/`!ped)!` (line), `!ped-change!`, `!8va!`-family, `!gliss(!`/`!gliss)!` → real `<pedal>`/`<octave-shift>`/`<glissando>`. Distinguished from the `%%damper-pedal` sound directive (6.6) |
| 1.6.0 | 2026-06-12 | Added per-note performance tags `@{v,t}` (6.7) and Source Conventions & Validation with measure-block markers `% M<n>` (11) |
| 1.5.0 | 2026-04-29 | Added MIDI Instrument Parameters, Playback Navigation, and Pedal Control |
| 1.4.0 | 2026-03-16 | Added MEI mapping reference |
| 1.3.0 | 2026-03-15 | Updated MusicXML mapping reference with comprehensive bidirectional mapping |
| 1.2.0 | 2026-01-17 | Added playback and advanced layout directives |
| 1.1.0 | 2026-01-17 | Added chord frames and figured bass |
| 1.0.0 | 2026-01-16 | Initial specification |

---

## 15. References

- [ABC Notation Standard v2.1](https://abcnotation.com/wiki/abc:standard:v2.1)
- [MusicXML 4.0 Specification](https://www.w3.org/2021/06/musicxml40/)
- [MEI (Music Encoding Initiative) Specification](https://music-encoding.org/)
