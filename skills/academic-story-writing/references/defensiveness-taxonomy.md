# Defensiveness Taxonomy and Scoped Repair (D1–D10)

**Purpose:** Find and correct writing that weakens an otherwise warranted scientific argument without adding necessary precision. This is a *claim-level, context-sensitive* writing aid, **not** a keyword blacklist, a substitute for scientific validity checks, a second reviewer persona, or permission to strengthen unsupported claims.

Use this reference when (a) defensive phrasing is detected in writing or editing, (b) a user requests a more direct/confident revision, or (c) an explicit defensiveness audit is requested. For ordinary writing, apply the lightweight safeguards silently; do not emit category labels or inspect every possible objection. For a user-requested audit, provide actionable categories and exact before/after changes.

## Shared decision procedure

For a suspicious sentence, determine:

1. **Scientific proposition:** What exactly is asserted or intended (construction, proof, measured result, mechanism, novelty, scope)?
2. **Current evidence and boundary:** What do the supplied equations, experiments, code, or verified literature establish? What remains unknown?
3. **Sentence's job:** Does the caveat provide a necessary assumption, material limitation, conceptual contrast, uncertainty source, reproducibility detail, or interpretive warning? If yes, keep it, possibly shorter or moved closer to its claim.
4. **Defense trigger:** Is the sentence defending against a stronger *unmade* claim, an unsupported imagined reviewer challenge, or the mere possibility of doubt? If yes, consider it a candidate for repair.
5. **Smallest valid repair:** Preserve the narrowest supported proposition, the original story, technical precision, and the user-selected editing scope. Delete only genuinely redundant matter, use positive scope, or state a direct observation. Do not erase necessary uncertainty.

A detector hits only when context confirms **unjustified defensive function**. Do not tag words such as `may`, `suggests`, `only`, `under`, `however`, `limitations`, or `not` by lexical match alone.

## Defensiveness categories

### D1 — Unnecessary Disclaimer / 多余免责声明
- **Signature:** Repeatedly denies broad conclusions that the paper never makes, after the actual claim's scope is already explicit.
- **Boundary to keep:** A warning essential to interpret a theorem, avoid reader confusion, or disclose a relevant limitation; one precisely placed scope condition.
- **Repair:** State the studied regime/guaranteed domain positively, deleting surplus denials.
- **Example:** `We do not claim the method works for every domain.` → `We evaluate the method on domains D1 and D2.` *(only if that is the reported scope; do not substitute a result).* 

### D2 — Unwarranted Hedging / 无依据削弱结论
- **Signature:** Layers of `may`, `might`, `potentially`, `perhaps`, `appears` obscure a directly implemented operation, established theorem, or recorded result.
- **Boundary to keep:** Real statistical uncertainty, unverified mechanism, correlation-not-causation, inaccessible sources, probabilistic theorem, or tentative proposal.
- **Repair:** Match the verb to the evidence: `define/derive/prove` for appropriate formal work, `observe/obtain` for data, `hypothesize` for an unverified explanation. Quantify/localize uncertainty instead of stacking hedges.
- **Example:** `Our algorithm may potentially minimize term L.` → `The algorithm optimizes objective L using the update in Eq. (3).` *(only if the algorithm actually does so; do not claim global optimum).* 

### D3 — Self-Deprecating Contribution Language / 自我贬低
- **Signature:** `merely`, `just`, `only`, `simple` are used to rhetorically downgrade a relevant, grounded scientific contribution rather than describe objective constraints.
- **Boundary to keep:** `only` as a genuine quantifier, `simple` for measured/defined complexity, or honest distinction between a baseline and new mechanism.
- **Repair:** Name the exact design, result, or distinction; do not inflate novelty or erase shared components.
- **Example:** `We merely add a regularizer to a standard backbone.` → `We add regularizer R to the backbone to impose constraint C.` *(novelty remains a separate question).* 

