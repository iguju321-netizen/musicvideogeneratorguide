# MINIMAX, WAN & HAPPYHORSE MODEL OPTIMIZATION GUIDE
**Music Videos Project · Companion guide 02 · Research snapshot: 17 November 2026**

## Evidence and naming policy

This guide covers MiniMax H3, H3 Max, H3 Fast, H3-Developer, Wan 3.0 / Wan 3.0 Prime, Wan 2.7, and HappyHorse 1.0 / 1.1. It separates the original provider model from a host's re-trained, speed-optimized or “developer” SKU.

Do not assume that a platform label such as “H3 Fast” or “H3-Developer” is an official MiniMax product tier. Confirm the provider, exact API model ID and task schema.

## 1. Quick selection matrix

| User-facing name | What is verified | Output / constraints | Music-video role |
|---|---|---|---|
| MiniMax H3 | Official MiniMax multimodal video model; open-sourced model announcement | 4–15s; up to 2K; native stereo audio; multimodal text/image/video/audio context | Short audiovisual performance, reference-led clips, sound-aware scene generation |
| MiniMax H3 Max | Third-party fal-built / retrained speed-optimized H3 variant | Runway Dev documents 5–15s, 480p/768p in its API wrapper; prompt or first/last frame; generated scene audio | Rapid visual/audio drafts; verify exact resolution options on selected host |
| MiniMax H3 Fast | Gateway-specific name `minimax-h3-fast` appears in some API catalogues; not established as universal official MiniMax tier | One gateway lists 4–30s and multimodal references; this is not universal | Treat as a host-specific speed lane; use only after schema check |
| MiniMax H3-Developer | Third-party gateway SKU, e.g. `minimax/h3-developer/text-to-video` and `/reference-to-video` | Host-specific endpoints and upload limits; not an official public MiniMax tier confirmed | Separate deployment profile; never assume native H3 feature parity |
| Wan 3.0 | Alibaba Model Studio `wan3.0-video` | 2–30s, 480p/720p/1080p, 30fps, MP4; native audio toggle; multimodal references | Longest short-form performance/narrative shots, audio-aware scenes, edit/extend |
| Wan 3.0 Prime | Alibaba Model Studio `wan3.0-video-prime` | Same broad modes and output envelope; speed-optimized tier | Faster iteration / final candidate when throughput matters |
| Wan 2.7 | Alibaba family, task-specific IDs | T2V/I2V: 2–15s; R2V/edit: 2–10s; 720p/1080p; 30fps; audio sync on supported tasks | Custom audio, multi-shot narrative, first/last-frame stitching, reference-led continuity |
| HappyHorse 1.1 | Alibaba Model Studio `happyhorse-1.1-t2v`, `-i2v`, `-r2v` | 3–15s, 480p/720p/1080p, 24fps, MP4; audio | Strong candidate for concise performance shots and reference-based character consistency |
| HappyHorse 1.0 | Alibaba Model Studio `happyhorse-1.0-t2v`, `-i2v`, `-r2v`, plus `-video-edit` | 3–15s, 720p/1080p, 24fps; video-edit endpoint listed for 1.0 | Legacy/original variant; use editing endpoint if available and needed |

## 2. MiniMax H3

### Verified provider facts
MiniMax's 3 August 2026 announcement describes H3 as an open-sourced general-purpose omni-modal video model. It accepts unified text, image, video and audio context and generates video with native stereo audio, up to 2K and up to 15 seconds. The announcement gives 4–15 seconds as the output range.

### Prompt optimization
- Assign a role to each modality: identity image, wardrobe image, location reference, motion video, rhythm/audio guide.
- Keep the scene's core action explicit and chronological.
- Use one principal movement phrase per 4–15 second clip.
- For dance, describe weight transfer, foot contact, torso accents, arm paths and formation changes; avoid only saying “dance energetically.”
- Treat native stereo audio as scene-audio generation, not proof that the uploaded master song will be reproduced exactly.
- If the goal is a music video cut to an existing track, generate visuals and assemble the master song in post unless the actual interface provides a tested audio-conditioning workflow.

### Music-video workflow
1. Generate a 5–8 second identity and movement test.
2. Generate a separate group-dance test with a simple formation change.
3. Generate a short lip-sync test in the target language.
4. Compare identity, mouth movement, body mechanics and sound separately.
5. Expand to 10–15 second clips only after the tests pass.

