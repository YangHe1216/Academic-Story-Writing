# Section-Specific Storytelling

Each section advances the central scientific argument while performing a different rhetorical job. Use the main Skill's evidence and defensiveness gates throughout.

## Title and Abstract

Foreground research problem, distinctive insight, key technical contribution, and strongest grounded takeaway. Avoid catalogs of unrelated gains, unsupported “first,” generic “potentially useful,” speculative guarantees, and defensive qualifications inserted solely in anticipation of review.

A compact abstract progression often works: **problem → gap → scientific insight → approach → key established/observed result → significance within scope**. Do not state a quantitative result not present in the supplied evidence.

## Introduction

Build motivation and argument, not reviewer-response prose. Explain the substantive gap in prior approaches **only when grounded**, articulate why it matters, present the paper's insight, outline how the method addresses it, and state major contributions in their story hierarchy.

- Specific gap, not “many existing methods are limited” by default.
- Strong contribution, not a list of every architectural feature.
- Grounded novelty distinction, not “we may be somewhat novel.”
- No self-defensive paragraphs about possible objections, missing seeds, or failure to solve different tasks unless actually central to the paper's claim.

## Related Work

Organize by scientific question, assumptions, mechanisms, and scope—not superficial vocabulary. Cite genuine overlaps and distinguish the paper's specific contribution without needless negative rhetoric. Use [novelty.md](novelty.md). Do not write “our work is completely different” when there are real shared mechanisms; do not write “our novelty is limited” solely because a common tool is reused.

## Specialized technical sections

For **Method**, **Theory**, and **Experiments / Results**, follow [method.md](method.md), [theory.md](theory.md), and [experiments.md](experiments.md) respectively. Their distinct claims and evidentiary standards take precedence over generic section phrasing.

## Discussion and Limitations

Interpret why the supported findings matter; make room for **actual** boundaries, tradeoffs, negative results, and unresolved questions. Limitations should be substantive and nonduplicative. Do not add a generic inventory of hypothetical reviewer criticisms. A thoughtful limitation is specific: `property not established`, `scope not evaluated`, or `dependence on assumption A`, with relevance to the central claim.

## Conclusion

Answer the research question using the strongest supported finding, restate the key insight, and close at the evidence-supported level of generality. Do not undercut the final contribution with a catch-all apology or a speculative acceptance claim.
