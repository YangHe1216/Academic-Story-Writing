# Theory Writing: State the Positive Result, Retain Mathematical Precision

**Say what is established before listing what is not.** A rigorous theorem's hypotheses, quantifiers, and conclusion are the natural limits on its claim; they do not require repeated surrounding apologies.

## Positive Theory Spine

1. Identify the research question or obstacle the analysis addresses.
2. Introduce notation and assumptions only as needed; define their mathematical roles.
3. State the strongest **valid** theorem, proposition, characterization, construction, bound, or counterexample precisely.
4. Summarize the proof intuition or core mechanism, distinguishing formal steps from intuition.
5. Explain why the result matters to the paper's central insight; do not claim empirical mechanisms proved by mathematics alone.
6. Discuss a limitation only when it materially qualifies the mathematical assertion or prevents a plausible incorrect inference not already excluded by the formal statement.

## Classify Before You Write

- `THEOREM / PROOF`: deductively established under explicit assumptions. Say “we prove/establish”; never soften to “may suggest” just to be careful.
- `COROLLARY / DERIVED PROPERTY`: follows from identified premises. State the relationship directly.
- `SUFFICIENT / NECESSARY CONDITION`: distinguish directions, quantifiers, existence, uniformity, asymptotics, locality, etc.
- `PROPOSITION WITH GAP`: do not invent a proof. Mark the unresolved step or restrict to what is actually proved.
- `DIAGNOSTIC / EXAMPLE / ILLUSTRATION`: directly state what it reveals or exhibits, without elevating it to a universal theorem.
- `HEURISTIC INTUITION`: explain it as intuition; do not disguise as proof.

## No Serial Self-Defense

Common unnecessary prose:

> “We do not claim global convergence. This is a different task. Our diagnostic should not be interpreted as a proof. We only intend to provide some insights.”

If the grounded positive result is a stationary-point convergence theorem under A1–A3, write:

> “Under Assumptions A1–A3, Theorem 2 establishes convergence to a stationary point. The result characterizes the conditions under which the proposed update admits this guarantee.”

This is **not** a global-optimality claim; no surrounding parade of nonclaims is necessary when the formal statement is clear. If a nearby sentence genuinely invites mistaken global inference, clarify the single relevant boundary at its point of use.

If the item is actually a diagnostic rather than a proof, write its positive diagnostic conclusion, for example: “The diagnostic isolates [measured behavior] under [condition].” Never state “Theorem proves” if only a plot or heuristic supports the statement.

## Theoretical Disclaimer Gate

Before adding `we do not claim`, `different task`, `diagnostic rather than proof`, `cannot conclude`, or `only a heuristic`, answer:

1. Which **specific** unsupported mathematical conclusion could the existing text plausibly cause a reader to draw?
2. Does the theorem statement already prevent it through explicit conditions/quantifiers?
3. Can the positive result be phrased more precisely instead of adding a new defensive sentence?
4. Is the caveat genuinely needed near this result, or should a broader limitation appear once in Discussion?

If no specific misreading is at stake, omit. **Do not delete necessary hypotheses, exceptional cases, proof limitations, or actual logical gaps.** Strength of rhetoric never repairs a missing proof.

## Story Alignment

A theorem should clarify a meaningful part of the paper's argument: existence, identifiability, characterization, guarantee, impossibility, approximation, or explanation. Do not append formal results as an unrelated catalog of impressive facts. If a result is mathematically valid but secondary, present it proportionately.
