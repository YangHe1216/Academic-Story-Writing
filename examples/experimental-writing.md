# Example — Controlled Experiment → Results Paragraph

> **Synthetic teaching example:** the following measurements and method names are invented. They do not represent a real paper, benchmark, or evaluation of the Academic Story Writing Skill.

## Input notes

Central story: structured coupling helps representation learning under the evaluated protocol.

- Dataset: D; fixed training/validation split.
- All compared configurations use the same preprocessing, compute budget, metric, and random seed.
- Full model: 81.2 accuracy units (assume percentage points for this pedagogical illustration).
- Remove component X: 79.8.
- Only specified architecture difference: X enabled vs disabled.
- No multi-seed or cross-dataset measurements supplied.

## Anti-pattern

> Although our method may potentially yield gains, the observed difference could be due to dataset-specific effects, and multiple seeds and additional datasets are necessary before the contribution of X can be discussed.

Problems: mixes within-D observation with cross-dataset generalization; raises a requirement not tied to the current claim; buries the observed result. It also overlooks that the same dataset was used in both compared arms. It would still be inappropriate to infer a population-level advantage without considering stochastic variance.

## Academic Story Writing Results paragraph

> Under the matched protocol on dataset D, the full model achieves 81.2, compared with 79.8 after removing component X, a difference of 1.4 percentage points. This ablation supports the contribution of X to performance in the evaluated configuration and is consistent with its intended role in the proposed formulation.

Why the wording is calibrated:
- States the measured difference directly.
- Does not claim performance is consistent **across seeds or datasets**.
- "Consistent with its intended role" does not claim the experiment proves the hypothesized mechanism.
- A specific concern about leakage, stochastic variability, or a mismatched control would justify local corrections **if supported by facts**, not generic reviewer theater.

## When additional evidence really is needed

If the target claim changes to **"X reliably improves expected performance across random initializations"**, one fixed-seed run is generally not enough. Repeated runs or suitable uncertainty estimates become relevant. If the claim changes to **"X generalizes across domains"**, evidence from additional domains or a defensible generalization analysis becomes relevant. The experiment requirement follows the **claim**, not a universal reviewer checklist.

## Reusable prompt

```text
$academic-story-writing
PRESERVE + WRITER. Turn these controlled-experiment records into a concise Results paragraph.
Report the actual contrast and connect it to our main story.
Separate within-setting observations from across-seed or cross-domain claims.
Do not add speculative demands for more datasets, ablations, or seeds.
Keep genuine statistical/design limitations when material.
```
