# HANDOFF — "A$$ IN MY FACE" music video

Paste this whole file into a new Claude session to bring it up to speed. It is self-contained.

---

## Who and what

- **Artist:** CAIROS RA (George "Cairos" Heinen), Hollywood-based.
- **Track:** *A$$ IN MY FACE* — CAIROS RA ft. DJ KISS. Explicit, Parental Advisory.
- **Hook:** "I love it how you do that."
- **Goal:** a full music video, GTA animation style, with Cairos as the lead character.
- **Second lead:** DJ KISS, a female character who appears late in the video.

## Where the existing assets live

| Asset | Location |
|---|---|
| Cover art | Canva design `DAHMf3h1N6g`, titled "CAIROS & DJ KISS" |
| Lyric video (already built) | Canva design `DAHQddfa78c`, titled "i love it" — 3 pages, 1344×1728, heavy black brush lettering on white: "i love it / how you / do that" |
| Character asset archives | Google Drive folder "Ass in my face", id `1dzXAT7B4Tj5YnMROArzv7PSl7cLuMjwS` — contains `cairos_macro.zip` (57MB) and `female_macro.zip` (64MB) |
| Treatment + storyboard | https://claude.ai/code/artifact/dc56107b-c24c-4b1d-90c9-9ec916ece55e |
| Repo copy | `music-video/TREATMENT.md` on branch `claude/music-video-ai-generation-qcbhle`, draft PR https://github.com/thekisher/Profitable_Results/pull/1 |

**"macro" means macro-scale / giant.** The video is built around Cairos growing to ~300 feet tall.

## Connected tools

Airtable, Canva, Coupler.io, Google Drive, Hugging Face. Gmail and Google Calendar are installed but switched off. **No video-generation tool is connected** — Hugging Face image spaces are the only generative capability, and they run on a free GPU quota that exhausts after a few images and resets in ~3 hours.

## Tool decision (this was a specific question the artist asked)

There is no single all-in-one tool that does this video well. Recommended split:

- **LTX Studio** — the spine. Script-first: you write a shot description and it builds a lit, camera-tracked shot, holding character and palette shot to shot. This video is narrative, so this carries it.
- **Neural Frames** — beat sync. The only one of these that reacts to actual audio stems rather than a global BPM. Use it for the transformation and the choruses.
- **Dzine** (or OpenArt) — character lock. Best at holding one face across many stills. Bake the turnarounds here first; everything else references them.
- **HeyGen — wrong tool.** It is an avatar / talking-head / dubbing product. It will not do stylized animation.

**Content-filter strategy, important:** every tool above runs a content filter, and a literal treatment for this title also gets age-gated off YouTube search, which would hurt the release. GTA's visual language is built on innuendo, not explicitness. All prompts are written around scale, silhouette, shadow and reaction. This clears the filters, clears Vevo, and is funnier. Keep writing them that way.

## Style bible

Cel-shaded crime-comic — the loading-screen / box-art look, **not** GTA V photoreal. Matches the graphic punch of the cover and is much cheaper to keep consistent across 40 shots.

Palette: `#14110F` ink · `#EDE6D8` bone · `#E8873A` sunset · `#B8332A` blood · `#D9A441` gold · `#1F4E4A` teal shadow

- **Line** — heavy black outline, constant weight, no taper. Interior detail at 50% weight.
- **Shading** — flat blocking, max two shade steps. No gradients, no ambient occlusion.
- **Camera** — macro shots are *always* ground-level low angle, wide lens. This single rule is what sells the scale.
- **Frame rate** — character animation on 2s (12fps), camera moves at 24fps. The mismatch reads as "animated" rather than as AI drift.
- **Grade** — warm haze in highlights, teal pushed into every shadow, grain + 8% halftone over the whole cut.
- **Titles** — loading-screen cards between sections; flat two-tone portrait, heavy condensed caps.
- **Lyrics on screen** — reuse the existing brush type from the Canva lyric build. Hook only, never the verses.

## Story

Cairos wakes up broke in a Hollywood one-bedroom, hits the boulevard, and grows to three hundred feet. The city's entire police response is a joke at his scale — wanted stars stack up, choppers circle his head like flies. Then DJ Kiss rises on the horizon, twice his height, and his wanted level stops meaning anything. Last chorus: the two of them over the skyline at sunset. Outro: normal size, dawn, sitting on a curb.

Structure: 16 shots across 9 sequences. Full shot list with timecodes and per-shot camera notes is in the artifact and in `TREATMENT.md`.

## Image generation — what has actually been learned

