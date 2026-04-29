# ABC+ Implementation Roadmap

**Status:** Active Development  
**Last Updated:** 2026-01-17

---

### Priority Implementation Roadmap

1. ✅ **Priority 1: Extended Dynamics**
   - Implemented: `!fp!`, `!sf!`, `!sfp!`, `!sfpp!`, `!sffz!`, `!fz!`, `!rf!`, `!rfz!`, `!sfzp!`, `!n!`, `!pf!`, `!pppp!`...`!ffffff!`.
2. ✅ **Priority 2: Extended Articulations**
   - Implemented: `!staccatissimo!`, `!spiccato!`, `!detached-legato!`, `!scoop!`, `!plop!`, `!doit!`, `!falloff!`, `!caesura!`, `!stress!`, `!unstress!`, `!soft-accent!`.
3. ✅ **Priority 3: Extended Ornaments**
   - Implemented: `!delayed-turn!`, `!delayed-inverted-turn!`, `!vertical-turn!`, `!inverted-vertical-turn!`, `!shake!`, `!schleifer!`, `!haydn!`.
4. ✅ **Priority 4: Technical Notations**
   - Implemented: `!hammer-on!`, `!pull-off!`, `!bend!`, `!tap!`, `!heel!`, `!toe!`, `!thumb-position!`, `!double-tongue!`, `!triple-tongue!`, `!fingernails!`, `!golpe!`, `!half-muted!`.
5. ✅ **Priority 5: Chord Diagrams**
   - Implemented: `%%frame C x32010` mapping to `<frame>`.
6. ✅ **Priority 6: Figured Bass**
   - Implemented: `%%fb 6 4 3` mapping to `<figured-bass>`.
7. ✅ **Priority 7: Layout & Formatting**
   - Implemented: `%%vskip`, `%%sep`, `%%measurenumbering`, `%%marker`.
8. ✅ **Priority 8: Sound & Playback (Part 1)**
   - Implemented: `%%swing`, `%%mute`, `!vel:XX!`.
9. ⏳ **Priority 9: Advanced Inst. (Harp/Accordion)**
   - Planned: `%%harp`, `%%accordion`.
10. ⏳ **Priority 10: Advanced Layout Control**
    - Planned: `%%pagelayout`, `%%systemlayout`, `%%stafflayout`.
11. ⏳ **Priority 11: Advanced Notation Elements**
    - Planned: `!ornament:...!` and `!technical:...!` syntax.
12. ⏳ **Priority 12: Detailed MIDI & Playback**
    - Planned: `%%mididevice`, `%%midiinstrument`, `%%midichannel`.
13. ⏳ **Priority 13: Complex Articulations & Effects**
    - Planned: `!articulation:...!`, `!effect:...!` extended attributes.
14. ⏳ **Priority 14: Advanced Harmony & Chords**
    - Planned: `%%harmony` detailed definitions.

---

## 📋 Comprehensive Checklist

### Extended Dynamics

 | Element | ABC+ Syntax | Status | 
 | --------- | ------------- | -------- | 
 | `<fp>` | `!fp!` | ✅ DONE | 
 | `<sf>` | `!sf!` | ✅ DONE | 
 | `<sfp>` | `!sfp!` | ✅ DONE | 
 | `<sfpp>` | `!sfpp!` | ✅ DONE | 
 | `<sffz>` | `!sffz!` | ✅ DONE | 
 | `<fz>` | `!fz!` | ✅ DONE | 
 | `<rf>` | `!rf!` | ✅ DONE | 
 | `<rfz>` | `!rfz!` | ✅ DONE | 
 | `<sfzp>` | `!sfzp!` | ✅ DONE | 
 | `<n>` | `!n!` | ✅ DONE | 
 | `<pf>` | `!pf!` | ✅ DONE | 
 | `<pppp>` | `!pppp!` | ✅ DONE | 
 | `<ppppp>` | `!ppppp!` | ✅ DONE | 
 | `<pppppp>` | `!pppppp!` | ✅ DONE | 
 | `<ffff>` | `!ffff!` | ✅ DONE | 
 | `<fffff>` | `!fffff!` | ✅ DONE | 
 | `<ffffff>` | `!ffffff!` | ✅ DONE | 

