# AI VIDEO MODEL OPTIMIZATION DATABASE

**Music Videos Project --- Companion Reference Document**\
**Initial research snapshot: 17 November 2026**\
**Status: Living document; verify model/version/interface before every
production where technical limits matter.**

## 1. Purpose and evidence policy

This database helps adapt music-video prompts to the selected AI video
model. It is not a generic ranking of models and does not claim that a
model is universally best.

For each model, separate: - **Verified specification:** stated by
official provider documentation. - **Prompting guidance:** official
recommendations or clearly identified practical heuristics. - **Creative
inference:** likely useful adaptation based on the documented
workflow. - **Unknown / needs testing:** capabilities or weaknesses not
sufficiently established by accessible sources.

A published feature is not a guarantee of reliable output. A provider's
advertised capability is not an independent benchmark. Do not describe a
weakness as proven unless supported by documentation or repeatable
tests.

Model capabilities can differ between the provider's own app, API,
regional deployment and third-party wrappers. Always confirm the exact
model ID and interface.

## 2. Standard profile template

Every new model profile must include:

1.  Provider, exact model name, version, model ID and date checked.
2.  Official documentation and API references.
3.  Supported generation modes: text-to-video, image-to-video,
    first/last frame, reference-to-video, video-to-video, editing,
    extension.
4.  Input references: images, video, audio, documents, links; count,
    duration, size and format limits.
5.  Output: duration, resolution, frame rate, aspect ratio, audio,
    format.
6.  Prompt syntax, asset naming/binding and shot/timeline conventions.
7.  Character and object consistency mechanisms.
8.  Camera and multi-shot controls.
9.  Audio, music, dialogue, language and lip-sync features.
10. Known strengths supported by sources or test evidence.
11. Known weaknesses and failure modes, with confidence labels.
12. Recommended music-video workflow.
13. Prompt structure and example skeleton.
14. Negative prompt approach and known syntax compatibility.
15. Content policy and interface restrictions, linked to official rules.
16. Unknowns and tests required.
17. Change log and next review date.

Do not fill missing fields by guessing. Mark them **Not verified**.

## 3. Cross-model prompting principles

These are project heuristics, not claims that every model responds
identically.

-   Define one primary task for each generation: create, animate,
    continue, edit, transfer motion, or assemble.
-   State which input asset controls identity, which controls movement,
    which controls style, and which controls audio.
-   Use explicit asset labels matching the interface's actual reference
    order or binding syntax.
-   State what must be preserved and what may change.
-   Describe action in chronological order with clear subjects, spatial
    relationships and camera behavior.
-   Prefer a small number of meaningful actions over many simultaneous
    unrelated actions.
-   For multi-shot output, specify shot order, duration and transition
    intent only where the model/interface supports it.
-   For long-form music videos, generate manageable clips and assemble
    them in an editor unless the selected model reliably supports the
    desired continuous sequence.
-   Do not assume an uploaded full-length song can be used as reference
    if the interface imposes short audio-reference limits.
-   Do not assume native generated audio will reproduce the user's
    copyrighted/master recording. The safest production workflow is
    often to generate visuals and assemble the licensed/original master
    track in post, unless the selected platform supports the intended
    audio workflow.
-   Use positive instructions to define desired behavior; use a focused
    negative prompt only if the interface supports it and it helps.
-   Test a representative short scene before committing to a long
    generation run.

## 4. Model profiles

### 4.1 Seedance 2.0

**Provider / distribution:** ByteDance ecosystem; availability and
controls vary by interface.\
**Exact version:** Seedance 2.0.\
**Evidence checked:** 17 November 2026.

**Verified capabilities and constraints** - BytePlus documentation
describes Seedance 2.0 series text-to-video, image-to-video and omni
reference-to-video workflows. - Official API documentation describes
reference-to-video using reference images, videos and audio, with
supported counts and duration constraints varying by task and
endpoint. - BytePlus materials state Seedance 2.0 reference-to-video can
use up to 9 images, 3 videos and 3 audio clips in the documented
workflow; confirm exact endpoint and current request schema before
use. - Seedance 2.0 duration is documented as 4--15 seconds in the
BytePlus tutorial. - Some 2.0 workflows require at least one image or
video reference; audio-only reference is not universally available.
Check the task type.

