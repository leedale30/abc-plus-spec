# ABC+ to MusicXML Feature Checklist

**Legend:**

- ✅ = Done & Working
- ⚠️ = Done & Not Working / Needs Fix
- ❌ = Not Done (To Implement)
- 🚫 = Can't Do (ABC limitation / Not applicable)

---

## 1. Core Notation

| Feature | MusicXML | ABC+ Syntax | Status |
|---------|----------|-------------|--------|
| Notes | `<note><pitch>` | `C D E F` | ✅ |
| Rests | `<rest>` | `z`, `x` | ✅ |
| Measure rests | `<rest measure="yes">` | `Z` | ✅ |
| Chords | `<chord>` | `[CEG]` | ✅ |
| Dotted notes | `<dot>` | `C3/2` | ✅ |
| Double-dotted | `<dot><dot>` | `C7/4` | ✅ |
| Accidentals | `<accidental>` | `^C`, `_C`, `=C` | ✅ |
| Octaves | `<octave>` | `C,`, `c'` | ✅ |
| Duration | `<duration>`, `<type>` | `C2`, `C/2` | ✅ |
| Stem direction | `<stem>` | Automatic | ✅ |

---

## 2. Key & Time Signatures

| Feature | MusicXML | ABC+ Syntax | Status |
|---------|----------|-------------|--------|
| Major keys | `<key><fifths>` | `K:C`, `K:G` | ✅ |
| Minor keys | `<key><mode>minor` | `K:Am`, `K:Em` | ✅ |
| Modal keys | `<key><mode>` | `K:Dmix`, `K:Ador` | ✅ |
| Time signature | `<time>` | `M:4/4`, `M:6/8` | ✅ |
| Compound time | `<time>` | `M:12/8` | ✅ |
| Cut time | `<time symbol="cut">` | `M:C|` | ✅ |
| Common time | `<time symbol="common">` | `M:C` | ✅ |
| Senza misura | `<senza-misura>` | — | ❌ |
| Key cancel | `<cancel>` | — | ❌ |

---

## 3. Clefs

| Feature | MusicXML | ABC+ Syntax | Status |
|---------|----------|-------------|--------|
| Treble | `<clef><sign>G` | `K:clef=treble` | ✅ |
| Bass | `<clef><sign>F` | `K:clef=bass` | ✅ |
| Alto | `<clef><sign>C<line>3` | `K:clef=alto` | ✅ |
| Tenor | `<clef><sign>C<line>4` | `K:clef=tenor` | ✅ |
| Percussion | `<clef><sign>percussion` | `K:clef=perc` | ✅ |
| TAB | `<clef><sign>TAB` | `K:clef=tab` | ✅ |
| Octave clefs | `<clef-octave-change>` | `K:clef=treble-8` | ⚠️ |
| No clef | `<sign></sign>` | `K:clef=none` | ✅ |

---

## 4. Barlines & Repeats

| Feature | MusicXML | ABC+ Syntax | Status |
|---------|----------|-------------|--------|
| Regular | `<barline>` | `|` | ✅ |
| Double | `<bar-style>light-light` | `||` | ✅ |
| Final | `<bar-style>light-heavy` | `|]` | ✅ |
| Repeat start | `<repeat direction="forward">` | `|:` | ✅ |
| Repeat end | `<repeat direction="backward">` | `:|` | ✅ |
| 1st ending | `<ending number="1">` | `[1` | ✅ |
| 2nd ending | `<ending number="2">` | `[2` | ✅ |
| 3rd+ endings | `<ending number="3">` | `[3` | ⚠️ |
| Dashed barline | `<bar-style>dashed` | `.|` | ✅ |
| Invisible barline | `<bar-style>none` | `[|]` | ✅ |

---

## 5. Articulations

