# ABC+ Implementation Roadmap

**Status:** Active Development  
**Last Updated:** 2026-01-17

---

## 🎯 Priority 1: Extended Dynamics

| Element | ABC+ Syntax | Status |
|---------|-------------|--------|
| `<fp>` | `!fp!` | ❌ TODO |
| `<sf>` | `!sf!` | ❌ TODO |
| `<sfp>` | `!sfp!` | ❌ TODO |
| `<sfpp>` | `!sfpp!` | ❌ TODO |
| `<sffz>` | `!sffz!` | ❌ TODO |
| `<fz>` | `!fz!` | ❌ TODO |
| `<rf>` | `!rf!` | ❌ TODO |
| `<rfz>` | `!rfz!` | ❌ TODO |
| `<sfzp>` | `!sfzp!` | ❌ TODO |
| `<n>` | `!n!` (niente) | ❌ TODO |
| `<pf>` | `!pf!` | ❌ TODO |
| `<pppp>` | `!pppp!` | ❌ TODO |
| `<ppppp>` | `!ppppp!` | ❌ TODO |
| `<pppppp>` | `!pppppp!` | ❌ TODO |
| `<ffff>` | `!ffff!` | ❌ TODO |
| `<fffff>` | `!fffff!` | ❌ TODO |
| `<ffffff>` | `!ffffff!` | ❌ TODO |

---

## 🎯 Priority 2: Extended Articulations

| Element | ABC+ Syntax | Status |
|---------|-------------|--------|
| `<staccatissimo>` | `!staccatissimo!` | ❌ TODO |
| `<spiccato>` | `!spiccato!` | ❌ TODO |
| `<detached-legato>` | `!detached-legato!` | ❌ TODO |
| `<scoop>` | `!scoop!` | ❌ TODO |
| `<plop>` | `!plop!` | ❌ TODO |
| `<doit>` | `!doit!` | ❌ TODO |
| `<falloff>` | `!falloff!` | ❌ TODO |
| `<caesura>` | `!caesura!` | ❌ TODO |
| `<stress>` | `!stress!` | ❌ TODO |
| `<unstress>` | `!unstress!` | ❌ TODO |
| `<soft-accent>` | `!soft-accent!` | ❌ TODO |

---

## 🎯 Priority 3: Extended Ornaments

| Element | ABC+ Syntax | Status |
|---------|-------------|--------|
| `<delayed-turn>` | `!delayed-turn!` | ❌ TODO |
| `<delayed-inverted-turn>` | `!delayed-inverted-turn!` | ❌ TODO |
| `<vertical-turn>` | `!vertical-turn!` | ❌ TODO |
| `<inverted-vertical-turn>` | `!inverted-vertical-turn!` | ❌ TODO |
| `<shake>` | `!shake!` | ❌ TODO |
| `<schleifer>` | `!schleifer!` | ❌ TODO |
| `<haydn>` | `!haydn!` | ❌ TODO |

---

## 🎯 Priority 4: Technical Notations

| Element | ABC+ Syntax | Status |
|---------|-------------|--------|
| `<hammer-on>` | `!hammer-on!` | ❌ TODO |
| `<pull-off>` | `!pull-off!` | ❌ TODO |
| `<bend>` | `!bend!` | ❌ TODO |
| `<tap>` | `!tap!` | ❌ TODO |
| `<heel>` | `!heel!` | ❌ TODO |
| `<toe>` | `!toe!` | ❌ TODO |
| `<thumb-position>` | `!thumb!` | ❌ TODO |
| `<double-tongue>` | `!double-tongue!` | ❌ TODO |
| `<triple-tongue>` | `!triple-tongue!` | ❌ TODO |
| `<fingernails>` | `!fingernails!` | ❌ TODO |
| `<golpe>` | `!golpe!` | ❌ TODO |
| `<half-muted>` | `!half-muted!` | ❌ TODO |

---

## 🎯 Priority 5: Chord Diagrams

| Element | ABC+ Syntax | Status |
|---------|-------------|--------|
| `<frame>` | `%%frame C x32010` | ❌ TODO |
| `<frame-strings>` | Auto | ❌ TODO |
| `<frame-frets>` | Fret count | ❌ TODO |
| `<first-fret>` | `fret=N` | ❌ TODO |
| `<frame-note>` | Per-string | ❌ TODO |
| `<barre>` | `barre=N` | ❌ TODO |

---

## 🎯 Priority 6: Figured Bass

| Element | ABC+ Syntax | Status |
|---------|-------------|--------|
| `<figured-bass>` | `%%fb 6 4 3` | ❌ TODO |
| `<figure>` | Space-separated | ❌ TODO |
| `<prefix>` | `#6`, `b3` | ❌ TODO |
| `<figure-number>` | Numbers | ❌ TODO |
| `<suffix>` | `6+` | ❌ TODO |
| `<extend>` | `6_` | ❌ TODO |

---

## 🎯 Priority 7: Layout & Formatting

| Element | ABC+ Syntax | Status |
|---------|-------------|--------|
| `<page-layout>` | `%%pagewidth` | ❌ TODO |
| `<system-layout>` | `%%systemsep` | ❌ TODO |
| `<staff-layout>` | `%%staffsep` | ❌ TODO |
| `<measure-numbering>` | `%%barnumbers` | ❌ TODO |
| `<rehearsal>` | Rehearsal marks | ❌ TODO |
| `<print new-page>` | `%%newpage` | ❌ TODO |
| `<print new-system>` | `%%newline` | ❌ TODO |

---

## 🎯 Priority 8: Harp & Accordion

| Element | ABC+ Syntax | Status |
|---------|-------------|--------|
| `<harp-pedals>` | `%%harp D# C B E F G A` | ❌ TODO |
| `<pedal-tuning>` | Per-pedal | ❌ TODO |
| `<accordion-registration>` | `%%accordion` | ❌ TODO |
| `<accordion-high>` | `high=N` | ❌ TODO |
| `<accordion-middle>` | `middle=N` | ❌ TODO |
| `<accordion-low>` | `low=N` | ❌ TODO |

---

## 🎯 Priority 9: Sound & Playback

| Element | ABC+ Syntax | Status |
|---------|-------------|--------|
| `<swing>` | `%%swing 60` | ❌ TODO |
| `<mute>` | `I:MIDI mute` | ❌ TODO |
| `<play>` | Playback control | ❌ TODO |

---

## ⚠️ Needs Fix

| Element | Current Issue |
|---------|---------------|
| `<inverted-turn>` | Mapping incomplete |
| `<harmonic>` | Partial support |
| `<octave-shift>` | 8va lines incomplete |
| `<pedal>` | Start/stop incomplete |
| `<clef-octave-change>` | `treble-8` parsing |
| `%%drummap` | Basic only |
| 3rd+ endings | May have issues |

---

## 🚫 Cannot Implement

| Element | Reason |
|---------|--------|
| `<image>` | No ABC equivalent |
| `<link>` | Digital publishing only |
| `<bookmark>` | Navigation only |
| `<glyph>` | SMuFL-specific |
| `<scordatura>` | Complex tuning display |
| `<eyeglasses>` | Historic notation |
| `<humming>` | Lyric-specific |
| `<laughing>` | Lyric-specific |
| `<listen>`, `<assess>`, `<wait>` | Education tools |
| `<arrow>` | Analysis diagrams |

---

## Contributing

To implement a feature:

1. Pick an item from a priority list
2. Add ABC+ syntax to `SPECIFICATION.md`
3. Implement in `abc2xml/abc2xml.py`
4. Add test case to `examples/`
5. Update this TODO and `CHECKLIST.md`
6. Submit PR