**Prompt adaptation** - Assign every reference a clear role: character
identity, wardrobe, location, action/motion, camera movement, visual
style or audio. - Explicitly state which reference attributes are
preserved and which are transformed. - Use chronological action and
clear spatial relationships. - Keep the shot's central action legible.
Avoid overloading a short clip with many scene changes. - For group
performances, identify each performer and position rather than using
vague collective references. - If generating a sequence of independent
shots, repeat essential character and wardrobe details in each clip.

**Music-video use** - Useful candidate workflow when multiple reference
types need to inform one short sequence. - Consider separate generations
for a performance master, narrative inserts and close-ups when the
requested edit is too dense for one short clip. - Do not assume exact
lyric lip-sync from the presence of audio reference; test the chosen
interface and task mode.

**Unknowns / cautions** - Exact limits vary by model endpoint, API
version and third-party platform. - Do not assume a prompt guide from an
unofficial site is provider policy. - Comparative strengths in complex
dance, long-term identity consistency and fine lip-sync require
controlled tests.

**Official references** - BytePlus video generation tutorial:
https://docs.byteplus.com/en/docs/modelark/video-generation-tutorial?redirect=1 -
BytePlus create video generation task API:
https://docs.byteplus.com/en/docs/modelark/create-video-generation-task-api

### 4.2 Seedance 2.5

**Provider / distribution:** ByteDance / Dreamina / BytePlus ecosystem;
exact model naming and available features vary by interface.\
**Exact version:** Confirm whether the user's interface labels it
Seedance 2.5, Dreamina Seedance 2.5 or a Flash variant.\
**Evidence checked:** 17 November 2026.

**Verified capabilities and constraints** - BytePlus documentation
describes Dreamina Seedance 2.5 with text-to-video, image-to-video,
reference-to-video, editing and extension workflows. - The BytePlus
API/tutorial documents durations up to 30 seconds for the 2.5 family,
with specific task constraints. - The documented 2.5 reference workflow
supports combined image, video and audio references. Published limits
differ between 2.5 and 2.5 Flash; confirm the exact variant. - One
BytePlus reference recommendation states 1--5 subjects generally produce
better results, while 6--10 may reduce stability; image reference
recommendations also distinguish subject counts and multi-view
strategies. Treat this as provider guidance, not a guarantee. - Asset
count, input duration, size, resolution and task support are
endpoint-specific.

**Prompt adaptation** - Plan a short temporal arc with clear stages:
opening state, action development, key transition and ending state. - If
using references, label assets and state their exact function. - For
multi-shot or storyboard workflows, specify shot order and what carries
across cuts. - Use explicit "preserve" and "change" instructions for
editing or transformation tasks. - Separate identity reference from
motion reference; do not ask one image to define every detail if it does
not contain those details. - A 30-second allowance does not mean every
prompt should contain 30 seconds of unrelated action. Use duration only
when the action genuinely needs it.

**Music-video use** - Consider 2.5 for longer short-form sequences,
multi-reference planning, extensions or edit/assembly workflows when the
user's interface exposes those features. - For music videos, test
whether the selected mode preserves performers and audio references as
intended before using it for the full production. - Divide a long song
into coherent sections with continuity handoffs, rather than assuming
one generation can cover the entire track.

**Unknowns / cautions** - "Seedance 2.5" may refer to different
interfaces or variants. Confirm model ID. - Do not assume every feature
described in a Dreamina workflow is available in a third-party
wrapper. - Independent quality rankings, dance reliability and exact
lip-sync accuracy require repeatable tests.

**Official references** - BytePlus Seedance / video task documentation:
https://docs.byteplus.com/en/docs/modelark/create-video-generation-task-api -
BytePlus video generation tutorial:
https://docs.byteplus.com/en/docs/modelark/video-generation-tutorial?redirect=1

### 4.3 Wan 3.0

**Provider:** Alibaba Cloud Model Studio.\
**Model ID:** `wan3.0-video` (also check `wan3.0-video-prime` where
available).\
**Evidence checked:** 17 November 2026.

**Verified capabilities and constraints** - Official documentation
describes an all-in-one model with text-to-video, first/last-frame
control, multimodal reference, audio, editing and extension. -
Documented duration: 2--30 seconds; output up to 1080P and 30 fps in the
Model Studio documentation. - Native output can include dialogue,
background music and sound effects; audio can be disabled in supported
API calls. - The documented reference workflow supports up to 10
reference images, up to 5 reference videos with a combined duration
limit, and up to 5 reference audio clips with a combined duration limit.
The guide also describes a total multimodal input allowance of up to 20
materials in relevant workflows. Confirm the exact endpoint
constraints. - Asset labels such as Image 1, Video 1 and Audio 1
correspond to their order within each reference-media type. - Official
documentation describes subject, motion, style, audio,
storyboard/keyframe, document/webpage, editing and extension reference
workflows.

