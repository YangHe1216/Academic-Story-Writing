# Experimental Writing and Claim-Specific Evidence Sufficiency

**Evaluate the experiment against the exact proposition being made, not an imagined stronger claim.** Do not turn every theoretically possible dataset, seed, baseline, ablation, or robustness check into a prerequisite for reporting a narrow supported result.

## First Determine the Kind of Claim

| Claim being written | Typical evidence needed |
|---|---|
| **Observed run**: “In configuration P, X obtains metric M.” | Actual record of that run and metric. |
| **Matched comparison**: “In setting D/P, X outperforms B.” | Faithful matched design, measured outcomes, relevant controls; distinguish association from strong causation. |
| **Across-run stability / average superiority** | Repeated or appropriately modeled stochastic variation; one seed alone is usually insufficient for such claims. |
| **Across-dataset/domain generality** | Multiple relevant contexts or a suitable generalization argument; a single fixed dataset does not establish this. |
| **Causal component mechanism/necessity** | Appropriate intervention or identification logic; measured improvement alone may not establish mechanism. |
| **Theorem** | A valid proof with assumptions; seeds do not validate a logical theorem. |

## Experimental Necessity Gate

Before writing “more tests are required” or downgrading a result, answer:

1. **Exact inference:** What is the author actually claiming—not what a stronger possible paper might claim?
2. **Specific threat:** What concrete feature of design/data/analysis threatens *that* inference (data leakage, unequal resources, changed preprocessing, selection bias, incompatible evaluation, stochastic instability, missing requisite assumptions, etc.)?
3. **Necessity:** Would the proposed extra experiment genuinely resolve the threat to the **current** claim, or only broaden scope/precision/replicability?

Classify proposed follow-up as `ESSENTIAL`, `OPTIONAL`, or `NOT RELEVANT` to the specific claim. In `WRITER`, do not insert the classification into prose unless a limitation is required to avoid misstatement. In `REVIEWER`, report the reasoning concisely.

## Controlled Dataset Example

Same dataset D, split, preprocessing, training budget, and metric; the experimental intervention toggles X. The dataset is held fixed across arms and **is not by itself an uncontrolled between-arm confounder**. This allows a bounded contrast such as “Under matched protocol P on D, enabling X improves M relative to the ablated configuration,” if the results support it.

This design does **not** prove generalization to all datasets, rule out leakage, remove all stochastic variability, or establish mechanism automatically. Dataset-specific interactions may still limit transportability. Do not use this separate generalization limitation to invalidate the correctly scoped within-D observation.

## Random Seeds Example

One fixed-seed stochastic run can support “In the reported run, X obtained M”; it typically cannot support “X reliably outperforms B across random initializations” or a population-average conclusion. Extra seeds may be important when effects are small relative to plausible run variability or when stability is a **central claim**. Identify that precise concern instead of automatically calling every single-seed result invalid.

A matched seed can control part of comparison variability; it cannot establish robustness to other random draws. If training and evaluation are deterministic, multiple seeds may add no information about that deterministic property.

## Writing Results without Reviewer Theater

1. State the comparison and relevant experimental conditions.
2. Report the observed direction and magnitude **using only supplied values**.
3. Interpret the result in relation to the paper's core scientific claim.
4. Connect ablations or analyses to the mechanisms they truly probe; do not leap from one outcome to a causal explanation.
5. State real negative findings/contradictions proportionately; never bury them to protect the story.
6. Omit generic appendices-in-prose such as “further datasets and multiple seeds are needed to validate this finding” unless the manuscript's actual claim requires them.

**Example — avoid:** “The component might contribute to improvements, but we cannot exclude dataset effects and would need additional datasets and seeds.”

**Prefer when warranted:** “On D, activating X improves M by [observed change] under the matched comparison. This result is consistent with the design objective [Y].” Avoid claiming causal mechanism or cross-dataset reliability unless separately supported.

## Reviewer Boundary

A proper reviewer may recommend optional replication, robustness, and stronger generalization. It must clearly distinguish an **essential validity threat** from “this would make the paper stronger.” In particular, “some reviewer might demand it” is not an experimental sufficiency argument.
