# Claim Calibration and Evidence Scope

## Governing Rule

**Make the strongest defensible claim that serves the paper's central story.** A strong claim is not an overclaim merely because it is assertive. A cautious claim is not rigorous merely because it uses hedges.

## Distinct Types of Claims

| Type | What warrants a direct statement | Typical phrase |
|---|---|---|
| Construction | Exact algorithm, objective, implementation, specified procedure | “We define …”, “Our method uses …” |
| Formal result | Checked proof/derivation under conditions | “Theorem 1 establishes … under A1–A3.” |
| Empirical observation | Recorded results in tested setup | “On D under P, X obtains …” |
| Mechanism / explanation | Separate causal/mechanistic evidence; otherwise an explicit hypothesis | “We hypothesize that …” |
| Generalization | Evidence covering claimed range of conditions | “Across the evaluated shifts …” |
| Priority / novelty | Adequate actual prior-work inspection | “Unlike [source], our formulation …” |

Independently assign evidence status:

- `ESTABLISHED`: precise mathematical/formal fact grounded in derivation or proof.
- `SUPPORTED`: supported observation or comparison **in its tested scope**.
- `HYPOTHESIZED`: explanatory or mechanistic idea not directly established.
- `UNVERIFIED`: sources inaccessible or support insufficient for the specific assertion.

An author-supplied claim can be written *as provided input*, but do not misleadingly say it has been independently validated. If it becomes important to establish priority, causality, or broad robustness, identify the verification issue precisely.

## Evidence-Grounded Scope Corrections

Apply the main Skill's Claim Downgrade Gate: correct only the part unsupported by a concrete conflict, a missing necessary assumption, or an overbroad quantifier.

Valid reasons include documented contradictory results, an invalid derivation, an unfair comparison, missing necessary assumptions, or an unsupported generalization. “A reviewer might object,” “this sounds ambitious,” superficial overlap, or lack of a literature search **are not themselves evidence of invalidity**. Lack of verification still prevents claiming a fact has been checked.

## Localize Uncertainty

- A theorem proved for conditions A1–A3 can be stated directly **under A1–A3**, even if it does not address global optimality.
- A controlled result on D is a result on D, not automatically a universal claim or an invalid observation.
- If “first” is not verified, replace that **priority** assertion with the strongest known technical distinction; do not make the empirical/theoretical result tentative.
- If a mechanism has not been isolated, report the performance directly and present the proposed explanation as a hypothesis.

## Disclaimers and Hedges

A disclaimer belongs in manuscript prose only if it prevents a likely, material, specific misreading that the positive phrasing itself does not prevent. Otherwise delete it or place the issue in a separate optional note. Avoid consecutive sentences of “we do not claim / this is a different task / diagnostic rather than proof / future work is necessary.”

Before adding `may`, `might`, `potentially`, `possibly`, `suggests`, `appears`, or `only`, ask which epistemic uncertainty it encodes. Use it only for that uncertainty. **Never remove needed mathematical or inferential boundaries to make the prose confident.**

## Story Prominence Is a Separate Decision

A well-supported efficiency gain may be secondary to a paper about representation robustness. Place it where it belongs, rather than making a distracting headline. A central thesis that lacks evidence should be flagged honestly; do not replace it with an unrelated metric improvement just to tell an easier story.

## Acceptance Boundary

Never promise acceptance or use a pseudo-precise likelihood without defensible predictive basis. If asked about venue readiness, assess substantive strengths, risks, fit, and evidence gaps in a dedicated review response—not as self-defensive language inserted into the paper.