**Prompt adaptation** - Assign each input asset a distinct role and
refer to it by the exact ordering syntax documented by the interface. -
For subject consistency, explicitly identify the character or object in
the relevant image/video. - For motion transfer, specify that the
reference video controls movement/camera while the image controls
identity, if that is the intended mapping. - For audio reference, state
whether the audio is intended to guide beat/tone/lip-sync or another
aspect; do not assume it will reproduce the original master recording
exactly. - Use first/last-frame controls when a precise visual start and
end state matters. - For editing, state the desired change precisely and
identify what must remain untouched.

**Music-video use** - Candidate for mixed reference workflows, short
multi-shot clips, music-guided dance or lip-sync experiments, and clip
extension. - The 2--30 second duration range can support longer
individual segments than some competing interfaces, but continuity
should still be checked between generated clips. - Use the
audio-reference limits as a planning constraint; a full song may need
segmentation or post-production assembly.

**Unknowns / cautions** - Model Studio region availability and account
entitlements vary. - Native audio generation is not the same as
guaranteed faithful reproduction of a supplied song. - Real-world
consistency and lip-sync quality must be tested for the selected
workflow.

**Official references** - Wan 3.0 generation guide:
https://www.alibabacloud.com/help/en/model-studio/wan3-video-generation-guide -
Wan 3.0 prompt guide:
https://www.alibabacloud.com/help/en/model-studio/wan3-video-generation-prompt-guide -
Wan 3.0 API reference:
https://www.alibabacloud.com/help/en/model-studio/wan3-video-generation-api-reference/

### 4.4 HappyHorse 1.1

**Provider / distribution:** Listed in Alibaba Cloud Model Studio
documentation; confirm the provider/interface used by the user.\
**Model IDs:** `happyhorse-1.1-t2v`, `happyhorse-1.1-i2v`,
`happyhorse-1.1-r2v`.\
**Evidence checked:** 17 November 2026.

**Verified capabilities and constraints** - Official Model Studio model
listing describes text-to-video, first-frame image-to-video and
reference image-to-video variants. - Listed output: 480P, 720P or 1080P;
3--15 seconds; 24 fps; MP4; audio feature indicated in the model
listing. - The reference-to-video API documents reference image ordering
and prompt references such as \[Image 1\] and \[Image 2\]. - The
documented prompt limit is 5,000 non-Chinese characters or 2,500 Chinese
characters in the reference API; confirm the exact endpoint and language
counting behavior. - Seed and watermark parameters are described in the
API reference.

**Prompt adaptation** - Match the prompt mode to the actual model ID:
text-to-video, first-frame image-to-video or reference image-to-video. -
For reference mode, label each image by its input order and identify the
specific subject or object in that image. - Keep the action and camera
direction clear, chronological and achievable within 3--15 seconds. - Do
not assume the image reference endpoint accepts reference video or audio
unless the selected API explicitly documents it.

**Music-video use** - Consider it for short, self-contained performance
or narrative inserts. - Build longer sequences from several clips with
repeated character and wardrobe descriptions. - If the original track is
essential, confirm how the user's actual interface accepts audio; the
text-to-video and reference-image documentation alone do not establish
every audio-reference workflow.

**Unknowns / cautions** - The model listing's "Audio" feature should not
be interpreted as a guarantee of supplied-song lip-sync. - No verified
comparative benchmark for complex choreography, multi-character
consistency or long-term continuity is included here. - Do not infer
permissiveness from successful generations. Consult the official
platform policy and interface moderation behavior.

**Official references** - Model and workflow list:
https://www.alibabacloud.com/help/en/model-studio/video-generate-edit-model -
HappyHorse reference-to-video API:
https://www.alibabacloud.com/help/en/model-studio/happyhorse-reference-to-video-api-reference/ -
HappyHorse text-to-video API:
https://www.alibabacloud.com/help/en/model-studio/happyhorse-text-to-video-api-reference

### 4.5 Kling VIDEO 3.0

**Provider:** Kling AI.\
**Exact model family:** VIDEO 3.0; distinguish from VIDEO 3.0 Omni.\
**Evidence checked:** 17 November 2026.

