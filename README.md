<p align="center">
  <img src="assets/hero.svg" alt="Aditya Kumar Rai: machine learning research on Kaggle" width="100%">
</p>

<p align="center">
  <a href="https://www.kaggle.com/adityakumarrai0401"><img src="https://img.shields.io/badge/Kaggle-adityakumarrai0401-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white" alt="Kaggle profile"></a>
  <a href="https://github.com/ADITYAKUMARRAI2007/compute-allocation-arc-agi-2"><img src="https://img.shields.io/badge/ARC_Prize_2026-33.19-7B2FF7?style=for-the-badge" alt="ARC Prize 2026: 33.19"></a>
  <a href="https://github.com/ADITYAKUMARRAI2007/label-repair-knee-mri"><img src="https://img.shields.io/badge/RSNA_Knee_MRI-0.944_AUC-2EA043?style=for-the-badge" alt="RSNA Knee MRI: 0.944 private AUC"></a>
  <a href="https://github.com/ADITYAKUMARRAI2007/kaggle-competition-playbooks"><img src="https://img.shields.io/badge/Playbooks-25-F0B400?style=for-the-badge&logo=bookstack&logoColor=white" alt="25 competition playbooks"></a>
</p>

I compete on Kaggle and write up what I learn as research. My work is about **getting the most out of a fixed compute budget**: deciding how to split GPU-hours between test-time training and long chain-of-thought reasoning, serving 27B models on 24 GB cards offline, and fixing noisy labels when a new architecture won't help.

Every solution here ships with its code, an exact inference notebook, a technical report, and the experiments that *didn't* work.

## Competition work in numbers

<table>
  <tr>
    <td align="center"><a href="https://github.com/ADITYAKUMARRAI2007/compute-allocation-arc-agi-2"><strong>33.19</strong><br>ARC-AGI-2 score<br><sub>4 × L4, 12 h, offline</sub></a></td>
    <td align="center"><a href="https://github.com/ADITYAKUMARRAI2007/label-repair-knee-mri"><strong>0.944</strong><br>knee-MRI private AUC<br><sub>12 findings, 9 h on 2 × T4</sub></a></td>
    <td align="center"><a href="https://github.com/ADITYAKUMARRAI2007/label-repair-knee-mri/blob/main/docs/experiments.csv"><strong>77</strong><br>logged experiments<br><sub>RSNA alone, with outcomes</sub></a></td>
    <td align="center"><a href="https://github.com/ADITYAKUMARRAI2007/kaggle-competition-playbooks"><strong>25</strong><br>domain playbooks<br><sub>distilled from top solutions</sub></a></td>
  </tr>
</table>

## Solutions

| Competition | Year | Result | What made the difference | Write-up & code |
| --- | --- | --- | --- | --- |
| [**ARC Prize 2026**](https://www.kaggle.com/competitions/arc-prize-2026-arc-agi-2) · ARC-AGI-2 | 2026 | **33.19** public LB<br><sub>29.72 TTT-only baseline</sub> | Moved compute from a test-time-trained 4B model to a 27B reasoning model at `xhigh` effort with 80k-token thinking budgets; patched a glibc-2.38 engine to run on 2.35 | [report](https://github.com/ADITYAKUMARRAI2007/compute-allocation-arc-agi-2/blob/main/docs/REPORT.md) · [code](https://github.com/ADITYAKUMARRAI2007/compute-allocation-arc-agi-2) <sub>(opens after the deadline)</sub> |
| [**RSNA Knee Abnormality Detection**](https://www.kaggle.com/competitions/rsna-knee-abnormality-detection) | 2026 | **0.944** private AUC<br><sub>0.942 public-recipe baseline</sub> | Repaired labels for the noisiest findings and added per-finding specialists; four new architectures earned no blend weight | [report](https://github.com/ADITYAKUMARRAI2007/label-repair-knee-mri/blob/main/docs/REPORT.md) · [code](https://github.com/ADITYAKUMARRAI2007/label-repair-knee-mri) · [notebook](https://www.kaggle.com/code/adityakumarrai0401/rsna-knee-label-ft-coatnet-specialists-blend) |

<details>
<summary><b>Findings I'd stake a claim on</b></summary>

<br>

<table>
<tr>
<td width="50%"><img src="assets/arc_compute_split.svg" width="100%"><br><sub><b>ARC:</b> same hardware and hours, but more reasoning-model time gives a higher hidden-set score.</sub></td>
<td width="50%"><img src="assets/rsna_private.svg" width="100%"><br><sub><b>RSNA:</b> label fixes moved the held-out score while the public leaderboard stayed flat.</sub></td>
</tr>
</table>

- **`reasoning_effort` is not monotonic.** Qwen3.8-27B scores lower at `medium` than at `low`, because the chat template only injects instructions for `low` and `xhigh`.
- **Generation bounds selection.** 93% of failed ARC grids never had a correct candidate, so no judge or reranker could have recovered them.
- **A 58-study expert set** ranks models correctly but cannot resolve differences below 0.003 AUC. Use it as a gate, not for tuning.
- **Small public validations misled me in both directions**, in both competitions. I now only trust validations that match the test distribution and the time budget.

</details>

## What I am building now

| Project | Why it is here |
| --- | --- |
| [**kaggle-competition-playbooks**](https://github.com/ADITYAKUMARRAI2007/kaggle-competition-playbooks) | 25 structured playbooks (validation, label engineering, ensembling, vision, LLMs, time series, ARC, …) with case studies from top solutions, usable by humans and coding agents. |
| [**orderguard**](https://github.com/ADITYAKUMARRAI2007/orderguard) | Deterministic authorization for autonomous commerce agents: the agent proposes, only verified code can move money. |
| [**thermal-chaos-arena**](https://github.com/ADITYAKUMARRAI2007/thermal-chaos-arena) | A control benchmark for agents operating fragile GPU clusters. |
| [**genai-cli**](https://github.com/ADITYAKUMARRAI2007/genai-cli) | A tool-calling agent CLI with chain-of-thought execution. |

## Toolbox

<p>
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white" alt="PyTorch">
  <img src="https://img.shields.io/badge/vLLM-30A2FF?style=flat-square" alt="vLLM">
  <img src="https://img.shields.io/badge/Hugging_Face-FFD21E?style=flat-square&logo=huggingface&logoColor=black" alt="Hugging Face">
  <img src="https://img.shields.io/badge/LoRA_%2F_TTT-6E40C9?style=flat-square" alt="LoRA / test-time training">
  <img src="https://img.shields.io/badge/timm-0A66C2?style=flat-square" alt="timm">
  <img src="https://img.shields.io/badge/Unsloth-111111?style=flat-square" alt="Unsloth">
  <img src="https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white" alt="NumPy">
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python">
</p>

## Get in touch

- Competition work: [Kaggle](https://www.kaggle.com/adityakumarrai0401)
- Code and write-ups: [GitHub](https://github.com/ADITYAKUMARRAI2007)
- Questions about a solution: open an issue in its repository.

<p align="center">
  <a href="https://github.com/ADITYAKUMARRAI2007/compute-allocation-arc-agi-2">ARC-AGI-2</a>
  ·
  <a href="https://github.com/ADITYAKUMARRAI2007/label-repair-knee-mri">Knee MRI</a>
  ·
  <a href="https://github.com/ADITYAKUMARRAI2007/kaggle-competition-playbooks">Playbooks</a>
  ·
  <a href="https://www.kaggle.com/adityakumarrai0401">Kaggle</a>
</p>
