# KLING, GROK, VIDU & BACH MODEL OPTIMIZATION GUIDE
**Music Videos Project · Companion guide 04 · Research snapshot: 17 November 2026**

## Scope and naming caution

This guide covers Kling V3.0 Pro / Std / Turbo / 4K, Kling Video O3 4K, Grok Imagine Video / v1.5 / v1.5 Developer, Vidu Q3-Turbo / Q3-Pro, and BACH 1.0 Pro.

These are not all one family. In particular, **Kling 3.0 and Kling O3 are separate model lines**. A provider or aggregator may offer the same model through different wrappers, so use the exact model ID and endpoint.

## 1. Quick selection matrix

| Requested name | Mapping / exact ID | Verified features | Best music-video use |
|---|---|---|---|
| Kling v3.0 Std | `kling3.0_standard` on Runway Dev; verify native Kling platform ID | 3–15s, multi-shot, native sound, 720p tier | Drafts and standard production shots |
| Kling v3.0 Pro | `kling3.0_pro` | 3–15s, multi-shot, native sound, 1080p tier | Final HD shots |
| Kling v3.0 4K | `kling3.0_4k` | 3–15s, multi-shot, native sound, 4K tier | High-resolution master shots |
| Kling V3.0 Turbo | Platform-specific fast tier; one catalogue lists a 1080p fast variant | Exact API controls vary; do not conflate with Pro/Std | Rapid drafts after exact model check |
| Kling Video O3 4K | Common third-party ID family `kwaivgi/kling-video/o3/4k/...` | 3–15s, native 4K, reference composition, video edit/reference modes; optional audio | Reference-led character continuity, 4K edits and reference video |
| Grok Imagine Video (classic) | `grok-imagine-video` | 1–15s; up to 720p; video editing and extension; reference mode | Existing-video editing, extension and reference workflows |
| Grok Imagine Video v1.5 | `grok-imagine-video-1.5` | 1–15s; native 1080p; up to 14 reference images, 3 voice references, pinned frames; lip-synced generated speech | Reference-led performers, voice consistency and lip-sync tests |
| Grok Imagine Video v1.5 Developer | Same upstream model ID in developer APIs unless marketplace proves otherwise | Developer/API access route, not verified as separate checkpoint | Use v1.5 guide plus gateway-specific schema |
| Vidu Q3-Turbo | `viduq3-turbo` | 1–16s; 540p/720p/1080p; audio-video sync and storyboard generation; faster tier | Quick dance tests, short edits and draft clips |
| Vidu Q3-Pro | `viduq3-pro` | 1–16s; up to 1080p; audio-video sync and storyboard generation; quality tier | Final short shots, start/end-frame transitions |
| BACH 1.0 Pro | Video Rebirth BACH 1.0 Pro | Reported: text/image/reference inputs, up to 12 references, 4K 10-bit 4:2:2, camera controls, relighting, multilingual native lip-sync | High-end production shots and controlled continuity; verify API access |

## 2. Kling 3.0 family

### Verified capabilities
Kling 3.0 is described in accessible provider/API documentation as a multi-shot video model with native audio. One request can contain up to six shots, each with its own prompt and duration; total clip duration is 3–15 seconds. Audio can include dialogue, sound effects and ambience. Tier differences in the documented Runway Dev implementation are primarily output resolution:
- Standard: 720p
- Pro: 1080p
- 4K: 4K

### Prompt strategy
Use an explicit shot list:
- `Shot 1 — [duration]: [framing, action, camera, audio]`
- `Shot 2 — [duration]: [framing, action, camera, audio]`
- Keep character identity, wardrobe and location stable across shots.
- State the transition logic between shots.
- Use one primary action per shot.
- Include sound direction only when generated audio is wanted; otherwise disable it where possible and add the master song in post.

### Std vs Pro vs 4K
The documented API tier comparison says the same basic inputs and durations are accepted, with resolution tier as the primary distinction. Do not assume that 4K changes character consistency or choreography accuracy by itself. Choose based on delivery resolution, cost and your own comparative tests.