**Verified capabilities and constraints** - Official Kling guide
describes text-to-video, image-to-video, start/end-frame generation,
native audio, multi-shot, element reference, multi-character
coreference, multilingual audio and 3--15 second duration. - Official
documentation lists supported languages including Chinese, English,
Japanese, Korean and Spanish, and describes dialect/accent support. -
Multi-shot can automatically plan shots; custom multi-shot allows
shot-level control in the interface. - Character or object elements can
be created from reference images or videos in supported workflows. -
Kling's API guide describes a multi-shot format supporting up to six
shots, each at least one second, with shot durations summing to total
duration. Exact constraints depend on API model and request mode.

**Prompt adaptation** - Decide whether to use single-shot or multi-shot
mode. Do not accidentally enable auto multi-shot for a shot intended to
be continuous. - For custom multi-shot, specify shot number, duration,
framing, action, camera movement and transition. - Use element binding
where available for recurring performers; explain which character is
bound to each element. - In multi-character dialogue or vocal scenes,
assign each line to a named performer. - For a music video, distinguish
the generated native audio from the user's master recording and plan
post-production if needed.

**Music-video use** - Candidate for short multi-shot sequences,
performance vignettes, dialogue/narrative scenes and reference-bound
recurring characters. - A 15-second generation is not a replacement for
a complete music-video timeline; maintain an external edit map and
continuity ledger. - Test dance formations and group identity with the
actual number of performers before producing many clips.

**Unknowns / cautions** - VIDEO 3.0 and VIDEO 3.0 Omni are separate
product variants; verify exact selection. - Do not assume all
element-reference features are available in every interface or API
route. - Native audio and language support do not guarantee exact
singing lip-sync to an uploaded commercial track.

**Official references** - Kling VIDEO 3.0 guide:
https://kling.ai/quickstart/klingai-video-3-model-user-guide - Kling
VIDEO 3.0 Omni guide:
https://kling.ai/quickstart/klingai-video-3-omni-model-user-guide -
Kling video API capability map:
https://kling.ai/document-api/guides/capability-map/video

### 4.6 Gemini Omni / Google Omni

**Provider:** Google.\
**Terminology:** "Google Omni" is ambiguous unless the interface is
specified. Current Google materials refer to Gemini Omni and Gemini Omni
Flash; confirm whether the user means Gemini Omni 1.1 Flash in the
Gemini app/API, Google Flow, or another Google workflow. Do not conflate
this with Kling VIDEO 3.0 Omni.\
**Evidence checked:** 17 November 2026.

**Verified capabilities and constraints** - Google's official Gemini
video documentation describes Gemini Omni Flash for multimodal video
generation and conversational editing, with text, image, audio and video
inputs in the documented API workflow. - The model page lists
`gemini-omni-1.1-flash` with text, image and video input, video
editing/extension up to 10 seconds, and output duration 3--10 seconds at
360p, 720p, 1080p or 4K at 24 fps. - Google product materials describe
reference-based creation, conversational editing, scene extension and
video-to-video editing. Product features and API features may differ. -
Google's Veo prompt guide remains useful as general Google video
prompting guidance, but it is not automatically the exact prompt guide
for Gemini Omni.

**Prompt adaptation** - Use conversational, iterative edits when working
in an interface designed for multi-turn refinement. - State the current
clip's preserved identity, scene, lighting and camera properties before
requesting a targeted change. - For new generation, specify shot
framing, movement, style, lighting, character, location and action. - If
the task is a multi-shot music-video sequence, verify whether the
selected Omni interface supports explicit shot-level control or whether
separate clips and external editing are more reliable. - Keep each
iterative edit focused: change one or a few related aspects while naming
what must remain unchanged.

**Music-video use** - Candidate for iterative refinement,
reference-based scene creation and editing/extension workflows. -
Because documented output clips are short in the API profile, plan a
multi-clip production and assemble the full song externally. - Do not
assume that the Google Gemini app, Google Flow and Gemini API expose
identical duration, reference, audio or editing controls.

**Unknowns / cautions** - Confirm whether "Google Omni" means Gemini
Omni 1.1 Flash or another product/interface. - Native audio and
multi-modal input are documented at product/API level, but exact
master-song lip-sync behavior should be tested. - Do not use
Veo-specific limits as Omni limits without verification.

