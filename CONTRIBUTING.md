# Contributing

Thanks for improving Academic Story Writing. This project focuses on **specific, evidence-grounded failures** in CS / AI / ML manuscript writing.

Useful contributions include:
- A case where a supported claim was weakened without a concrete reason.
- An example where a controlled experiment was dismissed due to irrelevant dataset/seed concerns.
- A genuine overclaim that the Skill missed.
- A case where editing a selected LaTeX passage changed equations, notation, references, or nearby text.
- A case where Writer mode slipped into imaginary-reviewer simulation.

When reporting a problem, include the requested mode, minimal source passage/notes, the model's output, your desired correction, and the **specific evidence** that supports the correction. Redact confidential research, unreleased submissions, third-party private reviews, personal data, and proprietary experiments. Prefer self-contained synthetic reproductions.

For changes to prompts/reference rules: keep `SKILL.md` short, avoid duplicate policies, use scoped reference files, and explain which failure mode the change addresses. Do not promise benchmark improvements without actual controlled evaluations.

Before publishing a PR, check prose and any examples for invented citations, unverifiable novelty, or misleading scientific claims. Open discussion before adding a new default review mode or automatic extra-experiment requirement.
