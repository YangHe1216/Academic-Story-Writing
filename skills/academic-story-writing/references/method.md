# Method Writing: Assert the Construction, Explain the Design

**Write what the method is, what it computes, why that design addresses the paper's question, and how its essential components fit together.** A Method section is not a preemptive rebuttal defending every design choice against every conceivable alternative.

## Positive Method Spine

1. **Design objective:** Name the concrete issue from the Story Contract.
2. **Core idea:** State the insight connecting the issue to the method.
3. **Construction:** Define inputs, variables, formulation, constraints, modules, algorithm, and sequence of operations; use precise equations and implementation references.
4. **Mechanism by construction:** Explain information flow, constraint enforcement, or update structure that actually follows from the definition.
5. **Component roles:** Show why essential pieces contribute to this design, not as a list of disconnected advantages.
6. **Evidence-facing bridge:** State what Theory or Experiments will analyze or evaluate; do not present hoped-for performance as an established fact.

## Separate Six Different Claims

| Claim | Allowed basis | Do not silently infer |
|---|---|---|
| “We define/implement X” | Specification or actual implementation | That X is novel or superior |
| “Constraint C enforces property P” | Logical implication of formulation | That training is guaranteed to find a satisfying solution if it isn't |
| “X is designed to reduce problem Y” | Stated objective and reasonable rationale | That X has actually reduced Y |
| “X provably satisfies P” | Correct theorem and assumptions | Broader optimization guarantees |
| “X improves metric M” | Measured outcomes in stated conditions | Universal superiority / causal necessity |
| “X is first/unique/necessary/optimal” | Strong novelty, necessity, or optimization evidence | Grounding from having chosen this design |

### Failure patterns and preferred action

**Apologizing for standard ingredients.**

Avoid: “Although we use a standard encoder, we do not claim it is novel; therefore the method should be viewed as an incremental combination.”

Prefer (when factual): “We use encoder E to construct representation h and introduce objective L that couples h to constraint C.” Cite the original encoder where appropriate. Explain a demonstrably nontrivial interaction without claiming that every combination is original.

**Inflating design motivation into guarantee.**

Avoid: “This architecture guarantees robust generalization.”

Prefer: “The architecture imposes constraint C to target failure mode F; Section X evaluates whether this improves robustness.” Here the design is stated directly, and the measured impact is left to the evidence.

**Apologizing for missing ablations.**

Avoid: “Without component-wise ablations, we cannot justify these modules.”

Prefer: “Module A computes feature F, which module B uses in the constrained update U.” An ablation can be important for a **necessity or attribution** claim, but is not required to define or explain a method.

**Unnecessary optimality disclaimer.**

Avoid: “We do not claim global optimality, so our method is merely a heuristic.”

Prefer: “We optimize the objective with alternating updates described in Algorithm 1.” When the implementation only computes an approximation, say so accurately; never imply a convergence or optimality guarantee without proof.

**Generic tentative language.**

Avoid: “We may potentially consider adding a regularizer.” (when it is already implemented)

Prefer: “We add regularizer R, which penalizes N in the objective.” Separately state any hypothesized effect of R as a hypothesis if not established.

## Method Disclaimer / Extra-Experiment Gate

Before inserting an apology about component novelty, heuristic status, lack of ablations, or optimality, ask what **specific false inference** it prevents. If the exact formulation already defines the property, omit the defensive sentence. If the paper really makes a component-necessity, empirical-mechanism, priority, or optimality claim, require the evidence that claim needs. Do **not** create a stronger claim and then demand experiments to refute it.

**Non-negotiable technical integrity:** retain nontrivial assumptions, data dependencies, failure modes, dimensional constraints, computational complexity when relevant, and reproducibility-critical implementation choices. Be direct about approximation or stochasticity where it actually characterizes the method.

