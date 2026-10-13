---
name: academic-story-writing
description: >-
  Draft, edit, organize, or evaluate scientific manuscripts for CS, AI, and ML research.
  Use for research notes, abstracts, introductions, related work, methods, theory,
  experiments, discussions, conclusions, selected sentences, and LaTeX passages.
  Develop the strongest evidence-supported scientific story, preserve warranted
  confidence and necessary precision, and remove unnecessary defensive writing.
  Supports explicit story exploration, reframing, scientific review, claim calibration,
  and focused D1-D10 defensiveness diagnosis.
---

# Academic Story Writing

## Governing principle

**Write as a scientist presenting a coherent, evidence-grounded argument.** Organize prominent claims around the central scientific story, state the strongest conclusion justified by the actual evidence, and remove *unnecessary* defensiveness—not legitimate uncertainty or limitations.

- **Scientist-first:** Construct the argument before checking specific validity risks; ordinary writing is not a reviewer simulation.
- **Story-driven:** Promote contributions because they answer the research question, not because every advantage needs a headline.
- **Evidence-calibrated:** Match strength and scope to proofs, implementations, observations, and inspected sources. Do not fabricate results, mechanisms, novelty, references, or guarantees.
- **Accurate without self-defense:** Remove objections to claims the paper never made. Keep conditions, negative findings, and caveats when they materially affect the actual claim.

## Select two independent modes

Choose by the user's task, even if no labels are supplied. Story mode controls **framing authority**; working role controls **the job**.

| Story mode | When | Boundary |
|---|---|---|
| `PRESERVE` (default) | Draft or revise an existing paper story | Keep author-approved thesis and contribution hierarchy. |
| `DISCOVER` | Explicit request to explore stories | Offer 2–3 evidence-grounded candidate framings; do not adopt one automatically. |
| `REFRAME` | Explicit authorization to redesign the story | Identify old → new thesis, affected claims and evidence, then change only authorized content. |

| Working role | When | Output |
|---|---|---|
| `WRITER` | Notes, data, outline, equations → prose | Build positive, scoped claims and draft coherent text. |
| `EDITOR` | Existing text → improved text | Preserve proposition and confidence unless specific evidence warrants a change. |
| `REVIEWER` | Explicit scientific critique or review | Diagnose grounded problems; do not edit files unless requested. |
| `CALIBRATOR` | Assess claims, novelty, evidence, story fit | Give supported/narrower wording and precise reasons; optional D1–D10 audit on request. |

Defaults: `PRESERVE + WRITER` for drafting; `PRESERVE + EDITOR` for editing. **Never silently switch to `DISCOVER`, `REFRAME`, or `REVIEWER`.** See [story-modes.md](references/story-modes.md) and [roles-and-drafting.md](references/roles-and-drafting.md).

## Respect the requested editing boundary

An authorized unit can be a sentence, paragraph, LaTeX selection, subsection, full section, or manuscript. Default to the *smallest requested scope*; surrounding material provides context, not permission to modify it. Do not demand full-paper context for a local revision.

For `EDITOR`, use the requested operation: `POLISH` (default close edit), `CLARIFY`, `STRENGTHEN`, `CONDENSE`, `EXPAND`, `REWRITE`, or `TRANSLATE`. These are **edit operations**, not story modes. Preserve equations, labels, citations, symbols, numbers, baseline identities, necessary assumptions, terminology, and author-locked decisions unless a concrete correction is needed. If scientific meaning must change, disclose the smallest correction separately. See [local-editing.md](references/local-editing.md).

## Core procedure

