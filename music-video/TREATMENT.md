# A$$ IN MY FACE — Music Video Treatment

**CAIROS RA ft. DJ KISS** · Draft 01 · 27 Jul 2026
Format: ~3:00, 16:9 master + 9:16 cutdown · Style: cel-shaded crime-comic (GTA loading-screen look)

Rendered version: https://claude.ai/code/artifact/dc56107b-c24c-4b1d-90c9-9ec916ece55e

---

## 1. Tooling

There is no single all-in-one tool that does this video well. The split:

| Role | Tool | Why |
|---|---|---|
| Shots & story (spine) | **LTX Studio** | Script-first. Holds character + palette shot to shot. |
| Beat sync | **Neural Frames** | Reacts to real stems, not global BPM. Takes 10–20 character refs. |
| Character lock | **Dzine** (or OpenArt) | Best at one face across many stills. Bakes the turnarounds. |
| — | ~~HeyGen~~ | Avatar/talking-head/dubbing product. Wrong tool for stylized animation. |

**Content-filter note.** Every tool above runs a filter, and a literal treatment for this title also gets age-gated off YouTube search. GTA's visual language is built on innuendo, not explicitness — shoot scale, shadow, silhouette and reaction. Clears the filters, clears Vevo, funnier. All prompts below are written that way.

## 2. Style bible

Palette: `#14110F` ink · `#EDE6D8` bone · `#E8873A` sunset · `#B8332A` blood · `#D9A441` gold · `#1F4E4A` teal shadow

- **Line** — heavy black outline, constant weight, no taper. Interior detail at 50% weight.
- **Shading** — flat blocking, max two shade steps. No gradients, no AO.
- **Camera** — macro shots are *always* ground-level low angle, wide lens. This single rule sells the scale.
- **Frame rate** — character on 2s (12fps), camera at 24fps. The mismatch reads as "animated," not as AI drift.
- **Grade** — warm haze in highlights, teal in every shadow, grain + 8% halftone over the whole cut.
- **Titles** — loading-screen cards between sections; flat two-tone portrait, heavy condensed caps.
- **Lyrics** — reuse the existing brush type from the Canva lyric build (`i love it / how you / do that`). Hook only, never the verses.

## 3. Cast

Bake both as four-view turnarounds (front / three-quarter / profile / back) before anything else is generated.

**CAIROS — lead**
```
Cel-shaded crime-comic character turnaround, video game cover art style.
Male rapper, mid-20s, tan skin, long dark hair, black aviator sunglasses,
open patterned silk shirt, heavy gold chains and gold bracelets, white sneakers.
Confident open-mouth grin. Heavy black ink outlines, flat saturated colour
blocking, two shade steps, no gradient. Neutral bone background.
Palette: #E8873A / #D9A441 / #1F4E4A / #14110F
```

**DJ KISS — second macro, enters at the bridge**
```
Cel-shaded crime-comic character turnaround, video game cover art style.
Female DJ, mid-20s, confident stance, arms crossed, oversized headphones
around neck, red lip, cropped jacket, high-waist cargo pants, gold hoops.
Same ink weight and flat colour blocking as the Cairos sheet.
Neutral bone background.
```

> **Open:** `cairos_macro.zip` / `female_macro.zip` (Drive, ~60MB each). If these are rigged 3D models the pipeline improves substantially — render true camera moves in Blender, cel-shade pass over the top, and character consistency stops being a problem. Section rewrites around them once contents are confirmed.

## 4. Treatment

Cairos wakes up broke in a Hollywood one-bedroom, hits the boulevard, and grows to three hundred feet. The city's entire police response is a joke at his scale. Then DJ Kiss rises on the horizon — twice his height — and his wanted level stops meaning anything.

The oldest GTA arc there is: a nobody accumulates absurd power, earns a star rating, causes cartoon chaos, and meets the one thing bigger than him. The hook lands hardest at the bridge, when the joke turns on Cairos.

## 5. Shot list

Timecodes are a **3:00 template** — no audio file exists in Drive or Canva yet. Send the WAV/MP3 and these get re-cut to the waveform as a frame-accurate EDL.

