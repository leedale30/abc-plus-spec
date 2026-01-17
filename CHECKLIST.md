# Complete MusicXML 4.0 Element Checklist

**Source:** [W3C MusicXML 4.0 Element Tree](https://www.w3.org/2021/06/musicxml40/musicxml-reference/element-tree/)

**Legend:**

- ✅ = Done & Working
- ⚠️ = Done, Needs Fix
- ❌ = Not Done
- 🚫 = Can't Do (no ABC equivalent / not applicable)

---

## Score Structure

| Element | Status | ABC+ Mapping |
|---------|--------|--------------|
| `<score-partwise>` | ✅ | Root element |
| `<score-timewise>` | 🚫 | Not used |
| `<part>` | ✅ | `V:` voice |
| `<measure>` | ✅ | `|` barline |
| `<work>` | ✅ | Header fields |
| `<movement-number>` | ❌ | — |
| `<movement-title>` | ✅ | `T:` title |

## Identification

| Element | Status | ABC+ Mapping |
|---------|--------|--------------|
| `<identification>` | ✅ | Container |
| `<creator>` | ✅ | `C:` composer |
| `<rights>` | ❌ | — |
| `<encoding>` | ✅ | Auto-generated |
| `<encoder>` | ✅ | Auto |
| `<encoding-date>` | ✅ | Auto |
| `<encoding-description>` | ❌ | — |
| `<software>` | ✅ | "abc2xml" |
| `<supports>` | ✅ | Auto |
| `<source>` | ✅ | `S:` field |
| `<relation>` | ❌ | — |
| `<miscellaneous>` | ❌ | — |
| `<miscellaneous-field>` | ❌ | — |

## Defaults & Layout

| Element | Status | ABC+ Mapping |
|---------|--------|--------------|
| `<defaults>` | ❌ | — |
| `<scaling>` | ❌ | — |
| `<millimeters>` | ❌ | — |
| `<tenths>` | ❌ | — |
| `<page-layout>` | ❌ | `%%pagewidth` |
| `<page-height>` | ❌ | `%%pageheight` |
| `<page-width>` | ❌ | `%%pagewidth` |
| `<page-margins>` | ❌ | — |
| `<left-margin>` | ❌ | `%%leftmargin` |
| `<right-margin>` | ❌ | `%%rightmargin` |
| `<top-margin>` | ❌ | `%%topmargin` |
| `<bottom-margin>` | ❌ | `%%botmargin` |
| `<system-layout>` | ❌ | — |
| `<system-margins>` | ❌ | — |
| `<system-distance>` | ❌ | `%%sysstaffsep` |
| `<top-system-distance>` | ❌ | — |
| `<system-dividers>` | ❌ | — |
| `<left-divider>` | ❌ | — |
| `<right-divider>` | ❌ | — |
| `<staff-layout>` | ❌ | — |
| `<staff-distance>` | ❌ | `%%staffsep` |
| `<appearance>` | ❌ | — |
| `<line-width>` | ❌ | — |
| `<note-size>` | ❌ | — |
| `<distance>` | ❌ | — |
| `<glyph>` | 🚫 | SMuFL glyphs |
| `<other-appearance>` | ❌ | — |
| `<music-font>` | ❌ | — |
| `<word-font>` | ❌ | — |
| `<lyric-font>` | ❌ | — |
| `<lyric-language>` | ❌ | — |
| `<concert-score>` | 🚫 | — |

## Credit

| Element | Status | ABC+ Mapping |
|---------|--------|--------------|
| `<credit>` | ❌ | — |
| `<credit-type>` | ❌ | — |
| `<credit-image>` | 🚫 | — |
| `<credit-symbol>` | ❌ | — |
| `<credit-words>` | ❌ | — |
| `<link>` | 🚫 | — |
| `<bookmark>` | 🚫 | — |

## Part List

| Element | Status | ABC+ Mapping |
|---------|--------|--------------|
| `<part-list>` | ✅ | Container |
| `<part-group>` | ✅ | `%%score` |
| `<group-name>` | ✅ | Voice name |
| `<group-name-display>` | ❌ | — |
| `<group-abbreviation>` | ❌ | — |
| `<group-abbreviation-display>` | ❌ | — |
| `<group-symbol>` | ✅ | `{` `}` `[` `]` |
| `<group-barline>` | ❌ | — |
| `<group-time>` | ❌ | — |
| `<score-part>` | ✅ | Voice definition |
| `<part-name>` | ✅ | Voice name |
| `<part-name-display>` | ❌ | — |
| `<part-abbreviation>` | ❌ | — |
| `<part-abbreviation-display>` | ❌ | — |
| `<group>` | ❌ | — |
| `<score-instrument>` | ✅ | `I:MIDI` |
| `<instrument-name>` | ✅ | MIDI program |
| `<instrument-abbreviation>` | ❌ | — |
| `<instrument-sound>` | ❌ | — |
| `<solo>` | ❌ | — |
| `<ensemble>` | ❌ | — |
| `<virtual-instrument>` | ❌ | — |
| `<virtual-library>` | ❌ | — |
| `<virtual-name>` | ❌ | — |
| `<player>` | ❌ | — |
| `<player-name>` | ❌ | — |
| `<midi-device>` | ✅ | `I:MIDI` |
| `<midi-instrument>` | ✅ | `I:MIDI` |
| `<midi-channel>` | ✅ | Channel |
| `<midi-name>` | ❌ | — |
| `<midi-bank>` | ❌ | — |
| `<midi-program>` | ✅ | Program |
| `<midi-unpitched>` | ✅ | `I:percmap` |
| `<volume>` | ✅ | Volume |
| `<pan>` | ✅ | Pan |
| `<elevation>` | ❌ | — |

## Attributes

| Element | Status | ABC+ Mapping |
|---------|--------|--------------|
| `<attributes>` | ✅ | Container |
| `<divisions>` | ✅ | Auto-calculated |
| `<key>` | ✅ | `K:` |
| `<fifths>` | ✅ | Key signature |
| `<mode>` | ✅ | `maj`, `min`, `mix`, etc. |
| `<cancel>` | ❌ | — |
| `<key-step>` | ❌ | Non-traditional keys |
| `<key-alter>` | ❌ | Non-traditional keys |
| `<key-accidental>` | ❌ | — |
| `<key-octave>` | ❌ | — |
| `<time>` | ✅ | `M:` |
| `<beats>` | ✅ | Numerator |
| `<beat-type>` | ✅ | Denominator |
| `<interchangeable>` | ❌ | — |
| `<time-relation>` | ❌ | — |
| `<senza-misura>` | ❌ | Free time |
| `<staves>` | ✅ | Grand staff |
| `<part-symbol>` | ❌ | — |
| `<instruments>` | ❌ | — |
| `<clef>` | ✅ | `clef=` |
| `<sign>` | ✅ | G, F, C, percussion, TAB |
| `<line>` | ✅ | Clef line |
| `<clef-octave-change>` | ⚠️ | `clef=treble-8` |
| `<staff-details>` | ❌ | — |
| `<staff-type>` | ❌ | — |
| `<staff-lines>` | ❌ | — |
| `<staff-tuning>` | ✅ | `I:tuning` |
| `<tuning-step>` | ✅ | — |
| `<tuning-alter>` | ✅ | — |
| `<tuning-octave>` | ✅ | — |
| `<capo>` | ✅ | `I:capo` |
| `<staff-size>` | ❌ | — |
| `<line-detail>` | ❌ | — |
| `<transpose>` | ✅ | — |
| `<chromatic>` | ✅ | — |
| `<diatonic>` | ✅ | — |
| `<octave-change>` | ✅ | — |
| `<double>` | ❌ | — |
| `<for-part>` | ❌ | — |
| `<part-clef>` | ❌ | — |
| `<part-transpose>` | ❌ | — |
| `<directive>` | ❌ | — |
| `<measure-style>` | ❌ | — |
| `<multiple-rest>` | ✅ | `Z` |
| `<measure-repeat>` | ❌ | — |
| `<beat-repeat>` | ❌ | — |
| `<slash>` | ❌ | — |
| `<slash-type>` | ❌ | — |
| `<slash-dot>` | ❌ | — |
| `<except-voice>` | ❌ | — |

## Note

| Element | Status | ABC+ Mapping |
|---------|--------|--------------|
| `<note>` | ✅ | `C D E F G A B` |
| `<grace>` | ✅ | `{notes}` |
| `<chord>` | ✅ | `[CEG]` |
| `<pitch>` | ✅ | Note letter |
| `<step>` | ✅ | C-B |
| `<alter>` | ✅ | `^` `_` `=` |
| `<octave>` | ✅ | `,` `'` |
| `<unpitched>` | ✅ | `I:percmap` |
| `<display-step>` | ✅ | Percussion |
| `<display-octave>` | ✅ | Percussion |
| `<rest>` | ✅ | `z` `x` `Z` |
| `<duration>` | ✅ | Note length |
| `<tie>` | ✅ | `-` |
| `<cue>` | ✅ | `!cue!` |
| `<instrument>` | ✅ | — |
| `<footnote>` | ❌ | — |
| `<level>` | ❌ | — |
| `<voice>` | ✅ | `V:` |
| `<type>` | ✅ | Note type |
| `<dot>` | ✅ | Dotted notes |
| `<accidental>` | ✅ | `^` `_` `=` |
| `<time-modification>` | ✅ | Tuplets `(3` |
| `<actual-notes>` | ✅ | — |
| `<normal-notes>` | ✅ | — |
| `<normal-type>` | ✅ | — |
| `<normal-dot>` | ❌ | — |
| `<stem>` | ✅ | Auto |
| `<notehead>` | ✅ | `I:percmap` |
| `<notehead-text>` | ❌ | — |
| `<staff>` | ✅ | Grand staff |
| `<beam>` | ✅ | Auto |
| `<notations>` | ✅ | Container |
| `<lyric>` | ✅ | `w:` |
| `<syllabic>` | ✅ | `-` |
| `<text>` | ✅ | Lyric text |
| `<elision>` | ✅ | `~` |
| `<extend>` | ✅ | `_` melisma |
| `<laughing>` | 🚫 | — |
| `<humming>` | 🚫 | — |
| `<end-line>` | ❌ | — |
| `<end-paragraph>` | ❌ | — |
| `<play>` | ❌ | — |
| `<ipa>` | 🚫 | — |
| `<mute>` | ❌ | — |
| `<semi-pitched>` | ❌ | — |
| `<other-play>` | ❌ | — |
| `<listen>` | 🚫 | — |
| `<assess>` | 🚫 | — |
| `<wait>` | 🚫 | — |
| `<other-listen>` | 🚫 | — |

## Notations

| Element | Status | ABC+ Mapping |
|---------|--------|--------------|
| `<notations>` | ✅ | Container |
| `<tied>` | ✅ | `-` tie |
| `<slur>` | ✅ | `()` |
| `<tuplet>` | ✅ | `(3` etc. |
| `<tuplet-actual>` | ✅ | — |
| `<tuplet-normal>` | ✅ | — |
| `<tuplet-number>` | ✅ | — |
| `<tuplet-type>` | ✅ | — |
| `<tuplet-dot>` | ❌ | — |
| `<glissando>` | ✅ | `!slide!` |
| `<slide>` | ✅ | `!slide!` |
| `<arpeggiate>` | ✅ | `!arpeggio!` |
| `<non-arpeggiate>` | ❌ | — |
| `<accidental-mark>` | ❌ | — |
| `<fermata>` | ✅ | `H` or `!fermata!` |
| `<other-notation>` | ❌ | — |

## Ornaments

| Element | Status | ABC+ Mapping |
|---------|--------|--------------|
| `<ornaments>` | ✅ | Container |
| `<trill-mark>` | ✅ | `T` or `!trill!` |
| `<turn>` | ✅ | `!turn!` |
| `<delayed-turn>` | ❌ | `!delayed-turn!` |
| `<inverted-turn>` | ⚠️ | `!invertedturn!` |
| `<delayed-inverted-turn>` | ❌ | — |
| `<vertical-turn>` | ❌ | — |
| `<inverted-vertical-turn>` | ❌ | — |
| `<shake>` | ❌ | `!shake!` |
| `<wavy-line>` | ✅ | `!trill(!` `!trill)!` |
| `<mordent>` | ✅ | `M` or `!mordent!` |
| `<inverted-mordent>` | ✅ | `P` or `!uppermordent!` |
| `<schleifer>` | ❌ | `!schleifer!` |
| `<tremolo>` | ✅ | `!///!` |
| `<haydn>` | ❌ | `!haydn!` |
| `<other-ornament>` | ❌ | — |

## Articulations

| Element | Status | ABC+ Mapping |
|---------|--------|--------------|
| `<articulations>` | ✅ | Container |
| `<accent>` | ✅ | `!accent!` |
| `<strong-accent>` | ✅ | `!marcato!` |
| `<staccato>` | ✅ | `.` or `!staccato!` |
| `<staccatissimo>` | ❌ | `!staccatissimo!` |
| `<spiccato>` | ❌ | `!spiccato!` |
| `<tenuto>` | ✅ | `!tenuto!` |
| `<detached-legato>` | ❌ | `!detached-legato!` |
| `<scoop>` | ❌ | `!scoop!` |
| `<plop>` | ❌ | `!plop!` |
| `<doit>` | ❌ | `!doit!` |
| `<falloff>` | ❌ | `!falloff!` |
| `<breath-mark>` | ✅ | `!breath!` |
| `<caesura>` | ❌ | `!caesura!` |
| `<stress>` | ❌ | `!stress!` |
| `<unstress>` | ❌ | `!unstress!` |
| `<soft-accent>` | ❌ | `!soft-accent!` |
| `<other-articulation>` | ✅ | — |

## Technical

| Element | Status | ABC+ Mapping |
|---------|--------|--------------|
| `<technical>` | ✅ | Container |
| `<up-bow>` | ✅ | `u` or `!upbow!` |
| `<down-bow>` | ✅ | `v` or `!downbow!` |
| `<harmonic>` | ⚠️ | `!harmonic!` |
| `<natural>` | ⚠️ | — |
| `<artificial>` | ❌ | — |
| `<base-pitch>` | ❌ | — |
| `<touching-pitch>` | ❌ | — |
| `<sounding-pitch>` | ❌ | — |
| `<open-string>` | ✅ | `!open!` |
| `<thumb-position>` | ❌ | `!thumb!` |
| `<fingering>` | ✅ | `!1!` - `!5!` |
| `<pluck>` | ❌ | — |
| `<double-tongue>` | ❌ | `!double-tongue!` |
| `<triple-tongue>` | ❌ | `!triple-tongue!` |
| `<stopped>` | ✅ | `!mute!` |
| `<snap-pizzicato>` | ✅ | `!snap!` |
| `<fret>` | ✅ | TAB auto |
| `<string>` | ✅ | `!1!` - `!6!` |
| `<hammer-on>` | ❌ | `!hammer-on!` |
| `<pull-off>` | ❌ | `!pull-off!` |
| `<bend>` | ❌ | `!bend!` |
| `<bend-alter>` | ❌ | — |
| `<pre-bend>` | ❌ | — |
| `<release>` | ❌ | — |
| `<with-bar>` | ❌ | — |
| `<tap>` | ❌ | `!tap!` |
| `<heel>` | ❌ | `!heel!` |
| `<toe>` | ❌ | `!toe!` |
| `<fingernails>` | ❌ | `!fingernails!` |
| `<hole>` | ❌ | Woodwind |
| `<hole-type>` | ❌ | — |
| `<hole-closed>` | ❌ | — |
| `<hole-shape>` | ❌ | — |
| `<arrow>` | 🚫 | Analysis |
| `<arrow-direction>` | 🚫 | — |
| `<arrow-style>` | 🚫 | — |
| `<arrowhead>` | 🚫 | — |
| `<circular-arrow>` | 🚫 | — |
| `<handbell>` | ❌ | `!handbell!` |
| `<brass-bend>` | ❌ | — |
| `<flip>` | ❌ | — |
| `<smear>` | ❌ | — |
| `<open>` | ❌ | — |
| `<half-muted>` | ❌ | `!half-muted!` |
| `<harmon-mute>` | ❌ | — |
| `<harmon-closed>` | ❌ | — |
| `<golpe>` | ❌ | `!golpe!` |
| `<other-technical>` | ❌ | — |

## Dynamics

| Element | Status | ABC+ Mapping |
|---------|--------|--------------|
| `<dynamics>` | ✅ | Container |
| `<p>` | ✅ | `!p!` |
| `<pp>` | ✅ | `!pp!` |
| `<ppp>` | ✅ | `!ppp!` |
| `<pppp>` | ❌ | `!pppp!` |
| `<ppppp>` | ❌ | `!ppppp!` |
| `<pppppp>` | ❌ | `!pppppp!` |
| `<f>` | ✅ | `!f!` |
| `<ff>` | ✅ | `!ff!` |
| `<fff>` | ✅ | `!fff!` |
| `<ffff>` | ❌ | `!ffff!` |
| `<fffff>` | ❌ | `!fffff!` |
| `<ffffff>` | ❌ | `!ffffff!` |
| `<mp>` | ✅ | `!mp!` |
| `<mf>` | ✅ | `!mf!` |
| `<sf>` | ❌ | `!sf!` |
| `<sfp>` | ❌ | `!sfp!` |
| `<sfpp>` | ❌ | `!sfpp!` |
| `<fp>` | ❌ | `!fp!` |
| `<rf>` | ❌ | `!rf!` |
| `<rfz>` | ❌ | `!rfz!` |
| `<sfz>` | ✅ | `!sfz!` |
| `<sffz>` | ❌ | `!sffz!` |
| `<fz>` | ❌ | `!fz!` |
| `<n>` | ❌ | `!n!` (niente) |
| `<pf>` | ❌ | `!pf!` |
| `<sfzp>` | ❌ | `!sfzp!` |
| `<other-dynamics>` | ❌ | — |

## Direction

| Element | Status | ABC+ Mapping |
|---------|--------|--------------|
| `<direction>` | ✅ | Container |
| `<direction-type>` | ✅ | Container |
| `<rehearsal>` | ❌ | — |
| `<segno>` | ✅ | `!segno!` |
| `<coda>` | ✅ | `!coda!` |
| `<words>` | ✅ | `"^text"` |
| `<symbol>` | ❌ | — |
| `<wedge>` | ✅ | `!<(!` `!>(!` |
| `<dashes>` | ❌ | — |
| `<bracket>` | ❌ | — |
| `<pedal>` | ⚠️ | `!ped!` |
| `<metronome>` | ✅ | `Q:` |
| `<beat-unit>` | ✅ | — |
| `<beat-unit-dot>` | ✅ | — |
| `<beat-unit-tied>` | ❌ | — |
| `<per-minute>` | ✅ | — |
| `<metronome-note>` | ❌ | — |
| `<metronome-relation>` | ❌ | — |
| `<metronome-arrows>` | ❌ | — |
| `<metronome-beam>` | ❌ | — |
| `<metronome-dot>` | ❌ | — |
| `<metronome-tied>` | ❌ | — |
| `<metronome-tuplet>` | ❌ | — |
| `<metronome-type>` | ❌ | — |
| `<octave-shift>` | ⚠️ | `8va` |
| `<harp-pedals>` | ❌ | `%%harp` |
| `<pedal-tuning>` | ❌ | — |
| `<pedal-step>` | ❌ | — |
| `<pedal-alter>` | ❌ | — |
| `<damp>` | ❌ | — |
| `<damp-all>` | ❌ | — |
| `<eyeglasses>` | 🚫 | — |
| `<string-mute>` | ❌ | — |
| `<scordatura>` | 🚫 | — |
| `<accord>` | 🚫 | — |
| `<image>` | 🚫 | — |
| `<principal-voice>` | ❌ | — |
| `<percussion>` | ✅ | Container |
| `<glass>` | ❌ | — |
| `<metal>` | ❌ | — |
| `<wood>` | ❌ | — |
| `<pitched>` | ❌ | — |
| `<membrane>` | ❌ | — |
| `<effect>` | ❌ | — |
| `<timpani>` | ❌ | — |
| `<beater>` | ❌ | — |
| `<stick>` | ❌ | — |
| `<stick-location>` | ❌ | — |
| `<stick-material>` | ❌ | — |
| `<stick-type>` | ❌ | — |
| `<other-percussion>` | ❌ | — |
| `<other-direction>` | ✅ | — |
| `<accordion-registration>` | ❌ | `%%accordion` |
| `<accordion-high>` | ❌ | — |
| `<accordion-middle>` | ❌ | — |
| `<accordion-low>` | ❌ | — |
| `<staff-divide>` | ❌ | — |
| `<offset>` | ❌ | — |
| `<sound>` | ✅ | Partially |
| `<swing>` | ❌ | `%%swing` |
| `<swing-type>` | ❌ | — |
| `<swing-style>` | ❌ | — |
| `<first>` | ❌ | — |
| `<second>` | ❌ | — |
| `<straight>` | ❌ | — |
| `<instrument-change>` | ❌ | — |
| `<midi-device>` | ✅ | — |
| `<midi-instrument>` | ✅ | — |
| `<play>` | ❌ | — |
| `<listening>` | 🚫 | — |
| `<other-listening>` | 🚫 | — |

## Harmony

| Element | Status | ABC+ Mapping |
|---------|--------|--------------|
| `<harmony>` | ✅ | `"Cm7"` |
| `<root>` | ✅ | Root note |
| `<root-step>` | ✅ | — |
| `<root-alter>` | ✅ | — |
| `<function>` | ❌ | — |
| `<numeral>` | ❌ | — |
| `<numeral-root>` | ❌ | — |
| `<numeral-alter>` | ❌ | — |
| `<numeral-key>` | ❌ | — |
| `<numeral-fifths>` | ❌ | — |
| `<numeral-mode>` | ❌ | — |
| `<kind>` | ✅ | Chord type |
| `<inversion>` | ❌ | — |
| `<bass>` | ✅ | `/E` slash |
| `<bass-step>` | ✅ | — |
| `<bass-alter>` | ✅ | — |
| `<bass-separator>` | ❌ | — |
| `<degree>` | ✅ | Extensions |
| `<degree-value>` | ✅ | — |
| `<degree-alter>` | ✅ | — |
| `<degree-type>` | ✅ | — |
| `<frame>` | ❌ | `%%frame` |
| `<frame-strings>` | ❌ | — |
| `<frame-frets>` | ❌ | — |
| `<first-fret>` | ❌ | — |
| `<frame-note>` | ❌ | — |
| `<barre>` | ❌ | — |
| `<staff>` | ✅ | — |
| `<offset>` | ❌ | — |

## Figured Bass

| Element | Status | ABC+ Mapping |
|---------|--------|--------------|
| `<figured-bass>` | ❌ | `%%fb` |
| `<figure>` | ❌ | — |
| `<prefix>` | ❌ | — |
| `<figure-number>` | ❌ | — |
| `<suffix>` | ❌ | — |
| `<extend>` | ❌ | — |

## Barline

| Element | Status | ABC+ Mapping |
|---------|--------|--------------|
| `<barline>` | ✅ | `|` `||` `|]` |
| `<bar-style>` | ✅ | Various |
| `<wavy-line>` | ✅ | — |
| `<segno>` | ✅ | `!segno!` |
| `<coda>` | ✅ | `!coda!` |
| `<fermata>` | ✅ | — |
| `<ending>` | ✅ | `[1` `[2` |
| `<repeat>` | ✅ | `|:` `:|` |

## Print

| Element | Status | ABC+ Mapping |
|---------|--------|--------------|
| `<print>` | ⚠️ | — |
| `<page-layout>` | ❌ | — |
| `<system-layout>` | ❌ | — |
| `<staff-layout>` | ❌ | — |
| `<measure-layout>` | ❌ | — |
| `<measure-numbering>` | ❌ | `%%barnumbers` |
| `<part-name-display>` | ❌ | — |
| `<part-abbreviation-display>` | ❌ | — |

## Grouping

| Element | Status | ABC+ Mapping |
|---------|--------|--------------|
| `<grouping>` | ❌ | — |
| `<feature>` | ❌ | — |

## Backup/Forward

| Element | Status | ABC+ Mapping |
|---------|--------|--------------|
| `<backup>` | ✅ | `&` overlay |
| `<forward>` | ✅ | — |

---

## Summary

| Status | Count | Percentage |
|--------|-------|------------|
| ✅ Done & Working | ~125 | ~45% |
| ⚠️ Needs Fix | ~10 | ~4% |
| ❌ Not Done | ~115 | ~42% |
| 🚫 Can't Do | ~25 | ~9% |
| **Total** | ~275 | 100% |

---

## Priority Implementation Queue

### High Priority (Common Use)

1. Extended dynamics: `<fp>`, `<sfp>`, `<fz>`, `<sf>`, `<sffz>`, `<sfzp>`
2. Extended articulations: `<staccatissimo>`, `<caesura>`, `<doit>`, `<falloff>`
3. Guitar chord diagrams: `<frame>`, `<frame-note>`, `<barre>`
4. Rehearsal marks: `<rehearsal>`

### Medium Priority

5. Figured bass: `<figured-bass>`, `<figure>`
2. Technical: `<hammer-on>`, `<pull-off>`, `<bend>`, `<tap>`
3. Layout: `<page-layout>`, `<system-layout>`, `<measure-numbering>`
4. Extended ornaments: `<delayed-turn>`, `<shake>`, `<schleifer>`

### Low Priority

9. Harp/Accordion: `<harp-pedals>`, `<accordion-registration>`
2. Playback: `<swing>`, `<mute>`, `<play>`