| Feature | MusicXML | ABC+ Syntax | Status |
|---------|----------|-------------|--------|
| Staccato | `<staccato>` | `.C` or `!staccato!` | ✅ |
| Staccatissimo | `<staccatissimo>` | `!staccatissimo!` | ❌ |
| Accent | `<accent>` | `!accent!` | ✅ |
| Strong accent | `<strong-accent>` | `!marcato!` | ✅ |
| Tenuto | `<tenuto>` | `!tenuto!` | ✅ |
| Detached legato | `<detached-legato>` | `!detached-legato!` | ❌ |
| Spiccato | `<spiccato>` | `!spiccato!` | ❌ |
| Scoop | `<scoop>` | `!scoop!` | ❌ |
| Plop | `<plop>` | `!plop!` | ❌ |
| Doit | `<doit>` | `!doit!` | ❌ |
| Falloff | `<falloff>` | `!falloff!` | ❌ |
| Caesura | `<caesura>` | `!caesura!` | ❌ |
| Breath mark | `<breath-mark>` | `!breath!` | ✅ |
| Stress | `<stress>` | `!stress!` | ❌ |
| Unstress | `<unstress>` | `!unstress!` | ❌ |
| Soft accent | `<soft-accent>` | `!soft-accent!` | ❌ |

---

## 6. Ornaments

| Feature | MusicXML | ABC+ Syntax | Status |
|---------|----------|-------------|--------|
| Trill | `<trill-mark>` | `!trill!` or `T` | ✅ |
| Trill line | `<wavy-line>` | `!trill(!`, `!trill)!` | ✅ |
| Mordent | `<mordent>` | `!mordent!` or `M` | ✅ |
| Inverted mordent | `<inverted-mordent>` | `!uppermordent!` or `P` | ✅ |
| Turn | `<turn>` | `!turn!` | ✅ |
| Inverted turn | `<inverted-turn>` | `!invertedturn!` | ⚠️ |
| Delayed turn | `<delayed-turn>` | `!delayed-turn!` | ❌ |
| Delayed inv. turn | `<delayed-inverted-turn>` | — | ❌ |
| Shake | `<shake>` | `!shake!` | ❌ |
| Schleifer | `<schleifer>` | `!schleifer!` | ❌ |
| Tremolo | `<tremolo>` | `!///!` | ✅ |
| Haydn ornament | `<haydn>` | `!haydn!` | ❌ |
| Accidental mark | `<accidental-mark>` | — | ❌ |

---

## 7. Dynamics

| Feature | MusicXML | ABC+ Syntax | Status |
|---------|----------|-------------|--------|
| ppp | `<ppp>` | `!ppp!` | ✅ |
| pp | `<pp>` | `!pp!` | ✅ |
| p | `<p>` | `!p!` | ✅ |
| mp | `<mp>` | `!mp!` | ✅ |
| mf | `<mf>` | `!mf!` | ✅ |
| f | `<f>` | `!f!` | ✅ |
| ff | `<ff>` | `!ff!` | ✅ |
| fff | `<fff>` | `!fff!` | ✅ |
| sfz | `<sfz>` | `!sfz!` | ✅ |
| sfp | `<sfp>` | `!sfp!` | ❌ |
| sfpp | `<sfpp>` | `!sfpp!` | ❌ |
| sffz | `<sffz>` | `!sffz!` | ❌ |
| fp | `<fp>` | `!fp!` | ❌ |
| fz | `<fz>` | `!fz!` | ❌ |
| rf, rfz | `<rf>`, `<rfz>` | `!rf!`, `!rfz!` | ❌ |
| n (niente) | `<n>` | `!n!` | ❌ |
| pf | `<pf>` | `!pf!` | ❌ |
| Crescendo hairpin | `<wedge type="crescendo">` | `!<(!`, `!<)!` | ✅ |
| Diminuendo hairpin | `<wedge type="diminuendo">` | `!>(!`, `!>)!` | ✅ |
| Dashes | `<dashes>` | — | ❌ |

---

## 8. Slurs & Ties

| Feature | MusicXML | ABC+ Syntax | Status |
|---------|----------|-------------|--------|
| Slur | `<slur>` | `(CDE)` | ✅ |
| Dotted slur | `<slur line-type="dotted">` | `.(CDE)` | ✅ |
| Tie | `<tie>`, `<tied>` | `C-C` | ✅ |
| Let ring | — | — | 🚫 |
| Nested slurs | `<slur number="2">` | `((CDE)(FGA))` | ✅ |

---

## 9. Beaming & Tuplets

