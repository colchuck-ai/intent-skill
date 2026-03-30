# Decomposing outcomes into requirements

- **Why / how / how-else** — From an outcome, ask (1) *“How is this outcome achieved?”* Each distinct answer is a **candidate requirement** (if still abstract, decompose further; if concrete enough to build, treat it as a requirement). (2) *“How else?”* — ask again so you do not lock into one design and so gaps surface. (3) *“Why does this requirement exist?”* — every candidate must trace back to the outcome; if it does not, it is misplaced or unjustified.

- **Risk analysis** — For each outcome, ask *“What could prevent this from being true?”* Each answer is a **risk**. Risks surface requirements you would otherwise discover late. Document each risk in the outcome README and map it to the **mitigating requirement**. Every risk must map to an existing requirement or force a new one.

- **Completeness** — An outcome is sufficiently decomposed when every “how” has a requirement, every risk has a mitigating requirement, every requirement traces back via “why,” and you cannot name a **realistic failure** that nothing addresses. Aim for enough coverage to build, not exhaustive enumeration.