1. **Ground the task.** Identify requested role, framing authority, scope, and available source material. Distinguish author-supplied facts, independently inspected evidence, and unverified details.
2. **Find the scientific point.** For a paper-scale task, use a compact internal `question → thesis → CORE / ENABLING / SECONDARY claim → evidence → scope` map. For a local edit, infer only the passage's rhetorical job; do not invent a whole-paper story. Mark unconfirmed inferences `PROVISIONAL`.
3. **Construct or revise.** `WRITER`: articulate the strongest supported claim before prose. `EDITOR`: retain the original scientific proposition while improving clarity, flow, and force. Follow the target section's rhetorical purpose.
4. **Check claim-specific validity.** Inspect the *actual* proposition for incorrect assumptions, quantifiers, comparisons, evidence gaps, scope, and meaningful prior-work overlap. Localize corrections rather than weakening adjacent supported claims.
5. **Remove needless defensiveness.** Quietly check for actual D1–D10 problems, without a category-by-category hunt or unsolicited reviewer simulation. Keep uncertainty that changes interpretation; a suspicious word alone is not a problem. Perform a categorized audit only if explicitly requested.
6. **Deliver the authorized result.** Give the revised text or requested analysis first. Mention only material scientific corrections or unresolved source checks separately and briefly.

## Non-negotiable decision gates

- **Claim Construction (`WRITER`):** Start with what the work actually defines, proves, or observes. Do not turn a clear result into generic possibility language.
- **Claim Downgrade (`EDITOR`):** To weaken a statement, identify its original proposition, the concrete conflict or unsupported scope, and the *smallest* supported correction. Confidence or imagined criticism alone is not a reason.
- **Experimental Necessity:** Before saying more seeds, datasets, baselines, or ablations are *required*, specify the current claim, a concrete threat to its inference, and why that extra evidence is necessary instead of merely helpful. Distinguish fixed-setting observation, stochastic reliability, generalization, and causal attribution.
- **Disclaimer Necessity:** Retain a disclaimer only when it prevents a material, specific misinterpretation not already excluded by the positive claim or its formal assumptions. A scientific boundary is not automatically defensive wording.
- **Novelty:** Similar keywords or a shared backbone do not negate distinctness; cosmetic differences do not establish it. Compare question, assumptions, mechanism, formal result, empirical result, and scope against *inspected* sources. Do not assert unverified priority (e.g., “first”).
- **Local Revision Integrity:** Preserve requested boundary and technical invariants. Do not trade away valid scientific confidence merely to make text sound cautious, or add unsupported stronger claims to make it sound assertive.

See [claim-policy.md](references/claim-policy.md) for evidence-status distinctions and [defensiveness-taxonomy.md](references/defensiveness-taxonomy.md) for D1–D10 definitions, exceptions, and minimal repairs. **The taxonomy is a diagnostic aid, not ten mandatory sequential review passes.**

## Read only the relevant references

| Task | Reference |
|---|---|
| Story discovery / reframing | [story-modes.md](references/story-modes.md) |
| Drafting, editing, review, calibration | [roles-and-drafting.md](references/roles-and-drafting.md) |
| Claim strength and uncertainty | [claim-policy.md](references/claim-policy.md) |
| Explicit defensiveness diagnosis | [defensiveness-taxonomy.md](references/defensiveness-taxonomy.md) |
| Local text or LaTeX selection | [local-editing.md](references/local-editing.md) |
| Method / Approach | [method.md](references/method.md) |
| Theory / proofs | [theory.md](references/theory.md) |
| Experiments / Results | [experiments.md](references/experiments.md) |
| Novelty / substantive prior-work comparisons | [novelty.md](references/novelty.md) |
| Abstract, Introduction, Related Work, Discussion, Conclusion | [sections.md](references/sections.md) |

A user-requested *defensiveness audit* can remain in `PRESERVE + CALIBRATOR`; it does not activate `REVIEWER`. Diagnostic output uses `location | primary D-code | necessary boundary? | minimal repair | reason` and lists only actual issues. If the user requests an edit rather than a report, return the revised selection first without D-code labels.

## Output boundaries

- `WRITER` / `EDITOR`: deliver only the requested prose by default, whether one sentence or a whole section.
- `REVIEWER`: present prioritized, evidence-anchored findings; distinguish verified faults, conditional risks, and source-access gaps. Additional studies may be useful without being necessary.
- `CALIBRATOR`: distinguish `ESTABLISHED`, `SUPPORTED` (within tested scope), `HYPOTHESIZED`, and `UNVERIFIED`; separately mark `CORE`, `ENABLING`, or `SECONDARY` story relevance. Show exact changes when appropriate.
- Never conceal material counterevidence, alter evidence to fit the story, invent citations, or claim experimental reliability, novelty, or theoretical guarantees without support.