| Feature | MusicXML | ABC+ Syntax | Status |
|---------|----------|-------------|--------|
| Beam groups | `<beam>` | Automatic | ✅ |
| Beam break | — | Space between notes | ✅ |
| Triplet | `<tuplet>` | `(3CDE` | ✅ |
| Quintuplet | `<time-modification>` | `(5CDEFG` | ✅ |
| Custom tuplet | `<actual-notes>/<normal-notes>` | `(5:4CDEFG` | ✅ |
| Nested tuplets | — | — | ⚠️ |

---

## 10. Grace Notes

| Feature | MusicXML | ABC+ Syntax | Status |
|---------|----------|-------------|--------|
| Grace note | `<grace>` | `{c}C` | ✅ |
| Acciaccatura | `<grace slash="yes">` | `{/c}C` | ✅ |
| Appoggiatura | `<grace>` | `{c}C` | ✅ |
| Grace chord | — | `{[ceg]}C` | ✅ |

---

## 11. Technical Notation

| Feature | MusicXML | ABC+ Syntax | Status |
|---------|----------|-------------|--------|
| Up bow | `<up-bow>` | `!upbow!` or `u` | ✅ |
| Down bow | `<down-bow>` | `!downbow!` or `v` | ✅ |
| Open string | `<open-string>` | `!open!` | ✅ |
| Snap pizz | `<snap-pizzicato>` | `!snap!` | ✅ |
| Fingering | `<fingering>` | `!1!`-`!5!` | ✅ |
| String number | `<string>` | `!1!`-`!6!` (TAB) | ✅ |
| Fret | `<fret>` | Auto-calculated | ✅ |
| Hammer-on | `<hammer-on>` | `!hammer-on!` | ❌ |
| Pull-off | `<pull-off>` | `!pull-off!` | ❌ |
| Bend | `<bend>` | `!bend!` | ❌ |
| Tap | `<tap>` | `!tap!` | ❌ |
| Heel/Toe | `<heel>`, `<toe>` | `!heel!`, `!toe!` | ❌ |
| Harmonic | `<harmonic>` | `!harmonic!` | ⚠️ |
| Double tongue | `<double-tongue>` | `!double-tongue!` | ❌ |
| Triple tongue | `<triple-tongue>` | `!triple-tongue!` | ❌ |
| Stopped | `<stopped>` | `!mute!` | ✅ |

---

## 12. Text & Directions

| Feature | MusicXML | ABC+ Syntax | Status |
|---------|----------|-------------|--------|
| Text above | `<words>` (above) | `"^text"` | ✅ |
| Text below | `<words>` (below) | `"_text"` | ✅ |
| Text left | `<words>` (left) | `"<text"` | ✅ |
| Text right | `<words>` (right) | `">text"` | ✅ |
| Tempo | `<metronome>` | `Q:1/4=120` | ✅ |
| Segno | `<segno>` | `!segno!` | ✅ |
| Coda | `<coda>` | `!coda!` | ✅ |
| D.S. | — | `!D.S.!` | ✅ |
| D.C. | — | `!D.C.!` | ✅ |
| Fine | — | `!fine!` | ⚠️ |
| Rehearsal mark | `<rehearsal>` | — | ❌ |
| Eyeglasses | `<eyeglasses>` | — | 🚫 |
| Pedal | `<pedal>` | `!ped!`, `!ped-up!` | ⚠️ |

---

## 13. Chord Symbols

| Feature | MusicXML | ABC+ Syntax | Status |
|---------|----------|-------------|--------|
| Root | `<root>` | `"C"` | ✅ |
| Kind | `<kind>` | `"Cm"`, `"C7"` | ✅ |
| Bass | `<bass>` | `"C/E"` | ✅ |
| Degree | `<degree>` | `"Cm7b5"` | ✅ |
| Frame (diagram) | `<frame>` | — | ❌ |
| Function | `<function>` | — | ❌ |

---

## 14. Lyrics

| Feature | MusicXML | ABC+ Syntax | Status |
|---------|----------|-------------|--------|
| Syllables | `<syllabic>` | `w: lyr-ics` | ✅ |
| Melisma | `<extend>` | `w: word_` | ✅ |
| Multiple verses | `<lyric number="N">` | Multiple `w:` lines | ✅ |
| Elision | `<elision>` | `w: wo~rd` | ✅ |
| Humming | `<humming>` | — | 🚫 |
| Laughing | `<laughing>` | — | 🚫 |

---

