# SEEDANCE MODEL OPTIMIZATION GUIDE
**Music Videos Project · Companion guide 01 · Research snapshot: 17 November 2026**

## Scope and evidence rules

This guide covers the Seedance variants requested: Seedance 2.5 Flash, Seedance 2.5, Seedance 2.0, Seedance 2.0 Fast, Seedance 2.0 Mini, and third-party labels called Seedance 2.0 Enhanced / Seedance 2.0 Mini Enhanced. It distinguishes BytePlus/ByteDance model IDs from aggregator labels.

**Evidence labels**
- **Provider-confirmed:** appears in BytePlus/ModelArk documentation or a provider announcement.
- **Platform label:** a third-party interface exposes this name; it may map to a provider model or a platform-specific workflow.
- **Practical guidance:** project prompting recommendations, not an experimentally proven model weakness.
- **Unverified:** do not assume the feature exists until the user's exact interface/model ID is checked.

## 1. Variant matrix

| User-facing name | Canonical BytePlus model ID / mapping | Documented output | Main difference / selection |
|---|---|---|---|
| Seedance 2.5 Flash | `dreamina-seedance-2-5-flash-261115` | 4–30s, 24fps, 480p/720p | Newer Flash tier; faster/cheaper positioning. Lower max resolution than standard 2.5 in the current ModelArk catalogue. |
| Seedance 2.5 | `dreamina-seedance-2-5-260628` | 4–30s, 24fps, 480p/720p/1080p/4K per current BytePlus model list; verify region/endpoint | Quality-oriented 2.5 tier; longer clip and richer reference budget than 2.0. |
| Seedance 2.0 | `dreamina-seedance-2-0-260128` | 4–15s, 24fps, up to 4K | Highest-resolution 2.0 tier in the documented BytePlus list. |
| Seedance 2.0 Fast | `dreamina-seedance-2-0-fast-260128` | 4–15s, 24fps, 480p/720p | Speed/iteration tier; not equivalent to full 2.0 output tiers. |
| Seedance 2.0 Mini | `dreamina-seedance-2-0-mini-260615` | 4–15s, 24fps, 480p/720p | Lightweight / lower-cost iteration tier. |
| Seedance 2.0 Enhanced | Third-party label; often maps to the standard `dreamina-seedance-2-0-260128` workflow, but confirm exact ID | Depends on host | BytePlus itself labels the standard 2.0 as an “enhanced version” in its enhanced-generation table. Some aggregators separately list an “Enhanced” task SKU. Do not assume those are identical without checking. |
| Seedance 2.0 Mini Enhanced | Third-party label; no universal canonical BytePlus ID confirmed | Depends on host | Treat as a platform-specific SKU until the API/model ID is known. Could denote a separate enhanced endpoint or merely a task mode. |
| Seedance 2.5 (uncensored) | Third-party access only in sources found; see separate Uncensored Access Guide | Host-dependent | Not an official ByteDance model release. Separate hosted route and moderation envelope. |
| Seedance 2.0 Mini (uncensored) | Third-party access only in sources found; see separate Uncensored Access Guide | Host-dependent | Not an official ByteDance model release. |

**Critical naming rule:** ask the user for the platform and exact model key when they say “Enhanced,” “Mini Enhanced,” or “Flash.” A model name on a marketplace is not necessarily the official model name.

## 2. Seedance 2.5 vs 2.0: practical decision

Choose **2.5** when:
- The clip needs 16–30 seconds in one generation.
- The reference set exceeds the 2.0 budget.
- The selected interface exposes video editing or extension and the job benefits from a longer segment.
- The 2.5 resolution ceiling is sufficient for the planned workflow.

Choose **2.0** when:
- Native 1080p or 4K output is essential.
- A short 4–15 second generation is sufficient.
- The project can be divided into short, continuity-led segments.

The Sogni comparison page describes Seedance 2.5 as 480p/720p and 2.0 as up to 4K, while the current BytePlus model list reports 2.5 model output options that include 1080p/4K. This discrepancy demonstrates why the exact host, date, endpoint and deployment must be checked before specifying resolution. **Never hard-code a resolution based on a different platform's page.**

## 3. Reference and workflow differences

### Seedance 2.5
The documented Sogni/BytePlus-backed workflow supports text-to-video, first-frame, first-and-last-frame, reference-to-video, video editing and extension. One published Sogni profile lists up to 30 images, 10 videos and 10 audio clips (30 media items total); its BytePlus endpoint may have different constraints. Verify the target deployment before writing asset-count-dependent prompts.

**Prompt strategy**
- Use an ordered reference manifest: `Image 1 = lead identity`, `Image 2 = wardrobe`, `Image 3 = location`, `Video 1 = movement reference`, `Audio 1 = rhythm / performance guide`.
- State which attributes each reference controls and which it must not override.
- For 16–30 second generations, write a compact temporal arc: opening composition → action progression → one key transition or escalation → final state.
- Do not fill 30 seconds with a string of unrelated mini-scenes. Keep one visual world or a tightly linked sequence.
- For multi-character choreography, define cast count, screen positions, formation changes and who leads each movement phrase.

### Seedance 2.5 Flash
Treat it as a **drafting / throughput tier** unless the interface's documentation establishes parity with standard 2.5.
- Keep the action simpler and the prompt hierarchy sharper.
- Use a strong first frame and one central movement phrase.
- Prefer a small reference set with clearly separated roles.
- Use Flash to explore blocking, camera placement, wardrobe silhouette and visual rhythm; rerun the selected concept in standard 2.5 if higher output resolution or fidelity is required.
- Do not assume that “Flash” supports fewer features merely because it is faster; BytePlus currently lists the same broad task modes for 2.5 Flash and standard 2.5, but output tiers differ.