### Kling 3.0 Turbo
“Turbo” is listed in third-party catalogues as a faster/lower-cost member of the Kling 3.0 family. Exact first-party API schema and output controls were not verified in the same detail as Standard/Pro/4K. Treat it as a separate selectable model only when the interface shows its exact ID. Use it for quick blocking, camera and movement tests; do not assume it is equivalent to Pro at lower latency.

## 3. Kling Video O3 4K

Kling O3 is a separate line from Kling 3.0. Accessible O3 4K API documentation describes:
- Text-to-video, image-to-video, reference-to-video, video edit and video-reference workflows.
- 3–15 second clips.
- Native 4K output in the 4K tier.
- Up to seven combined reference elements/images in supported reference workflows.
- Optional native audio.
- Multi-shot prompt lists or intelligent shot planning in supported endpoints.
- Reference labels such as `@Image1`, `@Element1`, and `@Video1` depending on task.

### Prompt strategy
O3 is particularly suited to asset-led prompts:
1. Define `@Element1` as the lead performer identity; `@Element2` as another performer or key prop.
2. Define `@Image1` as style/lighting reference, not identity, unless that is the intended role.
3. Use `@Video1` only when the reference-video endpoint supports it.
4. State what the reference controls: face, wardrobe, location, motion, camera or color treatment.
5. Describe what may change and what must remain unchanged.
6. If editing source footage, lead with the requested change and explicitly preserve all other aspects: “replace only the jacket; keep the walk, face, camera path, background and audio.”
7. For multi-shot prompts, specify duration and action per shot. Avoid mixing a full freeform prompt and a separate multi-shot array if the API disallows both.

**Do not transfer Kling 3.0's multi-shot limits or prompt syntax to O3 without checking the O3 endpoint.**

## 4. Grok Imagine Video family

### Grok Imagine Video classic
The classic model is the video editing/extension member of the current xAI lineup. The official xAI overview lists text-to-video, image-to-video, reference images, video editing and extension. It supports up to 720p; editing accepts short source clips, and extension adds a continuation. Exact limits depend on mode.

**Prompt strategy**
- For editing, describe the one change and what must stay unchanged.
- For extension, describe the continuation from the final action and preserve the same camera, lighting, performer and location.
- For reference-to-video, assign each image one role and label it by its reference index.
- Do not assume the classic model has the same native 1080p or voice-reference controls as v1.5.

### Grok Imagine Video v1.5
xAI's 16 June 2026 announcement describes better motion/physics and audio/speech synchronization. The 31 July 2026 reference update added text-to-video, image references, voice references and native 1080p. The current xAI docs list:
- 1–15 second output.
- 480p/720p/1080p.
- Up to 14 reference images.
- Up to 3 voice references.
- First and last frame plus up to four mid-video keyframes in supported workflows.
- Native audio with lip-synced generated speech.

**Prompt strategy**
- Use one image per fixed role: performer identity, wardrobe, location, styling or prop.
- Name references in the prompt using the exact syntax supported by the endpoint.
- Keep the cast and prop count small when continuity is critical.
- Pin the first/last frame and intermediate keyframes for planned visual transitions.
- Use voice references for character speech/voice continuity, not as a promise of exact music-master reproduction.
- For T2V, remember the xAI docs describe a first-frame image synthesis step followed by animation; make the opening composition especially clear.

### Grok Imagine Video v1.5 Developer
No distinct “Developer” checkpoint was verified. Official xAI API model ID is `grok-imagine-video-1.5`; developer access is the API route. If an aggregator lists a separate Developer name, record its exact endpoint and whether it changes the schema, safety setting, reference budget or pricing. Do not assume a different visual model.

## 5. Vidu Q3 family

### Vidu Q3-Turbo
Official Vidu model pages describe Q3-Turbo as the fastest and most cost-effective tier for previews and rapid drafts. API documentation lists:
- Text-to-video, image-to-video and start/end-to-video.
- 1–16 second duration.
- 540p, 720p or 1080p in the documented API.
- Audio-video synchronization and storyboard generation.

**Prompt strategy**
- Use concise shot direction with one action and one camera move.
- Use it for movement tests, choreography blocking and alternate cuts.
- When using start/end frames, ensure the images have compatible aspect ratios and compositions.
- Do not use the Turbo tier as the final reference benchmark unless the same prompt is also tested on Pro.

