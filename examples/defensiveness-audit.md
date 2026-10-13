# Defensiveness audit — illustrative cases

**Synthetic examples only.** These sentences show the diagnostic behavior of Academic Story Writing. They are not evidence of measured Skill performance.

| Code | Draft | Preferred, if source supports it | Why |
|---|---|---|---|
| D1 | We do not claim the method works everywhere. | We evaluate the method on datasets A and B. | Positive tested scope replaces an unmade universality claim. |
| D2 | The theorem may potentially establish a bound. | Under A1–A2, Theorem 1 establishes bound B. | Formal conclusion is direct; assumptions remain. |
| D3 | We merely use a standard backbone. | We combine backbone E with coupling objective C. | Describe the design without automatically claiming originality. |
| D4 | Reviewers may ask for stronger claims. | [Delete.] | No scientific content or relevant evidence. |
| D5 | We need more seeds before reporting the observed score. | In the recorded run, the method obtains M. | A recorded observation differs from a reliability claim. |
| D6 | We repeatedly note that no global optimum is guaranteed. | Under A1–A3, the algorithm converges to a stationary point. | Exact established scope replaces repeated caveats. |
| D7 | Related work uses the same encoder, so novelty is limited. | Both use encoder E; the contribution we establish is formulation F. | Component overlap does not settle substantive novelty. |
| D8 | The design is only a heuristic without an optimality proof. | Algorithm 1 uses an alternating update to minimize objective L approximately. | State the actual procedure without pretending it is optimal. |
| D9 | We do not prove global optimality; we do not handle all objectives. | Under A1–A3, Theorem 2 proves convergence to a stationary point. | Theory should say what is established. |
| D10 | Because the proposed mechanism remains unverified, the measured result is uncertain. | We observe a gain of Δ on D. We hypothesize that mechanism H explains it. | A hypothesis's uncertainty should not weaken an independent measurement. |

The proposed edits presuppose the conditions or results specified in each synthetic scenario. Never substitute them for real source evidence. A measured effect, a proof, and a mechanistic explanation have different evidence requirements.

## Usage

```text
$academic-story-writing
PRESERVE + EDITOR. Audit only the following Results paragraph for D1–D10.
Fix justified defensive phrasing without changing the measured setting,
method, numerical claims, or scientific story. Report categories only if found.

[Paste text]
```
