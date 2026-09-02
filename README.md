# Regarded — MiniMax H3 Sync Challenge

https://www.youtube.com/watch?v=ckyflxCj90U

> “Meet Riot. She's been abducted by aliens. I know, I know - it's not what she expected, either. But she swears this is how she remembers it.”

I’m DMing a tabletop campaign set during a modern First Contact scenario, and I’d already been using H3 to make what are basically campaign cutscenes. The challenge deadline gave me an excuse to stop experimenting and actually finish one.

**Regarded** is an 87.47-second scene generated locally with MiniMax H3 in ComfyUI and finished in DaVinci Resolve/Audacity.

## Final film

- **Runtime:** 87.47 seconds
- **Delivery:** 1280×720, 24 fps
- **Generation:** MiniMax H3 / ComfyUI
- **Hardware:** RTX 3090 Ti, 24 GB VRAM (local)
- **Editing:** DaVinci Resolve
- **Sample Audio Mixing:** Audacity
- **Voice reference:** recordings from myself and one player from the campaign

The project was built over roughly about four days, so render time mattered. Most shots were intentionally developed around the 720p target. S11-S12, the planetary impact sequence, were generated at 2 MP / roughly 1080p as an early test of how much extra render time higher-resolution finals would cost. That test helped convince me to keep the rest of the sequence focused on the 720p delivery target and spend the saved time on iteration instead.

## What I was testing

I deliberately stayed close to the standard H3 reference-to-video workflow instead of turning this into a giant custom-node exercise.

The useful part of the project is how the workflow changes as the scene gets harder:

- early shots establish Riot, the Orrery, weather and native H3 sound from image references;
- later shots feed previous H3 video forward to preserve blocking, screen direction, camera state and motion;
- several middle shots also feed previous H3 audio forward as a separate reference so rain, wind, Orrery mechanics and vocal tails survive camera changes;
- the Quorum voice uses a human timbre reference as an H3 input, not a pasted dialogue track;
- the homeworld sequence expands the reference stack with dedicated planet, position and mechanism references;
- S11-S12 use separate pre-impact and post-impact planet states to keep the same world intact across a relativistic impact and sensor whiteout;
- Turbo/full-step settings, text encoders, step counts and resolution were mixed up and tested shot by shot rather than globally.

The exact S01-S13 workflow JSONs are included. They stay separate because these were purpose-built passes, not one mega-graph assembled at any point. Where one H3 generation actually feeds another, that linkage is preserved in the workflow.

## Audio and finishing

H3 generated the synchronized dialogue, rain, wind, footsteps, Orrery sounds, telemetry, clipping, overload and aftermath audio used in the scene.

The final edit keeps that H3 audio and only applies normal finishing work: trims, clip-level gain changes, short crossfades/fades, EQ/noise cleanup where needed, conservative dynamics control and a safety limiter. No separately produced replacement soundtrack or external ambience bed was added.

The RKV sequence is intentionally much louder than the surrounding scene. The final mix was aimed at keeping that rupture violent without clipping or burying the quieter Quorum material.

## Repository map

- [`workflows/selected_shots/`](workflows/selected_shots/) — exact S01-S13 ComfyUI workflows
- [`workflows/H3_RIOT_WORKFLOW_INDEX.json`](workflows/H3_RIOT_WORKFLOW_INDEX.json) — annotated judge-facing production index
- [`clip_sequence/`](clip_sequence/) — the 13 selected H3 source outputs used to assemble the final sequence
- [`ref_prev_clips/`](ref_prev_clips/) — extracted/generated prior-shot references used for linked continuity passes
- [`references/`](references/) — character, environment, planet and audio reference assets
- [`documentation/SHOT_MANIFEST.md`](documentation/SHOT_MANIFEST.md) — shot-by-shot settings and reference strategy
- [`documentation/PRODUCTION_NOTES.md`](documentation/PRODUCTION_NOTES.md) — creative rationale, iteration lessons, audio provenance and final-edit notes
- [`documentation/DEPENDENCIES.md`](documentation/DEPENDENCIES.md) — models, nodes and environment

Several workflows load earlier generated clips or reference assets by filename. Those files are not model weights and are not embedded in the JSON, so they must be relinked if reproducing the sequence outside the original project folder.

The per-shot JSON files remain the authoritative record for prompts, seeds, references and settings.