### Vidu Q3-Pro
Vidu describes Q3-Pro as a higher-quality Q3 tier. The API lists T2V, I2V, start/end-frame and reference-to-video modes, 1–16 seconds and up to 1080p. Q3 models expose an audio option for synchronized generated audio.

**Prompt strategy**
- Use start/end frames when the opening and ending composition must match a storyboard.
- Give each reference image a single purpose.
- Describe motion in physical terms and include camera direction.
- For dance, prioritize a readable phrase over dense choreography; validate footwork and group timing in a short test.
- Treat generated dialogue/audio as separate from precise synchronization to the user's master song.

## 6. BACH 1.0 Pro

BACH 1.0 Pro is a Video Rebirth model, not a generic “Bach” model. An industry exhibitor profile describes the model with:
- Text, image and up to 12 reference inputs.
- First/last-frame control.
- Director-grade pan, tilt and dolly controls.
- Relighting / look changes without reshooting.
- 4K and 10-bit 4:2:2 output.
- Native lip-sync in more than ten languages, including Japanese.
- Claimed multi-cut identity, costume and performance consistency.

These details are from an industry exhibitor profile and should be treated as vendor-reported until verified in the official BACH product/API documentation and the user's interface.

### Prompt strategy
- Treat BACH as a production-control model: define shot, lens/framing, camera path, light source, exposure/contrast, performer blocking and continuity in production language.
- If relighting is supported, specify the target lighting change and explicitly preserve subject identity, set geometry and camera.
- Use first/last frames to constrain the visual transition.
- For multi-cut consistency, provide a small, well-organized identity/wardrobe reference set and repeat performer names/roles across shots.
- For lip-sync, state language, exact lyric/audio excerpt, speaker identity and whether the audio is a reference or generated. Test a short phrase first.
- Keep camera instructions executable: “slow 1.5m dolly-in” is clearer than “dynamic cinematic camera.”

**Unknowns:** official public API schema, exact model ID, prompt length, file limits, pricing, supported aspect ratios and content policy were not independently confirmed in this research pass. Ask for the user's exact BACH interface before writing production-specific syntax.

## 7. Model choice for music videos

- **Dense multi-shot performance in one short generation:** Kling 3.0, if the target interface supports its shot list.
- **Reference-heavy 4K character continuity/editing:** Kling O3 4K.
- **Voice-reference / generated speech lip-sync:** Grok Imagine Video 1.5.
- **Existing clip edit/extension:** Grok classic or Kling O3, depending on the required reference/edit mode.
- **Quick draft movement:** Vidu Q3-Turbo or Kling Turbo.
- **Quality-oriented short Q3 shot:** Vidu Q3-Pro.
- **Controlled camera, relighting and high-end finishing workflow:** BACH 1.0 Pro, pending API verification.

## 8. Sources

- xAI Grok Imagine Video 1.5 launch: https://x.ai/news/grok-imagine-video-1-5
- xAI Grok Imagine Video 1.5 reference update: https://x.ai/news/grok-imagine-video-1-5-references
- xAI Video Overview and model comparison: https://docs.x.ai/developers/model-capabilities/video/overview
- xAI Video Generation API: https://docs.x.ai/developers/model-capabilities/video/generation
- Kling 3.0 API tier comparison (Runway Dev access documentation): https://dev.runwayml.com/learn/kling-3-0-api
- Kling O3 4K reference-to-video (fal model page): https://fal.ai/models/fal-ai/kling-video/o3/4k/reference-to-video
- Vidu model catalogue: https://platform.vidu.com/models
- Vidu Q3 API docs: https://platform.vidu.com/docs/api-reference/video-models/vidu-q3/start-end-to-video
- Vidu Q3 image-to-video docs: https://platform.vidu.com/docs/api-reference/video-models/vidu-q3/image-to-video
- BACH 1.0 Pro exhibitor profile (Video Rebirth): https://inter-bee.com/en/forvisitors/exhibitor_info/detail/detail.php?id=545
- BACH product home: https://www.bach.art/welcome

## Change log
- 2026-11-17: Initial version. Kling O3 separated from Kling 3.0; Grok Developer label separated from upstream v1.5; Vidu tiers and BACH added.
