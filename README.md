# Aditya Kumar Rai

**ML researcher** working on **machine reasoning** (ARC-AGI), **medical imaging** and **efficient inference for large models**, through hands-on competition research and production AI systems.

## Research highlights
| Project | Problem | Result |
|---|---|---|
| [**ARC Prize 2026: NVARC + Qwen3.8 hybrid**](https://github.com/ADITYAKUMARRAI2007/arc-prize-2026-nvarc-qwen-hybrid) | Abstract reasoning (ARC-AGI-2), offline, 12 h on 4×L4 | **Public LB 33.19** (public baseline 29.72); test-time-trained 4B model + 27B reasoning model at xhigh effort |
| [**RSNA Knee MRI abnormality detection**](https://github.com/ADITYAKUMARRAI2007/rsna-knee-mri-abnormality-detection) | 12-finding multi-label MRI classification, 9 h on 2×T4 | **Private LB 0.944 AUC** · [notebook](https://www.kaggle.com/code/adityakumarrai0401/rsna-knee-label-ft-coatnet-specialists-blend); label-centred gains that held on the private board |
| [**Kaggle competition playbooks**](https://github.com/ADITYAKUMARRAI2007/kaggle-competition-playbooks) | Reusable research workflows | 25 playbooks distilled from top solutions across vision, NLP, LLMs, tabular, time series and more |

## What I work on
* **Reasoning and test-time compute:** test-time training, search (DFS), reasoning-effort and token-budget trade-offs, candidate selection.
* **Medical imaging:** multi-sequence MRI, label engineering from reports, specialist models, gold-set validation.
* **LLM systems:** serving large models on small GPUs (quantised 27B on 24 GB cards, a glibc compatibility patch for offline Kaggle), agents and tool use.

## Selected findings
* For Qwen3.8 on ARC-AGI-2, **reasoning effort and thinking budget mattered more than harness tricks**.
* In medical imaging, **better labels beat new architectures**: label work generalised to the private leaderboard; new backbones did not.
* **Validation must match the test distribution.** Small public-set checks repeatedly mispredicted leaderboard outcomes.

## Elsewhere
Kaggle: [adityakumarrai0401](https://www.kaggle.com/adityakumarrai0401)

## Engineering projects
AI agents and applied systems: [orderguard](https://github.com/ADITYAKUMARRAI2007/orderguard) (execution security for autonomous commerce agents), [thermal-chaos-arena](https://github.com/ADITYAKUMARRAI2007/thermal-chaos-arena) (GPU-cluster control arena), [genai-cli](https://github.com/ADITYAKUMARRAI2007/genai-cli) (tool-calling agent CLI).