**Official references** - Google Gemini video generation documentation:
https://ai.google.dev/gemini-api/docs/video - Gemini Omni Flash model
page: https://ai.google.dev/gemini-api/docs/models/gemini-omni-flash -
Google DeepMind Gemini Omni:
https://deepmind.google/models/gemini-omni/ - Veo prompt guide (related
Google prompting reference, not Omni specification):
https://deepmind.google/models/veo/prompt-guide/

### 4.7 MiniMax H3

**Provider:** MiniMax.\
**Exact model:** MiniMax H3; verify current deployment/API endpoint and
model version.\
**Evidence checked:** 17 November 2026.

**Verified capabilities and constraints** - MiniMax's official
announcement dated 3 August 2026 describes H3 as an open-source
general-purpose omni-modal video model. - The announcement describes
multimodal context understanding across text, images, video and audio. -
It states native stereo audio output, up to 2K resolution and 4--15
second video duration. - Supported aspect ratios include 21:9, 16:9,
4:3, 1:1, 3:4 and 9:16, among others.

**Prompt adaptation** - Treat H3 as a multimodal model and define the
role of each supplied modality. - Describe the intended scene and action
in chronological order. - Keep a short clip focused on a manageable
action sequence. - Where the deployed interface supports reference
binding, label identity, movement, style and audio assets explicitly. -
Do not assume API syntax or asset limits from the announcement; obtain
the exact deployment documentation first.

**Music-video use** - Candidate for short, multimodal audiovisual clips
and experimental music-video tests. - Test native stereo audio against
the intended use: generated scene audio, music generation, dialogue, or
synchronization to an uploaded track are different requirements. - Build
a controlled benchmark using the same performer, dance phrase, close-up
lip-sync and multi-character scene as other models.

**Unknowns / cautions** - The official announcement is not a complete
API or prompting manual. - Detailed reference counts, accepted file
sizes, shot control, lip-sync guarantees, commercial-use terms and
content policy must be checked against the actual deployment. - Do not
invent prompt syntax or claim specific strengths/weaknesses without
further official documentation or repeatable testing.

**Official reference** - MiniMax H3 announcement:
https://www.minimax.io/news/minimax-h3-open-source

## 5. Content policy and permissiveness research

Do not create a simple "permissiveness ranking" from anecdotal results.
For each provider and interface, record separately: - Official content
policy and prohibited content. - Age and identity restrictions. -
Sexual-content and nudity rules. - Violence and other sensitive-content
rules. - Restrictions on public figures, private individuals,
copyrighted characters, voices and likenesses. - Whether moderation
occurs at prompt submission, reference upload, generation or
publication. - Any interface-specific differences. - Date checked and
official source.

If a platform blocks a request, do not offer evasion instructions. Help
reformulate the creative direction within the platform's stated rules or
recommend a different compliant production approach.

For this project's mature but non-explicit visual direction, focus on
fashion, adult performers, expressive performance, confident
choreography, lighting, framing and chemistry. Preserve the Version 2.0
non-explicit boundary.

## 6. Comparative test protocol

To turn model profiles into practical intelligence, run the same small
benchmark through each model/interface when access permits.

Suggested benchmark clips: 1. Solo adult performer: face identity,
walking, camera orbit and close-up. 2. Four-person group: identity
distinction and simple formation change. 3. Dance phrase: footwork, arm
sequence, timing and natural variation. 4. Lip-sync test: one short,
clearly timed vocal phrase in the intended language. 5. Continuity test:
same performer and wardrobe across two separate clips. 6. Multi-shot
narrative: three shots with clear chronological progression. 7.
Reference conflict test: identity image plus motion reference with
explicit preserve/transform roles.

Record: - Exact model ID, interface, date and settings. - Prompt and
reference assets. - Number of attempts. - Identity consistency. - Motion
realism. - Dance accuracy. - Lip-sync accuracy. - Camera adherence. -
Shot transition quality. - Prompt sensitivity. - Moderation outcomes. -
Time/cost if known.

Rate each dimension with a consistent scale and retain example outputs.
Never generalize from one lucky or failed generation.

## 7. Change log

-   2026-11-17: Initial profiles created for Seedance 2.0, Seedance 2.5,
    Wan 3.0, HappyHorse 1.1, Kling VIDEO 3.0, Gemini Omni and MiniMax
    H3. Technical facts are linked to official documentation where
    available. Empirical comparative testing remains outstanding.
