# UNCENSORED & LESS-FILTERED VIDEO MODEL ACCESS GUIDE
**Music Videos Project · Separate companion guide · Research snapshot: 17 November 2026**

## 1. Purpose and boundaries

This document records third-party hosted routes described as “uncensored,” “spicy,” or less-filtered for model families in the project. These names do **not** necessarily indicate a new model checkpoint or an official release by the original model developer.

For every route, distinguish:
1. The upstream model family.
2. The host or marketplace.
3. Whether the host adds an additional moderation layer.
4. Whether the upstream model itself applies moderation.
5. The exact model ID and API schema.
6. The provider terms, host terms, age requirements and applicable law.

**Project boundary remains unchanged:** the Master Music Video Guidelines V2.0 require sensual, mature, confident or provocative presentation where appropriate, while remaining non-explicit. This companion guide is for accurate routing and prompt compatibility, not for bypassing safeguards or changing the project's content boundary.

All depicted performers must be adults. Never generate sexual or exploitative content involving minors, non-consensual sexual content, or intimate imagery of a real person without consent. A platform's “uncensored” label does not remove legal, consent, likeness or safety obligations.

## 2. Verified or reported access routes

| Model family | Third-party route found | What the source claims | Confidence / caution |
|---|---|---|---|
| Seedance 2.5 | Sogni: `seedance-2-5-uncensored` / `seedance2-5-uncensored`; alias “Seedance 2.5 Spicy” | Separate model route on an uncensored account; described as carrying Seedance 2.5 features and limits | Third-party documentation, not official ByteDance release |
| Seedance 2.0 Mini | Sogni: `seedance-2-0-mini-uncensored` / `seedance2-mini-uncensored` | Separate Mini route with more permissive content policy | Third-party documentation, not official ByteDance release |
| Wan 3.0 | Sogni: `wan3.0-spicy-video`; aliases include Wan 3.0 Enhanced / Wan 3 Uncensored | More permissive hosted Wan 3 route; 2–30s, native audio, 480p–1080p reported | Third-party hosted build; do not assume same moderation or settings as Alibaba's API |
| MiniMax H3 | Third-party hosted H3 routes marketed as “uncensored” or without an additional host refusal layer | Some hosts state they remove their own additional refusal layer; upstream model/service may still apply moderation | Host claims vary; no universal official MiniMax “uncensored H3” checkpoint verified |
| MiniMax H3 Max | Third-party routes listed by some adult-oriented marketplaces | A host may expose H3 Max without its own extra filter | Not a provider-level H3 Max uncensored release; verify the exact endpoint |
| HappyHorse 1.1 | Vellria lists `vellria-happyhorse-1-1`; Spicy Studio lists a HappyHorse 1.1 spicy route | Host describes mature-theme access with 3–15s output and up to 1080p | Third-party access route; not an official Alibaba uncensored model |
| Vidu Q3 | SpicyAPI reports a Q3 Spicy variant | Host reports an unfiltered route distinct from Vidu's own screened API/app | Third-party route; not an official Vidu Q3 model |
| Grok Imagine Video | No confirmed official “uncensored” model variant located | xAI has standard safety controls; third-party API routes may expose configurable screening in some authorized integrations | Do not call a model uncensored based on one API parameter |
| Kling 3.0 / O3 | No provider-official uncensored model variant confirmed | Some third-party endpoints expose authorized safety-check configuration | An API flag is not a separate uncensored checkpoint and may require account authorization |
| Google Gemini Omni / Veo | No uncensored model variant confirmed | Google model cards and acceptable-use policies apply | Do not advertise an uncensored route without a verifiable provider/host source |
| BACH 1.0 Pro | No uncensored variant confirmed | No public uncensored model route verified | Unknown |
| MiniMax H3-Developer | No official uncensored classification confirmed | “Developer” describes a third-party API deployment label in the sources found | Do not infer uncensored status from “Developer” |

## 3. Seedance uncensored routes

Sogni documentation identifies:
- `seedance-2-5-uncensored` (Creative Agent selector `seedance2-5-uncensored`)
- `seedance-2-0-mini-uncensored` (selector `seedance2-mini-uncensored`)

The Sogni docs describe these as separate hosted routes from standard Seedance. They are not official ByteDance model names. The 2.5 uncensored route is documented as inheriting the Seedance 2.5 capabilities in that host, while the Mini route inherits the Mini capability envelope. Always check Sogni's live model docs and price estimate because limits and access requirements can change.

**Prompt adaptation**
- Use the regular Seedance prompt structure from Guide 01.
- Do not write euphemisms or evasive instructions to bypass a refusal.
- State adult performers and the intended non-explicit visual direction clearly.
- Use precise fashion, choreography, framing and lighting direction rather than vague sexualized adjectives.
- If a prompt is rejected, diagnose whether the issue is a likeness agreement, reference-image restriction, host policy or model limitation; do not assume that switching to an uncensored label resolves every issue.