## 3. MiniMax H3 Max

H3 Max is not simply a “higher quality H3.” The accessible Runway Dev documentation describes it as a fal-built, speed-optimized / retrained H3 variant. Its documented wrapper supports text-to-video or first/last-frame generation, 5–15 seconds, prompt up to 6,000 characters, and 480p or 768p in that integration; native scene audio is generated in the same pass. Other hosts may expose different settings.

**Prompt strategy**
- Keep prompts more concise than a full master-script segment.
- Lead with the single visible action and camera move.
- Use first/last frames to lock the intended shot geometry when the interface supports them.
- Avoid relying on numerous references; Runway Dev says reference images and video inputs route to standard H3 instead.
- Use H3 Max for fast iteration only when its output limits match the project; use standard H3 for larger reference workflows or higher resolution.

## 4. MiniMax H3 Fast

The exact name is ambiguous. One third-party gateway documents a `minimax-h3-fast` ID and claims the same broad 4–30 second, up-to-2K, reference-rich input envelope as its `minimax-h3` route, with a faster priority lane. That should be treated as a **gateway-specific API variant**, not a universally established official MiniMax model tier.

Before prompting:
- Obtain the exact model ID and provider endpoint.
- Verify whether “Fast” is a queue/priority mode, a separate checkpoint, a lower-quality model or a billing alias.
- Verify whether it supports audio references, video references, first/last frames and 2K output.
- If it is only a speed lane, keep the same prompt structure as the underlying H3 model; do not invent special syntax.

## 5. MiniMax H3-Developer

The requested “H3-Developer” appears in third-party API catalogues, including separate text-to-video and reference-to-video model IDs. It is not established in the accessible MiniMax first-party model announcement as a distinct official public product.

**Mandatory handling**
- Treat the deployment as its own model profile.
- Record the actual gateway, model key, endpoint, media limits, resolution, duration and content review behavior.
- Use a self-contained prompt and explicit reference-role mapping.
- Do not infer that the word “Developer” means uncensored, open-weight, local, or moderation-free.
- Do not transfer the official H3 spec wholesale to this deployment.

## 6. Wan 3.0 and Wan 3.0 Prime

### Verified capabilities
Alibaba Model Studio lists:
- `wan3.0-video`
- `wan3.0-video-prime` (speed-optimized)

Both are all-in-one reference models with text-to-video, first/last-frame control, multimodal references, native audio, audio toggle, smart duration and adaptive aspect ratio. The published output envelope is 480p/720p/1080p, 2–30 seconds, 30fps, MP4.

### Prompt strategy
Wan supports more explicit asset-role direction than a simple T2V prompt:
- Use first/last-frame mode when the desired transition endpoints matter.
- Use reference mode when identity, movement, look or audio should be guided without pinning both ends.
- Identify assets by their actual type and order: Image 1, Video 1, Audio 1, etc., according to the selected API.
- State whether audio should be generated, disabled, or guided by supplied audio.
- Describe camera movement as a continuous path where continuity matters.
- For longer music-video clips, use 2–30 seconds only when the action genuinely develops across that duration.

### Prime-specific guidance
Prime is positioned as the speed-optimized member. Keep the same core prompt structure, but test it on a representative dance or multi-performer shot before assuming parity in motion fidelity or identity retention. Select Prime for throughput; select standard Wan 3.0 if the user's own tests show better results for the final take.

### Wan 3.0 prompt skeleton
> [Shot identity and duration]. Use Image 1 as [specific identity/wardrobe/location role], Video 1 as [specific movement/camera reference], and Audio 1 as [specific audio purpose]. Preserve [identity and wardrobe details]. In one coherent action, [chronological action]. Camera [movement] while keeping [spatial relationship]. Audio: [native audio intent or disable audio if the master track will be added in post]. End on [clear final state].

## 7. Wan 2.7