### Seedance 2.0
- Prioritize image/reference binding and precise action chronology.
- Use 4–15 second clips, usually one main action phrase per generation.
- For a complex video, create a set of self-contained prompts that repeat character, wardrobe and location anchors.
- If 4K is available, do not assume the prompt itself must be longer; resolution is an output parameter, not a storytelling instruction.

### Seedance 2.0 Fast
- Use for fast concept iterations, motion tests, camera blocking and alternate takes.
- Reduce simultaneous actions; retain one clear subject action and one camera move.
- Avoid making it carry the entire final master if the host's Fast tier has a lower resolution ceiling.
- Do not infer that it has identical quality to standard 2.0 from shared task-mode checkmarks.

### Seedance 2.0 Mini
- Best treated as a compact generation tier for simple shots, short inserts, look tests and rapid prompt iteration.
- Keep character count low and actions physically legible.
- Use fewer simultaneous references; repeat essential identity and wardrobe information in the prompt.
- Avoid relying on it for dense multi-shot storytelling until the chosen interface has been benchmarked.

## 4. “Enhanced” naming and interface verification

BytePlus's own enhanced-generation page places `dreamina-seedance-2-0-260128` and `dreamina-seedance-2-5-260628` in an “enhanced version” category, while `dreamina-seedance-2-0-fast-260128` and `dreamina-seedance-2-0-mini-260615` are in a “basic version” category. Third-party catalogues also expose separate SKUs called “Seedance 2.0 Enhanced” and “Seedance 2.0 Mini Enhanced.”

Therefore:
1. Ask for a screenshot or exact model ID if “Enhanced” appears in the interface.
2. Record provider, aggregator, endpoint, model ID, task type and selected quality tier.
3. Do not write an Enhanced-specific prompt syntax unless its provider docs establish one.
4. If the SKU resolves to the same underlying model, use the matching core profile and note only host-specific constraints.

## 5. Music-video prompt blueprint

Use this order for Seedance unless the selected interface recommends another syntax:

1. **Scene identity:** scene name, duration, music section, structural role.
2. **Reference binding:** identify each image/video/audio asset by exact slot and purpose.
3. **Performer continuity:** adult cast, face/identity anchors, hair, wardrobe and accessories.
4. **Visual world:** location, lighting, atmosphere, props and spatial layout.
5. **Action chronology:** opening pose/state, movement phrase, interaction, progression, ending state.
6. **Camera plan:** shot size, lens feel, camera position, movement and focus behavior.
7. **Music relationship:** beat accents, energy curve, lyric performance moments and instrumental inserts.
8. **Continuity locks:** details that must remain unchanged.
9. **Focused exclusions:** only likely failure modes relevant to this shot.

**Example skeleton**

> Create a [duration] cinematic music-video segment for [song section]. Use Image 1 as the fixed identity reference for the lead performer; use Image 2 for the exact wardrobe; use Image 3 for the location and lighting palette. Preserve the lead's facial identity, hairstyle, jewelry and outfit throughout. In the opening wide shot, [clear opening action]. The performer then [chronological movement phrase]. The camera [specific camera move] while maintaining [framing/subject relationship]. On the musical accent at [known timestamp or phrase landmark], [specific visual accent]. End with [specific final state] so the clip can cut into the next segment. Maintain realistic anatomy, grounded foot contact and natural motion. Do not introduce new performers, wardrobe changes, props or locations.

## 6. Common failure prevention

- **Overloaded clip:** reduce the number of simultaneous actions and use multiple generations.
- **Identity drift:** reduce ambiguous references; state which reference controls face, hair and clothing.
- **Dance becomes generic:** write counts or phrase landmarks and describe the actual footwork, arm pathway, torso accent, formation and performer interaction.
- **Random edits:** specify shot order only when the chosen generation mode supports multi-shot output; otherwise generate shots separately and edit in post.
- **False lip-sync confidence:** audio reference is not proof of accurate lyric-level mouth movement. Test a short vocal phrase separately.
- **Unstable wardrobe:** repeat the full current wardrobe in every independent prompt and explicitly prohibit unexplained changes.

## 7. Negative prompt guidance

Use the project baseline negative prompt, but trim it to the clip's risks. Seedance prompts should prioritize positive instructions and chronological actions. Do not assume every interface exposes a separate negative-prompt field; if not, phrase exclusions briefly at the end of the positive prompt.

## 8. Sources

- BytePlus ModelArk model list (current model IDs, modes and output): https://docs.byteplus.com/en/docs/modelark/model-list
- BytePlus enhanced-generation model table: https://docs.byteplus.com/en/docs/byteplus_las/video_gen_enhanced
- BytePlus Seedance 2.5 prompt guide: https://docs.byteplus.com/en/docs/modelark/seedance-2-5
- BytePlus video generation tutorial: https://docs.byteplus.com/en/docs/modelark/video-generation-tutorial
- Sogni Seedance 2.5 comparison and reference limits (third-party deployment; useful for comparison, not universal endpoint truth): https://docs.sogni.ai/models/seedance-2-5/
- Sogni Creative Agent model selectors and uncensored route names: https://github.com/Sogni-AI/sogni-creative-agent-skill/blob/main/references/models.md

## Change log
- 2026-11-17: Initial version. Added current 2.5 Flash model ID and separated BytePlus official variants from third-party Enhanced labels.
