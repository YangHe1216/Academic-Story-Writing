# Writing Roles and Draft-to-Prose

Choose one working role for the requested output. Perform a focused scientific correctness check inside `WRITER` and `EDITOR` without adopting `REVIEWER` behavior.

## WRITER — Construct Before Hedging

For notes/bullets/outline/technical drafts:

1. Extract the scientific point and the paragraph's job (problem, gap, insight, construction, theorem, result, or implication).
2. Build a compact internal claim map: `claim → evidence/source → exact scope → story relevance`.
3. Choose the most direct justified verb: `define`, `introduce`, `derive`, `prove`, `obtain`, `observe`, `demonstrate on [tested setting]`; use `hypothesize` only for a hypothesis. Do not use `may/might/potentially` as generic academic style.
4. Draft a topic sentence that **says something**. Connect rationale, technical detail, and evidence to that point. End with its scientific implication when useful.
5. Perform a narrow integrity check: is any statement stronger than its source? If so, correct only that statement; do not dilute neighboring supported contributions.
6. Return the prose first. If crucial information is missing, insert a specific placeholder or separately flag the exact claim needing verification. Do not invent content to hide gaps.

**When inputs are author-provided but not independently verified:** you can draft based on those supplied premises without claiming you have confirmed them. Do not automatically distrust and weaken *every* premise merely because notes are rough.

### Draft conversion example

Notes (hypothetical): “Component X; same dataset/split; +∆ metric with X; central story is controllable representation.”

Unhelpful: “We explore a potentially useful component that may provide improvements, although additional datasets and seeds could be needed to validate the finding.”

Better, with ∆ replaced by the actual supplied result: “Under the matched evaluation protocol, adding component X improves [metric] by [measured difference]. This supports its role in [specific design objective].”

This **does not** establish cross-dataset generality or cause of the performance difference unless separate evidence supports those claims. Do not add those unmade claims or preemptively apologize for them.

## EDITOR — Protect Warranted Confidence

**Local passage editing is a first-class task.** For a user-selected phrase/sentence/paragraph, identify the single communicative purpose and revise within that boundary. Do not automatically broaden to the full section or start a paper-wide review. When the user says only “optimize this wording,” choose a close rewrite with minimal semantic change; when they explicitly request a deeper rewrite, improve the logical sequence **within the selection**. See [local-editing.md](local-editing.md).


- Start from the author's exact proposition and section function.
- Improve clarity, specificity, logical sequence, transitions, and economy **without changing epistemic strength by reflex**.
- Before changing `we prove/show/establish` into `we suggest/may`, invoke the Claim Downgrade Gate from `SKILL.md`. Explain material changes in a short note.
- Maintain numbers, notation, assumptions, citations, and author-locked choices. If a source contradicts a claim, localize the correction; do not rewrite the whole manuscript as defense.
- For Method writing, keep direct descriptions of the algorithm. For Theory, retain legitimate quantifiers. For Experiments, preserve exact tested conditions.

## REVIEWER — Only on Request

Switch to a critical-evaluation role **only when explicitly requested**. For each important issue, provide: `exact claim`, `specific inspected evidence or missing assumption`, `consequence for that claim`, `minimal decisive correction/check`. Classify:

- `VERIFIED ISSUE`: direct contradiction, invalid proof step, confounded comparison, substantive overlap in inspected source.
- `CONDITIONAL RISK`: matters only under an explicit condition; say which and how it could be resolved.
- `SOURCE NEEDED`: cannot establish an answer with available documents.

Prioritize substantive objections; do not pad findings to look comprehensive. Separate required corrective actions from optional extra evidence. Diagnose by default; **do not edit source files** unless asked.

## CALIBRATOR — Claim and Story Auditor

For each prominent sentence assess: `story role` (CORE / ENABLING / SECONDARY), `evidence status` (ESTABLISHED / SUPPORTED / HYPOTHESIZED / UNVERIFIED), `verified novelty relation` (if available), and recommended `KEEP / STRENGTHEN / NARROW / DE-EMPHASIZE / VERIFY`. Provide exact before/after text and specific justification. Do not assert acceptance predictions.

For a **specific defensiveness diagnosis** rather than broad critique, use [defensiveness-taxonomy.md](defensiveness-taxonomy.md) and keep the D-code analysis separate from manuscript text. It does not activate the `REVIEWER` role.
