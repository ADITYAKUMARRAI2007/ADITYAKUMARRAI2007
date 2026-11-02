<p align="center"><img src="assets/banner.svg" alt="Aditya Kumar Rai" width="100%"></p>

### Research interests
**Reasoning under compute constraints** (test-time training, long chain-of-thought, budget allocation, abstraction benchmarks) · **learning from noisy labels in medical imaging** · **efficient inference** of large models on small GPUs.

I like questions with a clean measurable answer: *where should the next GPU-hour go?* *Is the bottleneck the model or the labels?* *When does a validation set stop telling the truth?*

---

### Research

<table>
<tr>
<td width="38%" valign="top"><a href="https://github.com/ADITYAKUMARRAI2007/compute-allocation-arc-agi-2"><img src="assets/arc_compute_split.svg" width="100%"></a></td>
<td valign="top">

**Where Should the Compute Go? Test-Time Training vs. Long Reasoning on ARC-AGI-2**<br>
<sub>Technical report, 2026</sub>

Under a fixed offline budget (12 h, 4 × 24 GB GPUs), moving time from a test-time-trained 4B model to a 27B reasoning model raised ARC-AGI-2 hidden-set accuracy **29.7% → 33.2%**. Effort settings are non-monotonic (a chat-template artefact), long reasoning needs 60–100k tokens, and most errors are wrong hypotheses that answer selection can't recover. Includes an in-place ELF patch to run a glibc-2.38 engine on glibc 2.35.

[report](https://github.com/ADITYAKUMARRAI2007/compute-allocation-arc-agi-2/blob/main/docs/REPORT.md) · [code](https://github.com/ADITYAKUMARRAI2007/compute-allocation-arc-agi-2)
</td>
</tr>
<tr>
<td width="38%" valign="top"><a href="https://github.com/ADITYAKUMARRAI2007/label-repair-knee-mri"><img src="assets/rsna_private.svg" width="100%"></a></td>
<td valign="top">

**Label Repair over Architecture Search: Multi-Finding Knee MRI Classification under Noisy Labels**<br>
<sub>Technical report, 2026</sub>

With weak, report-derived labels for 12 knee-MRI findings, four new architectures (3D, 2.5D, distilled) never earned blend weight, while relabelling the noisiest findings and per-finding specialists raised held-out macro AUC **0.942 → 0.944**. A 58-study expert set ranks models correctly but cannot resolve < 0.003 AUC.

[report](https://github.com/ADITYAKUMARRAI2007/label-repair-knee-mri/blob/main/docs/REPORT.md) · [code](https://github.com/ADITYAKUMARRAI2007/label-repair-knee-mri) · [inference notebook](https://www.kaggle.com/code/adityakumarrai0401/rsna-knee-label-ft-coatnet-specialists-blend)
</td>
</tr>
<tr>
<td width="38%" valign="top"><a href="https://github.com/ADITYAKUMARRAI2007/compute-allocation-arc-agi-2"><img src="assets/arc_effort.svg" width="100%"></a></td>
<td valign="top">

**Note: reasoning effort is not monotonic**<br>
<sub>Short note, 2026</sub>

For Qwen3.8-27B on ARC-AGI-2, `medium` effort scores below `low` because the chat template injects instructions only for `low` and `xhigh`. A one-line configuration choice moves accuracy by ~3×, so check what an "effort" knob actually changes before using it.
</td>
</tr>
</table>

---

### Things I believe more strongly after this year
1. **Measure on the distribution you will be judged on.** Small public validations mispredicted held-out results in both projects, in both directions.
2. **Allocation and budgets beat harness cleverness** for reasoning models at fixed cost.
3. **Generation bounds selection.** If the right answer is never produced, no judge, vote or reranker can find it.
4. **Labels are a model component.** For noisy medical data, fixing the weakest labels moved held-out metrics when new architectures did not.

### Playbooks
**[kaggle-competition-playbooks](https://github.com/ADITYAKUMARRAI2007/kaggle-competition-playbooks)**: 25 structured research playbooks (validation design, label engineering, ensembling, vision, LLMs, time series, …) distilled from top solutions, with case studies.

### Also building
Agent systems: [orderguard](https://github.com/ADITYAKUMARRAI2007/orderguard) (deterministic authorization for autonomous commerce agents) · [thermal-chaos-arena](https://github.com/ADITYAKUMARRAI2007/thermal-chaos-arena) (control benchmark for fragile GPU clusters) · [genai-cli](https://github.com/ADITYAKUMARRAI2007/genai-cli) (tool-calling agent CLI).

<sub>Benchmarks used: ARC Prize 2026 (ARC-AGI-2) and RSNA Knee Abnormality Detection 2026, both hosted on Kaggle ([adityakumarrai0401](https://www.kaggle.com/adityakumarrai0401)).</sub>
