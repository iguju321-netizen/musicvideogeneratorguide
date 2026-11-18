# GOOGLE GEMINI OMNI & VEO MODEL OPTIMIZATION GUIDE
**Music Videos Project · Companion guide 03 · Research snapshot: 17 November 2026**

## Scope

Covers Gemini Omni 1.1 Flash, Gemini Omni 1.2 Flash, Gemini Omni Flash Developer, Veo 3.1, Veo 3.1 Fast and Veo 3.1 Lite.

“Developer” in a marketplace may describe an API access route or developer-facing wrapper, not a distinct model checkpoint. Always record the exact model ID.

## 1. Quick selection matrix

| Requested name | Canonical model / mapping | Verified key points | Recommended use |
|---|---|---|---|
| Gemini Omni 1.1 Flash | `gemini-omni-1.1-flash` | 3–10s, 24fps; 360p/720p/1080p/4K listed; text/image input and video editing/extension; up to 10s source video for edit/extend | Short edits, extensions, quick conversational iteration |
| Gemini Omni 1.2 Flash | `gemini-omni-1.2-flash` | 3–15s; 360p/720p/1080p/4K; native audio; improved reference adherence; conversational editing and extension | Better fit for longer single segments, identity/wardrobe continuity and iterative clip refinement |
| Gemini Omni Flash Developer | Usually developer/API route to the currently selected Omni Flash version; exact ID must be checked | No distinct official “Developer” model checkpoint verified | Use the underlying 1.1 or 1.2 profile, plus gateway-specific input schema |
| Veo 3.1 | `veo-3.1-generate-001` (Vertex AI naming) | Premium quality tier; native audio; text/image workflows and reference/keyframe features depend on product surface | Final-quality visual masters when output quality is the priority |
| Veo 3.1 Fast | `veo-3.1-fast-generate-001` | Faster tier, native audio; production iteration and standard workflows | Rapid but quality-conscious scene generation |
| Veo 3.1 Lite | `veo-3.1-lite-generate-001` (check current API docs) | Cost-optimized; text-to-video and image-to-video; 4/6/8s; 720p/1080p; landscape/portrait | High-volume drafts, shot tests and rapid iteration |

## 2. Gemini Omni 1.1 Flash

### Verified facts
Google AI for Developers documents the model code `gemini-omni-1.1-flash`. The listed video output range is 3–10 seconds at 24fps and resolutions 360p, 720p, 1080p or 4K. It supports text and image input and video input for editing/extension, with source video up to 10 seconds in the documented API model page.

### Prompt strategy
- Use concise natural-language direction with one clear visual objective.
- State the shot's opening composition, performer action and camera movement.
- For image-conditioned clips, identify the reference as identity, wardrobe, location or style; do not let one reference ambiguously control everything.
- Use conversational editing for one targeted change at a time: “keep the performer, pose and camera; change only the lighting.”
- Keep edits incremental; avoid asking for a full reimagining when continuity is the priority.
- For a long music video, generate short segments and assemble the full track in post.

### Music-video use
Use 1.1 for short inserts, edits, extensions and rapid visual exploration. Its 10-second ceiling makes it less convenient than 1.2 for longer continuous performance segments.

## 3. Gemini Omni 1.2 Flash

### Verified differences from 1.1
Google announced Omni 1.2 Flash on 5 November 2026. It increases maximum clip duration from 10 to 15 seconds, adds multi-turn conversational editing across full clips, and improves reference adherence. Google also describes stronger consistency across faces, garments, props and environments, improved speech/lip-sync and more continuous camera moves. Google lists 3–15 second output in one-second increments and up to 4K output through supported product surfaces.

### Prompt strategy
1. **Describe one continuous shot or a deliberately ordered small multi-shot sequence.**
2. **Pin identity and wardrobe:** identify the reference image(s) that control each performer and outfit.
3. **Use a clear camera path:** specify start position, movement, subject relationship and end framing.
4. **State continuity constraints:** face, hair, jewelry, garment construction, set dressing, lighting and props.
5. **Use conversational revisions surgically:** change one variable per follow-up while explicitly preserving everything else.
6. **Use first/last frame or references only where the interface supports the exact mode.**
7. **For dialogue/lip-sync:** identify speaker, language, vocal style and exact supplied audio; test separately before relying on it for a full music-video chorus.

### Music-video use
1.2 is the preferred Omni profile for 10–15 second performance shots, longer continuous camera moves, multi-turn corrections, and stronger reference continuity. It still does not replace editorial assembly for a complete 3-minute music video.

