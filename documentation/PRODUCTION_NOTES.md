# Production Notes

This collects the creative rationale, iteration notes, audio provenance and final-edit record in one place. The short version is that the project was built around continuity: one character, one alien presence, one mechanical environment, one planet and one evolving soundscape across thirteen separate H3 generations.

## Creative rationale

### The Quorum

The Quorum’s “Lion Man” appearance is perceptual, not literal. Riot is translating something incomprehensible into an ancestral humanoid-predator form. The main reference point was the Lion Man of Hohlenstein-Stadel, plus the much more basic human fear of realizing you are alone with an apex predator.

The hooded eyes, attempted reflective eyeshine and stretched proportions are there to make the figure feel wrong before it feels openly threatening. I was trying to avoid both a conventional monster and a friendly fantasy angel.

The voice follows the same idea. Two human recordings are used as a timbre reference, but H3 is prompted to synthesize them into one dry, layered, collective voice rather than simply replaying either speaker.

### The Highlands and Orrery

The Scottish Highlands are a constructed meeting space. The Quorum presents Riot with something quiet and pastoral while giving her increasingly awful information.

The henge and Orrery are also interpretive. They are Riot’s mental model of alien astronavigation: standing stones and a mechanical celestial instrument standing in for architecture she could not otherwise understand.

The Orrery’s two moons and layered mechanisms matter because it is supposed to represent a specific planetary system, not generic fantasy machinery. Keeping that geometry consistent turned out to be one of the harder continuity problems in the project (and I never quite solved it before the deadline).

### The homeworld and RKV

The homeworld is revealed gradually across several shots rather than appearing as one sudden effect.

The relativistic kill vehicle starts as a deliberately tiny visual cue. Making the projectile obvious made the scale feel smaller, so the final version relies on a faint intermittent strobe, a hidden strike beyond the upper-right limb, then a violent jump to white-blue sensor saturation.

The next shot recovers from that whiteout onto the same planet in a damaged state.

The scene is built as:

**hostile approach → encounter → recognition → homeworld reveal → RKV strike → aftermath → final warning**

The Quorum is physically absent from the last shot. The closing line arrives after Riot is alone again, reinforcing that the figure was never necessarily standing in the henge in the first place.

## What changed during iteration

This was very much not a first-generation-wins project.

Separate references were developed for Riot, the Quorum, the Orrery, spatial position and the Quorum homeworld. The biggest recurring failures were:

- Riot drifting in appearance, placement or wetness;
- the Quorum becoming too monstrous or too angelic;
- the Orrery adding/removing moons or changing orientation;
- impossible mechanism geometry;
- broken screen direction;
- planet geography changing between cuts;
- impact shots turning into generic missiles, orange explosions or symmetric shockwaves.

Previous H3 clips were increasingly reused as production state rather than just inspiration. By the middle of the sequence, later generations are explicitly inheriting prior video and, in several cases, prior H3 audio as separate references.

Prompting also got shorter and more technical. Long descriptive prompts tended to create extra machinery, duplicated objects and confused staging. The later prompts put more weight on subject definitions, camera geometry, screen position, fixed geography, timing windows, physical constraints and sound cues tied to visible events.

Turbo and full-step generations were compared shot by shot. The trade was not simply speed versus quality. Depending on the shot, the deciding factor might be motion stability, dialogue timing, facial consistency, reference adherence or fine detail. In general, unless on a time constraint, I'd prefer to not use turbo LORAs.

Most of the sequence stayed around the 720p-oriented 1 MP workflow. S11-S12 were pushed to 2 MP / roughly 1080p once the planet identity and impact composition were established. Those early higher-resolution finals were useful as a render-time test, and the length of rendering them helped justify spending the rest of the deadline on more iterations at the lower target instead.

## Audio provenance

H3’s native joint video/audio generation is used throughout the selected workflows.

`firstskyinprogress.wav` is a voice-timbre reference built from recordings by the project creator and one player from the tabletop campaign. It is used as an H3 reference input for the Quorum. The recording itself is not the final dialogue track.

Several middle workflows also feed audio from a prior H3 clip into the next H3 generation. The point is continuity: rain, wind, Orrery mechanics, vocal tails and storm pressure can survive while the camera or subject action changes.

The clearest linked-audio stretch is S05-S10.

The impact sequence deliberately handles audio differently:

- **S11** generates telemetry, clipping and sensor overload natively from the prompt.
- **S12** uses the prior impact shot visually, but does not inherit its audio. H3 generates a new overload/recovery track.
- **S13** also uses the preceding shot, but visually only. Space audio is mostly dropped, Highland rain/wind/breathing return, and the Quorum voice reference is used again for the final off-screen line.

## Final edit

The finished scene was assembled in DaVinci Resolve.

The picture pass used normal editorial work: trims, hard cuts where they read better, a last second Orrery-to-planet-impact visual bridge, a shortened destruction section and the final RKV-to-Riot aftermath cut.

The audio pass kept H3’s generated sound and concentrated on making the separate clips behave like one scene:

- clip-level gain changes;
- short audio-only crossfades/fades where needed;
- EQ/noise cleanup;
- conservative compression/limiting;
- master peak protection.

No external score, ambience bed or separately generated replacement soundtrack was added.

The RKV was intentionally left much louder than the surrounding scene. The main mix pass reduced the worst peak mismatch while preserving that dramatic jump.

The last measured review master reported approximately:

- **87.47 s runtime**
- **−20.5 LUFS integrated**
- **18.9 LU loudness range**
- **−5.2 dBTP true peak**

Those numbers are kept here as QC history, not presented as a fresh measurement of the final upload.

All images were generated with OpenAI's Image 2.0.