## 4. Wan 3.0 Enhanced / spicy route

Sogni documentation identifies `wan3.0-spicy-video` as its Wan 3.0 Enhanced route and lists aliases such as `wan3-enhanced` / `wan3.0-enhanced`. It is a host-side build and is separate from the standard Alibaba `wan3.0-video` route. The documentation describes native audio, 2–30 second output, 30fps and up to 1080p.

Some API hosts expose an `nsfw_checker` parameter for Wan 3.0. This is a moderation setting on that host's endpoint, not a separate “uncensored model.” It may be unavailable on some variants, and disabling a check does not guarantee generation or remove other provider/platform checks.

**Prompt adaptation**
- Use Guide 02's Wan structure.
- Identify whether the job is T2V, I2V, R2V, first/last frame or edit.
- Keep visual direction explicit and non-explicit.
- Confirm whether the selected host allows the needed reference type and audio mode.

## 5. MiniMax H3 hosted routes and local weights

Some hosts market MiniMax H3 as “uncensored” because they do not add an additional moderation layer between the user and the upstream service. This is not evidence that MiniMax has published an official uncensored checkpoint. MiniMax's own H3 announcement describes the open-sourced model, but hosted product behavior and local deployment are distinct.

**Important distinction**
- **Official hosted service:** can include provider-side prompt checks, prompt enhancement or output review.
- **Third-party hosted service:** may add or omit its own review layer, but upstream checks may remain.
- **Local/open-weight workflow:** moderation behavior depends on the exact weights, inference stack, text encoder, wrapper and operator's own safeguards.

Do not assume a “developer” model is local or unfiltered. Record the exact host and deployment. Do not rely on community claims about removing refusal layers as official model capabilities.

## 6. Prompting for mature but non-explicit music videos

For this project, the desired result is usually achieved through direction rather than explicitness:
- Adult performers with confident, self-possessed screen presence.
- Fashion-led styling, clubwear, stagewear or editorial wardrobe.
- Suggestive but non-explicit choreography.
- Flirtatious interaction and chemistry without explicit sexual acts.
- Close-ups, silhouettes, reflections, low-key lighting, color contrast and deliberate camera movement.
- Clear consent and agency in performer interactions.
- Consistent wardrobe and choreography continuity.

**Recommended wording pattern**
> Adult performers, mature fashion-editorial styling, confident flirtatious stage presence, expressive close-proximity choreography, intentional eye contact and playful chemistry. Keep the performance suggestive but non-explicit, with no nudity or explicit sexual activity. Preserve each performer's agency and consistent wardrobe.

This is a creative-direction template, not a guarantee that any particular platform will accept the prompt.

## 7. Verification checklist before use

- [ ] Confirm exact host name and website.
- [ ] Confirm exact model ID, not only display label.
- [ ] Confirm upstream provider and whether the route is official or third-party.
- [ ] Read the host's current acceptable-use policy.
- [ ] Read the upstream provider's terms where applicable.
- [ ] Confirm age and likeness/consent requirements.
- [ ] Confirm whether reference images of real people require a likeness agreement.
- [ ] Confirm reference-image, audio, video and output limits.
- [ ] Confirm whether the host modifies or expands prompts.
- [ ] Keep a record of the exact date, settings and moderation outcome.

## 8. Sources

- Sogni Seedance 2.5 / uncensored model documentation: https://docs.sogni.ai/models/seedance-2-5/
- Sogni current model catalog and selectors: https://github.com/Sogni-AI/sogni-creative-agent-skill/blob/main/references/models.md
- Sogni Wan 3 Uncensored / Enhanced guide: https://docs.sogni.ai/models/wan-3-uncensored/
- Sogni direct-generation workflow and model selector list: https://docs.sogni.ai/api-reference/direct-generation/
- MiniMax H3 official announcement: https://www.minimax.io/news/minimax-h3-open-source
- MiniMax H3 host-side moderation explanation (host's own claim): https://minimaxi.design/blog/what-is-uncensored-minimax-h3
- Vellria uncensored model catalogue: https://vellria.com/en/models
- HappyHorse 1.1 Vellria route: https://vellria.com/en/models/vellria-happyhorse-1-1
- Spicy Studio model access overview: https://spicystudio.io/
- SpicyAPI Vidu Q3 report (third-party test claims): https://spicyapi.ai/blog/vidu-q3-nsfw
- xAI video API overview and safety controls: https://docs.x.ai/developers/model-capabilities/video/overview

## Change log
- 2026-11-17: Initial version. Includes only routes with public documentation or catalog evidence; no universal “uncensored” claim is made for a provider family.