## 15. Multi-Voice & Staff

| Feature | MusicXML | ABC+ Syntax | Status |
|---------|----------|-------------|--------|
| Voices | `<voice>` | `V:1`, `V:2` | ✅ |
| Grand staff | `<staves>` | `%%score {1 2}` | ✅ |
| Bracket group | `<group-symbol>bracket` | `%%score [1 2]` | ✅ |
| Brace group | `<group-symbol>brace` | `%%score {1 2}` | ✅ |
| Voice overlay | `<backup>` | `&` | ✅ |
| Staff assignment | `<staff>` | Auto | ✅ |
| Cue notes | `<cue>` | `!cue!` | ✅ |

---

## 16. Percussion

| Feature | MusicXML | ABC+ Syntax | Status |
|---------|----------|-------------|--------|
| Unpitched | `<unpitched>` | `I:percmap` | ✅ |
| Notehead | `<notehead>` | `I:percmap ... x` | ✅ |
| MIDI mapping | — | `I:percmap ... 42` | ✅ |
| Drummap | — | `%%drummap` | ⚠️ |
| Beater | `<beater>` | — | ❌ |
| Stick | `<stick>` | — | ❌ |

---

## 17. Figured Bass

| Feature | MusicXML | ABC+ Syntax | Status |
|---------|----------|-------------|--------|
| Figured bass | `<figured-bass>` | — | ❌ |
| Figure | `<figure>` | — | ❌ |
| Figure number | `<figure-number>` | — | ❌ |
| Prefix/Suffix | `<prefix>`, `<suffix>` | — | ❌ |
| Extend | `<extend>` | — | ❌ |

---

## 18. Layout & Formatting

| Feature | MusicXML | ABC+ Syntax | Status |
|---------|----------|-------------|--------|
| Page break | `<print new-page>` | `%%newpage` | ❌ |
| System break | `<print new-system>` | `%%newline` | ⚠️ |
| Page layout | `<page-layout>` | `%%pagewidth` | ❌ |
| Staff spacing | `<staff-layout>` | `%%staffsep` | ❌ |
| Measure numbers | `<measure-numbering>` | `%%barnumbers` | ❌ |
| Credits | `<credit>` | — | ❌ |

---

## 19. Sound & Playback

| Feature | MusicXML | ABC+ Syntax | Status |
|---------|----------|-------------|--------|
| Tempo | `<sound tempo>` | `Q:1/4=120` | ✅ |
| Dynamics | `<sound dynamics>` | — | ❌ |
| MIDI program | `<midi-instrument>` | `I:MIDI` | ✅ |
| Swing | `<swing>` | — | ❌ |
| Transpose | `<transpose>` | — | ❌ |

---

## 20. Advanced/Specialized

| Feature | MusicXML | ABC+ Syntax | Status |
|---------|----------|-------------|--------|
| Image | `<image>` | — | 🚫 |
| Link | `<link>` | — | 🚫 |
| Bookmark | `<bookmark>` | — | 🚫 |
| Grouping | `<grouping>` | — | ❌ |
| Feature | `<feature>` | — | ❌ |
| Glyph | `<glyph>` | — | 🚫 |
| Scordatura | `<scordatura>` | — | 🚫 |
| Harp pedals | `<harp-pedals>` | — | ❌ |
| Accordion reg. | `<accordion-registration>` | — | ❌ |

---

## Summary

| Status | Count | Percentage |
|--------|-------|------------|
| ✅ Done & Working | ~95 | ~65% |
| ⚠️ Done, Needs Fix | ~12 | ~8% |
| ❌ Not Done | ~32 | ~22% |
| 🚫 Can't Do | ~8 | ~5% |
| **Total Elements** | ~147 | 100% |

---

## Priority Queue

### High Priority (Common Use)

1. Extended dynamics: `!fp!`, `!sfp!`, `!fz!`
2. Extended articulations: `!staccatissimo!`, `!caesura!`
3. Guitar chord diagrams: `%%frame`
4. Figured bass: `%%fb`

### Medium Priority

5. Technical: `!hammer-on!`, `!pull-off!`, `!bend!`
2. Layout: `%%newpage`, `%%newline`
3. Extended ornaments

### Low Priority

8. Harp/accordion
2. Advanced structure