## 4. Gemini Omni Flash Developer

No separate official model checkpoint called “Gemini Omni Flash Developer” was confirmed. The official model IDs located are `gemini-omni-1.1-flash` and `gemini-omni-1.2-flash`. “Developer” may mean:
- Gemini API / AI Studio access,
- Google Cloud developer endpoint,
- a marketplace's developer SKU,
- a third-party wrapper.

**Required intake:** exact model ID, provider/gateway, API endpoint, task modes, duration/resolution options and whether the UI has its own safety or prompt rewriting layer. If the model ID is 1.1 or 1.2, use that version's guide and add only the host-specific parameter notes.

## 5. Veo 3.1 family

### Veo 3.1 standard
Google describes standard Veo 3.1 as the top-quality tier where visual fidelity is the priority for final production cuts. Use it for final candidate shots when the selected interface supports the required duration, reference and resolution controls.

**Prompt strategy**
- Give the model a clearly defined shot rather than a broad montage.
- Specify camera movement, lens/framing intention, lighting source and subject action.
- Describe physical movement in chronological order.
- Keep audio direction separate from visual direction.
- For multi-performer scenes, state positions and interactions explicitly.
- Use references to lock character, costume and environment when available in the target interface.

### Veo 3.1 Fast
Google describes Fast as the quicker tier while maintaining high quality, suited to standard production workflows. Use the same creative prompt structure as standard Veo, but treat Fast as an iteration tier until comparative tests show that it meets final-shot requirements.

**Prompt strategy**
- Keep the central action singular and readable.
- Use fewer competing camera instructions.
- Use it for blocking, timing, camera tests and alternate takes.
- Rerun selected shots on standard Veo when the final fidelity is materially better in your tests.

### Veo 3.1 Lite
Google describes Lite as its most cost-effective video model, with speed comparable to Fast and a price under half Fast in the initial release announcement. The documented Lite API supports T2V and I2V, 4/6/8-second duration choices, 720p/1080p, and 16:9 or 9:16. The DeepMind model card describes it as based on Veo 3 and reports no safety regression against Veo 3.1 in Google's own evaluations.

**Prompt strategy**
- Use Lite for rapid shot prototyping and high-volume generation.
- Restrict each clip to one action phrase and one camera move.
- Keep the image-to-video motion instructions simple and preserve the still's identity/composition.
- Do not assume Lite has every advanced reference, editing or extension feature of standard Veo; verify the exact product surface.

## 6. Google model selection for music videos

- **Short shot, many iterations:** Veo Lite or Omni 1.1.
- **Short shot with better continuity and conversational editing:** Omni 1.2.
- **Fast production draft:** Veo Fast.
- **Final visual fidelity:** Veo 3.1 standard, subject to actual interface controls.
- **A complete music video:** none should be treated as a one-prompt replacement for a directed timeline and editorial assembly.

## 7. Audio and lyric policy

Native generated audio, dialogue lip-sync, voice reference, audio-conditioned motion and faithful reproduction of an uploaded master track are different capabilities. Never promise that a model will reproduce the user's exact song unless the chosen endpoint documents and passes that test. When the song is already finished, the reliable default remains visual generation plus licensed/original master-track assembly in post.

## 8. Sources

- Google Gemini Omni 1.1 Flash model documentation: https://ai.google.dev/gemini-api/docs/models/gemini-omni-flash
- Google Gemini Omni 1.2 Flash launch announcement: https://blog.google/innovation-and-ai/technology/developers-tools/introducing-gemini-omni-1-2-flash/
- Google Cloud Gemini Omni 1.2 Flash model documentation: https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/gemini/omni-1-2-flash
- Google DeepMind Gemini Omni 1.2 Flash model card: https://deepmind.google/models/model-cards/gemini-omni-1-2-flash/
- Google Veo 3.1 Lite announcement: https://blog.google/innovation-and-ai/technology/ai/veo-3-1-lite/
- Google DeepMind Veo 3.1 Lite model card: https://deepmind.google/models/model-cards/veo-3-1-lite/
- Google Cloud Veo 3.1 family overview: https://cloud.google.com/blog/products/ai-machine-learning/veo-3-1-lite-and-a-new-veo-upscaling-capability-on-vertex-ai
- Google Veo prompting guide: https://cloud.google.com/vertex-ai/generative-ai/docs/video/video-gen-prompt-guide

## Change log
- 2026-11-17: Initial version. Split Omni 1.1 and 1.2 and separated Developer routing from model identity.
