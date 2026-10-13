# Local Academic Text Optimization

## Purpose

Support a standalone **sentence, two sentences, paragraph, multi-paragraph excerpt, LaTeX selection, subsection, or a named range in an academic manuscript**. Use `PRESERVE + EDITOR` for existing text and `PRESERVE + WRITER` for notes or experimental records.

## Local Edit Contract

Given the user's selected text and request, determine silently:

1. **Boundary:** exactly which content may be edited? A quoted span, selected range, a paragraph, or a section? Do not modify adjacent paragraphs or unrequested files.
2. **Operation:** `POLISH` (default: minimal changes), `CLARIFY` (make logic explicit), `STRENGTHEN` (more direct, evidence-grounded contribution framing), `CONDENSE`, `EXPAND`, `TRANSLATE`, or `REWRITE` (within selection). User-specific instructions override these labels.
3. **Rhetorical role:** statement of problem, limitation, insight, design, formal result, experimental observation, interpretation, related-work comparison, or transition.
4. **Invariant content:** technical meaning, evidence/scope, numbers, units, variable names, math, assumptions, equation labels, references, citations, terminology, author-set thesis.
5. **Output size:** return only the edited span by default. If requested, give a before/after table, diff, or a brief change rationale. Do not force those on an ordinary editing request.

## Sentence- and Phrase-Level Procedure

- Preserve the original proposition; remove filler and unjustified `may/might/potentially/arguably` when the source supports a direct statement.
- Improve subject–verb clarity, verb choice, information order, concision, and linkage to the research point.
- Keep scientifically necessary uncertainty: unknown mechanisms, statistical variability, unverified novelty priority, or theorem assumptions.
- Do **not** replace a local sentence with an entirely new scientific argument, an invented motivation, or a reviewer disclaimer.
- Do **not** silently upgrade `correlates with` to `causes`, a per-dataset result to broad generalization, an intended design to a proved property, or a mathematical observation to a theorem.

## Paragraph- and Excerpt-Level Procedure

- Preserve topic and function, then ensure `main point → supporting mechanism/evidence → implication` where appropriate. This is a flexible structure, not a requirement to add three sentences.
- Remove redundant setup, repeated disclaimers, generic defensive qualifiers, and unrelated selling points.
- Improve topic sentences, transitions, and logical sequencing **within the authorized selection**.
- Avoid inventing new citations/results or assuming missing paper-wide details. If surrounding context is available, use it to maintain terminology and avoid contradictions.
- If the original content is already good, make small edits rather than a stylistic overhaul.

## Draft Fragments → Focused Prose

For bullet points, notes, equations, or result fragments, build the strongest warranted local claim before writing. Convert them to the exact requested output length (e.g., one sentence, one paragraph, or a short explanation). Avoid the reflex to say “further datasets/seeds/ablations are needed” unless the specific authored claim requires those data, as defined in [experiments.md](experiments.md).

## Technical and LaTeX Preservation

- Keep `$...$`, `\(...\)`, `\[...\]`, `\begin{...}` / `\end{...}`, `\label{...}`, `\ref{...}`, `\eqref{...}`, `\cite{...}`, macros, and math operators intact unless asked to fix them.
- Do not change a symbol's identity, sign, condition, or quantifier to smooth English.
- Preserve exact measured values, dataset names, baseline identities, and uncertainty notations.
- If a mathematical/citation element appears inconsistent, correct only when supported or flag it in a **separate, compact note**.

## Examples (Hypothetical — Claims Must Be Verified in Actual Work)

### One-sentence Method polish

Input: “We try to use X to maybe handle the constrained representation issue.”

Preferred when the design genuinely does this: “We introduce X to address the constrained representation problem.”

This states the design purpose, not an empirical guarantee that X solves the problem.

### Controlled experimental comparison

Input: “With all configurations matched, X is better on D, but there might be dataset effects so extra datasets are needed.”

Preferred when the matched comparison and outcome are supported: “Under the matched experimental protocol, X achieves higher [metric] than the baseline on dataset D.”

Do not assert cross-dataset transfer; do not demand other datasets to report a within-D comparison. If the actual setup has an uncontrolled difference, flag that particular problem.

### Theory statement

Input: “We do not claim universal convergence; under A1–A3, we can show convergence to a stationary point.”

Preferred when the theorem is valid: “Under Assumptions A1–A3, the proposed algorithm converges to a stationary point.”

The assumption boundary remains, without an extra rhetorical apology.