### Extended Articulations

 | Element | ABC+ Syntax | Status | 
 | --------- | ------------- | -------- | 
 | `<staccatissimo>` | `!staccatissimo!` | ✅ DONE | 
 | `<spiccato>` | `!spiccato!` | ✅ DONE | 
 | `<detached-legato>` | `!detached-legato!` | ✅ DONE | 
 | `<scoop>` | `!scoop!` | ✅ DONE | 
 | `<plop>` | `!plop!` | ✅ DONE | 
 | `<doit>` | `!doit!` | ✅ DONE | 
 | `<falloff>` | `!falloff!` | ✅ DONE | 
 | `<caesura>` | `!caesura!` | ✅ DONE | 
 | `<stress>` | `!stress!` | ✅ DONE | 
 | `<unstress>` | `!unstress!` | ✅ DONE | 
 | `<soft-accent>` | `!soft-accent!` | ✅ DONE | 

### Extended Ornaments

 | Element | ABC+ Syntax | Status | 
 | --------- | ------------- | -------- | 
 | `<delayed-turn>` | `!delayed-turn!` | ✅ DONE | 
 | `<delayed-inverted-turn>` | `!delayed-inverted-turn!` | ✅ DONE | 
 | `<vertical-turn>` | `!vertical-turn!` | ✅ DONE | 
 | `<inverted-vertical-turn>` | `!inverted-vertical-turn!` | ✅ DONE | 
 | `<shake>` | `!shake!` | ✅ DONE | 
 | `<schleifer>` | `!schleifer!` | ✅ DONE | 
 | `<haydn>` | `!haydn!` | ✅ DONE | 

### Technical Notations

 | Element | ABC+ Syntax | Status | 
 | --------- | ------------- | -------- | 
 | `<hammer-on>` | `!hammer-on!` | ✅ DONE | 
 | `<pull-off>` | `!pull-off!` | ✅ DONE | 
 | `<bend>` | `!bend!` | ✅ DONE | 
 | `<tap>` | `!tap!` | ✅ DONE | 
 | `<heel>` | `!heel!` | ✅ DONE | 
 | `<toe>` | `!toe!` | ✅ DONE | 
 | `<thumb-position>` | `!thumb!` | ✅ DONE | 
 | `<double-tongue>` | `!double-tongue!` | ✅ DONE | 
 | `<triple-tongue>` | `!triple-tongue!` | ✅ DONE | 
 | `<fingernails>` | `!fingernails!` | ✅ DONE | 
 | `<golpe>` | `!golpe!` | ✅ DONE | 
 | `<half-muted>` | `!half-muted!` | ✅ DONE | 

### Playback Controls

 | Element | ABC+ Syntax | Status | 
 | --------- | ------------- | -------- | 
 | `<swing>` | `%%swing` | ✅ DONE | 
 | `<mute>` | `%%mute` | ✅ DONE | 
 | `<play>` | Playback control | ❌ TODO | 
 | `<first-fret>` | `fret=N` | ✅ DONE | 
 | `<frame-note>` | Per-string | ✅ DONE | 
 | `<barre>` | `barre=N` | ❌ TODO | 

---

## 🎯 Priority 5: Chord Diagrams

 | Element | ABC+ Syntax | Status | 
 | --------- | ------------- | -------- | 
 | `<frame>` | `%%frame C x32010` | ✅ DONE | 
 | `<frame-strings>` | Auto | ✅ DONE | 
 | `<frame-frets>` | Fret count | ✅ DONE | 
 | `<first-fret>` | `fret=N` | ✅ DONE | 
 | `<frame-note>` | Per-string | ✅ DONE | 
 | `<barre>` | `barre=N` | ❌ TODO | 

---