Generated on Hugging Face `Z-Image-Turbo`. Two real findings:

**1. The model drifts to chibi/mascot proportions by default.** First attempt came out squat and big-headed — wrong register entirely. The fix, keep these in every character prompt:

```
realistic athletic human proportions, eight heads tall,
NOT chibi, NOT cartoon mascot proportions, NOT big-headed
```

Also swap "cel-shaded crime-comic" for `gritty urban crime graphic novel illustration, screen-printed video game cover art` — that phrasing lands the look far more reliably.

**2. Seeds:** `3318` produced correct results twice. `7412` produced the chibi failure. Start from `3318`.

**Working Cairos prompt:**
```
Gritty urban crime graphic novel illustration, screen-printed video game cover
art. Full-body standing portrait of an adult male rapper, realistic athletic
human proportions, eight heads tall, tall and lean, NOT chibi, NOT cartoon
mascot proportions, NOT big-headed. Mid-20s, tan skin, long dark hair, black
aviator sunglasses, open patterned silk shirt, heavy gold chains, black jeans,
white sneakers. Confident smirk, three-quarter hero stance. Heavy black ink
outlines, flat saturated colour blocking, two shade steps only, no gradient,
halftone texture. Flat bone-cream background. Sunset orange, gold, deep teal
shadows, near-black ink.
```

**Working macro hero shot (this one came out genuinely usable):**
```
Gritty urban crime graphic novel illustration, screen-printed video game cover
art. Extreme low angle from street level looking steeply up at a colossal
three-hundred-foot-tall man towering over a sun-bleached Los Angeles boulevard.
He wears an open patterned silk shirt, heavy gold chains, black jeans, white
sneakers, black aviator sunglasses. Realistic adult human proportions. Palm
trees and low stucco apartment blocks reach only to his knee. Tiny cars and a
police helicopter for scale. Heavy black ink outlines, flat saturated colour
blocking, two shade steps, no gradient, halftone texture. Hazy orange sunset
sky, deep teal ground shadows, bone highlights. Wide-angle lens distortion,
dramatic upward perspective.
```

**DJ KISS (not yet generated):**
```
Gritty urban crime graphic novel illustration, screen-printed video game cover
art. Full-body standing portrait of an adult female DJ, realistic athletic
human proportions, eight heads tall, NOT chibi, NOT cartoon mascot proportions.
Mid-20s, confident stance, arms crossed, oversized headphones around neck, red
lip, cropped jacket, high-waist cargo pants, gold hoops. Heavy black ink
outlines, flat saturated colour blocking, two shade steps only, no gradient,
halftone texture. Flat bone-cream background.
```

**Known problem to fix first:** character consistency drifts between generations — hair came out long in the portrait and short in the macro shot. Do not generate story shots until four clean single-figure views (front / three-quarter / profile / back) are locked. Generate each view as a **separate** call — asking for a "turnaround sheet" in one image produces a cluster of floating heads.

## Build order

1. Get the audio and re-time the shot list to the waveform.
2. Freeze both character turnarounds. Export ≥12 refs each. Do not proceed until Cairos is identical across all four views.
3. Block the story in LTX Studio — shot list as script, turnarounds as character refs, draft quality first, upscale only once the cut works.
4. Build the transformation and both choruses in Neural Frames against real stems so the scale-up peaks on the downbeat.
5. Lip-sync hero shots only — two or three hook close-ups. Full-video lip sync will read uncanny at this style.
6. Assemble and grade in Resolve or CapCut. Grain + 8% halftone as the final node so every source blends into one look.
7. Cut the 9:16. Shots 05, 08, 13 and 14 are already composed for vertical.

## Open blockers

**1. No audio file exists anywhere reachable.** Not in Drive, not in Canva. The artist has a WAV on their phone and computer. Every timecode in the shot list is a 3:00 placeholder until the real waveform is available.

Minimum needed to unblock, readable off any DAW in 30 seconds:
- BPM
- Where each section starts (intro / verse 1 / hook / verse 2 / hook / bridge / outro), in bars or mm:ss
- Total runtime

Note: a 3-minute WAV is ~30MB of binary and may not transfer cleanly through tooling. An MP3 export is far more likely to come through. Uploading to the Drive folder above is the working path.

**2. Contents of the two zips are unknown.** ~60MB each, not yet opened. If they are rigged 3D models, the pipeline improves substantially — render real camera moves in Blender, cel-shade pass over the top, and character consistency stops being a problem entirely. If they are image sets, stay on the Dzine turnaround route.