| TC | Shot | Camera | Note |
|---|---|---|---|
| 0:00–0:06 | Card 01 — the label | Static, flat 2D | CAIROS RA punches in word by word; FT. DJ KISS small in red. PA logo bottom-right. |
| 0:06–0:12 | Card 02 — the city | Slow push 5% | Two-tone skyline, palms, flat orange sky. Title drips on in the cover's brush face. |
| 0:12–0:20 | Apartment, morning | Locked wide, eye level | Face-down on the sofa in yesterday's shirt, shades on. Eviction notice. Blind bars. |
| 0:20–0:30 | Boulevard walk | Tracking side-on | GTA cutscene grammar. Palms, taco truck, a cop car that doesn't care yet. |
| 0:30–0:40 | The look-up | Low angle, 8mm | First low angle while still normal-sized — so the growth reads as scale, not lens. |
| 0:40–0:56 | **Transformation** | Camera falls away, no cut | One unbroken retreat as he scales. Build in Neural Frames against the riser. |
| 0:56–1:04 | Wanted level: one star | HUD overlay | Star pops top-right on the first hook word. |
| 1:04–1:14 | Sneaker and the squad car | Ground level | Bus-sized sneaker lands beside a cop car; it bounces. Comedy, not gore. |
| 1:14–1:24 | Hook burn-in | Static, type over plate | I LOVE IT / HOW YOU / DO THAT, one line per bar. Only lyrics in the video. |
| 1:24–1:36 | Helicopters | Orbit | Three news choppers circling his head like flies. Three stars. |
| 1:36–1:44 | Freeway wade | High wide | The *only* high angle — wading up the 101 like a creek. Breaking the rule makes it visible. |
| 1:44–1:52 | Billboard | Static insert | Leans on a shoulder-height billboard advertising the single. Grins down the lens. |
| 1:52–2:20 | Full chaos | Rapid cut, 6–10f | Chorus 1 material recut faster and wider. Four stars. Grade pushed hotter. |
| 2:20–2:32 | **Something on the horizon** | Long lens, held | Second silhouette rises behind the hills, twice his height. Four seconds, no cut. |
| 2:32–2:44 | Wanted level clears | HUD | Stars grey out. Choppers leave. He looks up — reverse of the 0:30 shot. The rhyme is the video. |
| 2:44–2:54 | Two of them, one skyline | Locked wide, push out | Both giants over the city at last light. Hook burn-in, final pass. |
| 2:54–3:00 | Curb, dawn | Static wide, hold to black | Normal size on Cahuenga, sharing a water. A cop car rolls past and doesn't stop. |

### Key prompts

**Transformation (0:40)**
```
Cel-shaded crime-comic. Extreme low angle, camera at street level looking up
a colossal man in open silk shirt and gold chains growing to tower over palm
trees and stucco apartment blocks. Tiny cars for scale. Heavy ink outlines,
flat colour blocking, hazy orange sky, deep teal ground shadow, halftone.
16:9, wide lens distortion, dramatic upward perspective
```

**Freeway wade (1:36)**
```
Cel-shaded crime-comic aerial wide. Colossal man wading up a multi-lane
Los Angeles freeway, cars streaming around his ankles, palm-lined embankments,
smog-orange haze. Heavy ink outlines, flat colour blocking, teal shadows.
16:9, high angle, strong graphic perspective lines
```

**Horizon reveal (2:20)**
```
Cel-shaded crime-comic wide. Silhouette of an enormous female figure with
headphones rising behind the Hollywood hills at dusk, dwarfing a second giant
male figure in the foreground. Flat two-tone, heavy ink rim light, deep teal
sky, hot orange horizon band. 16:9, extreme scale contrast, long lens.
```

**Loading card (0:06)**
```
Cel-shaded crime-comic loading screen illustration. Flat two-tone Hollywood
skyline silhouette, palm trees, low stucco buildings, flat orange sunset sky,
no gradient. Heavy ink outline, bold graphic shapes, halftone texture.
16:9, video game cover art composition, negative space upper third for title
```

## 6. Build order

1. **Send the audio** (WAV/MP3 + BPM). Every mark above gets re-timed to the waveform.
2. **Freeze both turnarounds** in Dzine/OpenArt. Do not proceed until Cairos is identical across all four views. Export ≥12 refs per character.
3. **Block the story in LTX Studio** — shot list as script, turnarounds as character refs, draft quality first, upscale only once the cut works.
4. **Build the transformation and both choruses in Neural Frames** against real stems so the scale-up peaks on the downbeat.
5. **Lip-sync hero shots only** — two or three hook close-ups. Full-video lip sync will read uncanny at this style.
6. **Assemble and grade** in Resolve/CapCut. Grain + 8% halftone as the final node so every source blends into one look.
7. **Cut the 9:16.** Shots 05, 08, 13, 14 are already composed for vertical — teaser with no re-render.
