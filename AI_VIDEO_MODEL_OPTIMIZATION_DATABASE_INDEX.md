# AI VIDEO MODEL OPTIMIZATION DATABASE — ROUTING INDEX
**Updated 17 November 2026**

Load only the selected family guide, not all four, to reduce context size.

| Guide | File | Models covered |
|---|---|---|
| 01 | `01_SEEDANCE_MODEL_OPTIMIZATION_GUIDE.md` | Seedance 2.5 Flash; 2.5; 2.0; 2.0 Fast; 2.0 Mini; 2.0 Enhanced; 2.0 Mini Enhanced |
| 02 | `02_MINIMAX_WAN_HAPPYHORSE_OPTIMIZATION_GUIDE.md` | MiniMax H3; H3 Max; H3 Fast; H3-Developer; Wan 3.0; Wan 3.0 Prime; Wan 2.7; HappyHorse 1.0; HappyHorse 1.1 |
| 03 | `03_GOOGLE_GEMINI_OMNI_VEO_OPTIMIZATION_GUIDE.md` | Gemini Omni 1.1 Flash; Gemini Omni 1.2 Flash; Gemini Omni Flash Developer; Veo 3.1; Veo 3.1 Fast; Veo 3.1 Lite |
| 04 | `04_KLING_GROK_VIDU_BACH_OPTIMIZATION_GUIDE.md` | Kling V3.0 Turbo; Kling Video O3 4K; Kling v3.0 Pro; Kling v3.0 4K; Kling v3.0 Std; Grok Imagine Video v1.5 Developer; Grok Imagine Video v1.5; Grok Imagine Video; Vidu Q3-Turbo; Vidu Q3-Pro; BACH 1.0 Pro |
| Separate | `05_UNCENSORED_AND_LESS_FILTERED_ACCESS_GUIDE.md` | Third-party access routes for Seedance, Wan, MiniMax H3, HappyHorse and Vidu, plus verification notes for other families |

## Full requested-list routing

| # | Requested name | Guide | Identity / caution |
|---:|---|---|---|
| 1 | Seedance 2.5 Flash | 01 | BytePlus `dreamina-seedance-2-5-flash-261115` |
| 2 | Seedance 2.5 | 01 | BytePlus `dreamina-seedance-2-5-260628` |
| 3 | Bach 1.0 Pro | 04 | Video Rebirth; public API schema still needs confirmation |
| 4 | MiniMax H3 Max | 02 | Speed-optimized/retrained H3 route; host-specific schema |
| 5 | MiniMax H3 Fast | 02 | Gateway-specific label; verify exact endpoint |
| 6 | Gemini Omni 1.1 Flash | 03 | `gemini-omni-1.1-flash` |
| 7 | Gemini Omni 1.2 Flash | 03 | `gemini-omni-1.2-flash` |
| 8 | MiniMax H3-Developer | 02 | Third-party API SKU; not verified as official MiniMax tier |
| 9 | Wan-3.0-Prime | 02 | `wan3.0-video-prime` |
| 10 | Wan-3.0 | 02 | `wan3.0-video` |
| 11 | MiniMax H3 | 02 | Official MiniMax H3 |
| 12 | Seedance 2.0 Mini | 01 | `dreamina-seedance-2-0-mini-260615` |
| 13 | Seedance 2.0 Enhanced | 01 | BytePlus enhanced category or third-party SKU; verify ID |
| 14 | Seedance 2.0 Mini Enhanced | 01 | No universal canonical ID confirmed |
| 15 | HappyHorse-1.1 | 02 | `happyhorse-1.1-t2v`, `-i2v`, `-r2v` |
| 16 | Kling V3.0 Turbo | 04 | Fast tier; exact host/model ID required |
| 17 | Kling Video O3 4K | 04 | Separate O3 line, not Kling 3.0 4K |
| 18 | Grok Imagine Video v1.5 Developer | 04 | Developer route; no separate official checkpoint verified |
| 19 | Grok Imagine Video v1.5 | 04 | `grok-imagine-video-1.5` |
| 20 | Gemini Omni Flash Developer | 03 | Developer/API wrapper label; map to 1.1 or 1.2 |
| 21 | HappyHorse-1.0 | 02 | `happyhorse-1.0-*`; edit endpoint listed for 1.0 |
| 22 | Seedance 2.0 | 01 | `dreamina-seedance-2-0-260128` |
| 23 | Seedance 2.0 Fast | 01 | `dreamina-seedance-2-0-fast-260128` |
| 24 | Wan-2.7 | 02 | Task-specific T2V/I2V/R2V/edit IDs |
| 25 | Veo 3.1 Lite | 03 | Cost-optimized tier |
| 26 | Veo 3.1 Fast | 03 | Speed tier |
| 27 | Veo 3.1 | 03 | Quality tier |
| 28 | Grok Imagine Video | 04 | Classic model, distinct from v1.5 |
| 29 | Vidu Q3-Turbo | 04 | `viduq3-turbo` |
| 30 | Kling v3.0 Pro | 04 | Pro / 1080p tier in documented wrapper |
| 31 | Kling v3.0 4K | 04 | 4K tier |
| 32 | Kling v3.0 Std | 04 | Standard / 720p tier |
| 33 | Vidu Q3-Pro | 04 | `viduq3-pro` |

## Model-selection intake
Before writing production prompts, establish exact platform, model ID, task mode, duration, resolution, aspect ratio, reference types/counts, audio behavior, negative-prompt support, prompt rewriting and moderation behavior. “Developer,” “Enhanced,” “Fast,” “Mini,” “Turbo,” “Prime,” “Pro,” “Std” and “4K” are not self-explanatory model identities.

## Evidence policy
Distinguish provider documentation, third-party API documentation, marketplace labels, vendor claims, practical prompting advice and unknowns. A capability documented on one host must not be generalized to every host. Do not make model quality rankings without repeatable controlled tests.

The previous long-form database is preserved as `AI_VIDEO_MODEL_OPTIMIZATION_DATABASE_ARCHIVE_2026-11-17.md` for historical reference only.