## 🎯 Priority 6: Figured Bass

 | Element | ABC+ Syntax | Status | 
 | --------- | ------------- | -------- | 
 | `<figured-bass>` | `%%fb 6 4 3` | ✅ DONE | 
 | `<figure>` | Space-separated | ✅ DONE | 
 | `<prefix>` | `#6`, `b3` | ✅ DONE | 
 | `<figure-number>` | Numbers | ✅ DONE | 
 | `<suffix>` | `6+` | ✅ DONE | 
 | `<extend>` | `6_` | ❌ TODO | 

---

## 🎯 Priority 7: Layout & Formatting

 | Element | ABC+ Syntax | Status | 
 | --------- | ------------- | -------- | 
 | `<page-layout>` | `%%pagewidth` | ✅ DONE | 
 | `<system-layout>` | `%%vskip` | ✅ DONE | 
 | `<staff-layout>` | `%%staffsep` | ✅ DONE | 
 | `<measure-numbering>` | `%%measurenumbering` | ✅ DONE | 
 | `<rehearsal>` | `%%marker` | ✅ DONE | 
 | `<print new-page>` | `%%newpage` | ✅ DONE | 
 | `<print new-system>` | `%%newline` | ✅ DONE | 
 | `<other-direction>` | `%%sep` | ✅ DONE | 
 | `<system-distance>` | `%%vskip` | ✅ DONE | 

---

## 🎯 Priority 8: Harp & Accordion

 | Element | ABC+ Syntax | Status | 
 | --------- | ------------- | -------- | 
 | `<harp-pedals>` | `%%harp D# C B E F G A` | ❌ TODO | 
 | `<pedal-tuning>` | Per-pedal | ❌ TODO | 
 | `<accordion-registration>` | `%%accordion` | ❌ TODO | 
 | `<accordion-high>` | `high=N` | ❌ TODO | 
 | `<accordion-middle>` | `middle=N` | ❌ TODO | 
 | `<accordion-low>` | `low=N` | ❌ TODO | 

---

## 🎯 Priority 9: Sound & Playback

 | Element | ABC+ Syntax | Status | 
 | --------- | ------------- | -------- | 
 | `<swing>` | `%%swing` | ✅ DONE | 
 | `<mute>` | `%%mute` | ✅ DONE | 
 | `<velocity>` | `!vel:XX!` | ✅ DONE | 
 | `<play>` | Playback control | ❌ TODO | 

---

## 🎯 Priority 10: Advanced Layout Control

 | Element | ABC+ Syntax | Status | 
 | --------- | ------------- | -------- | 
 | `<page-layout>` | `%%pagelayout` | ❌ TODO | 
 | `<system-layout>` | `%%systemlayout` | ❌ TODO | 
 | `<staff-layout>` | `%%stafflayout` | ❌ TODO | 

---

## 🎯 Priority 11: Advanced Notation Elements

 | Element | ABC+ Syntax | Status | 
 | --------- | ------------- | -------- | 
 | `<ornaments>` (Complex) | `!ornament:...!` | ❌ TODO | 
 | `<technical>` (Complex) | `!technical:...!` | ❌ TODO | 

---

## 🎯 Priority 12: Detailed MIDI & Playback

 | Element | ABC+ Syntax | Status | 
 | --------- | ------------- | -------- | 
 | `<midi-device>` | `%%mididevice` | ❌ TODO | 
 | `<midi-instrument>` | `%%midiinstrument` | ❌ TODO | 
 | `<midi-bank>` | `%%midibank` | ❌ TODO | 

---

## 🎯 Priority 13: Complex Articulations & Effects

 | Element | ABC+ Syntax | Status | 
 | --------- | ------------- | -------- | 
 | Articulations (w/ attrs) | `!articulation:...!` | ❌ TODO | 
 | Effects (w/ attrs) | `!effect:...!` | ❌ TODO | 

---

## 🎯 Priority 14: Advanced Harmony & Chords

 | Element | ABC+ Syntax | Status | 
 | --------- | ------------- | -------- | 
 | `<harmony>` (Detailed) | `%%harmony` | ❌ TODO | 

---

## ⚠️ Needs Fix

 | Element | Current Issue | 
 | --------- | --------------- | 
 | 3rd+ endings | May have issues | 

---

## 🚫 Cannot Implement

 | Element | Reason | 
 | --------- | -------- | 
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