Alibaba Model Studio's current guide lists multiple task-specific Wan 2.7 endpoints rather than one single all-purpose endpoint:
- Text-to-video: `wan2.7-t2v` and dated versions; 2–15s, 720p/1080p, 30fps, audio sync and multi-shot narrative.
- Image-to-video: `wan2.7-i2v` and dated versions; first frame, first/last frame, continuation and audio-driven workflows; 2–15s.
- Reference-to-video: `wan2.7-r2v-2026-06-12`; multi-character references, ImageN/VideoN syntax; 2–10s.
- Video editing: `wan2.7-videoedit`; instruction-based editing and style transfer; 2–10s.

**Prompt strategy**
- Select the task endpoint first; then write to that endpoint's actual input mode.
- For multi-shot narrative T2V, label shots and keep each shot's action self-contained.
- For I2V, treat the image as the first frame and specify only the motion/change that follows.
- For first/last-frame stitching, describe a plausible transition between the two supplied states.
- For R2V, assign each character image/video a unique identity and do not refer ambiguously to “the person.”
- For custom audio, specify whether it controls beat, vocal performance, atmosphere or dialogue. Do not claim exact lyric timing unless it is supplied.

## 8. HappyHorse 1.1 and 1.0

### HappyHorse 1.1
Alibaba Model Studio lists three distinct endpoints:
- `happyhorse-1.1-t2v`: text-to-video with audio.
- `happyhorse-1.1-i2v`: first-frame image-to-video with audio.
- `happyhorse-1.1-r2v`: reference image-to-video with audio.

Output: 480p/720p/1080p, 3–15 seconds, 24fps, MP4.

**Prompt strategy**
- For T2V, specify one clear performance action, location and camera behavior.
- For I2V, preserve the starting frame's identity, pose, wardrobe and framing; describe the motion that begins after frame one.
- For R2V, make the character identity reference distinct from scene/style references.
- Use concise, concrete choreography; avoid a long list of simultaneous actions.
- Audio is listed as a feature, but exact synchronization to a user-supplied commercial song must be tested on the target endpoint.

### HappyHorse 1.0
Alibaba lists T2V, I2V, R2V and a separate video-edit endpoint for 1.0. Output is 720p/1080p, 3–15 seconds, 24fps. The official catalogue does not list a 1.1 video-edit endpoint in the same way.

**Selection guidance**
- Choose 1.1 for the newer listed T2V/I2V/R2V routes and the lower 480p option for drafts.
- Choose 1.0 when the actual job requires the documented 1.0 video-edit endpoint.
- Do not assume 1.0 is universally “better” or “worse”; compare the precise task modes and test outputs.

## 9. Common quality-control rules

- Separate native audio generation from uploaded-track conditioning.
- Test dance footwork and group formation separately from cinematic camera moves.
- Use a clear start state and final state for every generated clip.
- Keep identity, wardrobe and location anchors repeated in each independently generated segment.
- Do not use “uncensored” as a substitute for a verified model ID; see the separate access guide.

## 10. Sources

- MiniMax H3 official announcement: https://www.minimax.io/news/minimax-h3-open-source
- MiniMax H3 Max integration profile (Runway Dev; third-party API access): https://dev.runwayml.com/learn/minimax-h3-max-api
- MiniMax H3 Fast gateway schema (third-party): https://docs.beatapi.io/api-reference/video-api/minimax-h3-fast
- MiniMax H3-Developer gateway T2V schema (third-party): https://chinesemodels.ai/documentation/models/minimax/h3-developer/text-to-video
- Alibaba Model Studio video generation/edit model catalogue: https://help.aliyun.com/en/model-studio/video-generate-edit-model/
- Alibaba Wan 3.0 generation guide: https://www.alibabacloud.com/help/en/model-studio/wan3-video-generation-guide
- Alibaba Wan 3.0 prompt guide: https://www.alibabacloud.com/help/en/model-studio/wan3-video-generation-prompt-guide
- Alibaba Wan 3.0 API reference: https://www.alibabacloud.com/help/en/model-studio/wan3-video-generation-api-reference/
- Alibaba Wan 2.7 video edit API reference: https://www.alibabacloud.com/help/en/model-studio/wan-video-editing-api-reference
- MiniMax H3 Max overview (third-party): https://design.minimax.io/tools/minimax-h3-max

## Change log
- 2026-11-17: Initial version. Added Wan 2.7 and HappyHorse 1.0/1.1; separated official H3 from H3 Max and host-specific Fast/Developer SKUs.