### D4 — Imaginary Reviewer Defense / 假想审稿人防御
- **Signature:** Prose anticipates objections not requested by the user and not grounded in a concrete mismatch: `reviewers may ask...`, speculative rebuttal paragraphs, preemptive defenses.
- **Boundary to keep:** A material real issue with inspected evidence; a requested rebuttal or explicit `REVIEWER` task; critical context required for valid interpretation.
- **Repair:** Remove the hypothetical objection from manuscript prose; present a concrete issue only outside the revised text when necessary.
- **Example:** `A reviewer might object that module R is not new.` → `Module R implements the coupling defined in Eq. (4).` *(if true; don't manufacture novelty).* 

### D5 — Unnecessary Evidence Demands / 实验要求膨胀
- **Signature:** Treats extra datasets/seeds/baselines/ablations as automatic prerequisites for a narrower demonstrated claim.
- **Boundary to keep:** Evidence genuinely essential for the **actual** inference: a reliability claim over seeds, cross-domain generalization, causal attribution, fair comparison, identifiable stochastic instability, or incompatible protocols.
- **Repair:** Distinguish `ESSENTIAL`, `OPTIONAL`, and `NOT RELEVANT` to the stated claim; report the supported finding. Suggest a new experiment only with an exact validity threat and an explanation of why it is necessary.
- **Example:** `Without more datasets we cannot conclude anything.` → `On dataset D under protocol P, enabling X yields a measured improvement of Δ.` *(if records support it; cross-dataset claims require more).* 

### D6 — Repetitive Defensive Framing / 重复性防御
- **Signature:** Caveats recur after already being made clearly, or paragraph after paragraph returns to a nonclaim/limitation without adding new information.
- **Boundary to keep:** Repeating a condition where mathematically necessary for standalone theorem statements, figures, or results, or when the reader otherwise misinterprets the claim.
- **Repair:** State the limitation once at the appropriate point; let subsequent sentences advance the scientific argument.
- **Example:** Four consecutive sentences explaining that a bound is not a global optimality guarantee → one precise convergence statement with its necessary assumptions.

### D7 — Surface-Similarity Novelty Retreat / 表面相似导致的创新性退缩
- **Signature:** Method-name, architecture-family, or keyword similarity to prior work automatically downgrades novelty, even when research question, assumptions, mechanism, or guarantee differ.
- **Boundary to keep:** Verified substantive overlap from the actual inspected prior work; unverified `first/novel/unprecedented` priority cannot be asserted as established.
- **Repair:** Specify overlap and distinctness **dimension by dimension**, then defend only the meaningful demonstrated contribution. See `novelty.md`.
- **Example:** `Since both use Transformers, our novelty may be limited.` → `Both approaches use Transformer encoders; our formulation differs in [verified objective/mechanism/result].` *(fill only verified differences).* 

### D8 — Method-Design Apology / 方法设计式自我辩解
- **Signature:** Method prose spends more space defending conventional modules, heuristic choices, missing ablations, or lack of optimality than explaining the algorithm itself.
- **Boundary to keep:** Real prerequisites for an algorithm to operate, necessary reproducibility information, real approximation conditions, or an empirical component-necessity claim requiring an ablation.
- **Repair:** Explain objective → construction → component role → intended mechanism. Separate observed effects from design intent. See `method.md`.
- **Example:** `We only use a heuristic and do not prove optimality.` → `We optimize the objective using the alternating update in Algorithm 1.` *(if this accurately describes an approximate solver; do not claim guaranteed optimum).* 

### D9 — Theory-Boundary Inflation / 理论边界膨胀
- **Signature:** Theorem and derivation prose repeatedly describes what was *not* proved rather than first stating what is actually established.
- **Boundary to keep:** Assumptions, quantifiers, convergence mode, rates, domain, probability level, approximation gap, sufficient-vs-necessary distinctions, and the explicit distinction between diagnostic analysis and proof when it changes the reader's interpretation.
- **Repair:** Lead with the exact theorem or calculated property and the conditions for which it holds. Consolidate true limitations once where they change interpretation. See `theory.md`.
- **Example:** `We do not establish global optimality; this is only a stationary-point result.` → `Under A1–A3, Theorem 2 guarantees convergence to a stationary point.` *(assuming the theorem proves precisely this).* 

### D10 — Uncertainty Spillover and Story Hijack / 不确定性蔓延与主线偏移
- **Signature:** A single unverified novelty priority, possible mechanistic explanation, or secondary metric causes all of Introduction/Method/Results/Conclusion to become tentative or a peripheral caveat becomes the paper's organizing theme.
- **Boundary to keep:** A genuine contradiction that undermines the central thesis; adverse outcomes that are necessary to interpret the main claim.
- **Repair:** Locate the uncertain *subclaim*, limit **only that proposition**, preserve independent formal/empirical results and story prominence. Explain a material story-level problem separately if necessary.
- **Example:** `Because 'first' is unverified, our empirical contribution is uncertain.` → `The method achieves [measured outcome] under [tested protocol]. Its priority relative to prior work remains to be verified.` *(outside manuscript if the priority caveat is not needed in the paragraph).* 

## Prioritization and overlap rules

- Tags may co-occur, but **choose one primary diagnosis**: D4 for imagined objection origin, D5 for mandatory extra-experiment demand, D2 for confidence-calibration wording, D6 for recurrence, D7 for superficial related-work inference, D8/D9 for the section-specific failure, D10 for story-wide spillover.
- **High priority:** demonstrably incorrect scientific inference or unsupported alteration of confidence (including D5, D7, D9, D10 when material). Correct the claim, not merely the wording.
- **Medium priority:** rhetoric that obstructs the central point (D1–D4, D6, D8 without scientific distortion). Apply minimal rewrite.
- **No issue:** limitation is essential for meaning, reproducibility, a verified source conflict, or ethics. Do not remove it to satisfy a confidence target.

## Audit output (only when requested)

Return `location | primary D-code | evidence-based necessity judgment | smallest justified revision | reason` for actual findings; do not force all ten categories or output a diagnosis during ordinary drafting. An audit alone does not authorize edits. When editing is requested, preserve selection boundaries and return revised prose first.

**Guardrail:** rhetorical confidence cannot substitute for proof, measured reliability, a causal design, or verified novelty. Do not convert correlation to causation, a single observed run to population superiority, or a standard combination to “first” without evidence.
