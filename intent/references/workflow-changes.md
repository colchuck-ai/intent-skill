# Workflow: Changing existing artifacts

Procedure when **editing** an established doc (product root, outcome, requirement, engineering root, component)—not only net-new files. Typical loop: **draft → AI review → independent review** (see [`context-loading.md`](context-loading.md)). Prefer the **artifact-specific** workflow ([`workflow-product-root.md`](workflow-product-root.md), [`workflow-outcomes.md`](workflow-outcomes.md), [`workflow-requirements.md`](workflow-requirements.md), [`workflow-engineering-root.md`](workflow-engineering-root.md), [`workflow-components.md`](workflow-components.md)) when it matches what you are doing.

**Disjoint sessions:** If you **resume later** (e.g. a separate review or emit pass), **read [`context-loading.md`](context-loading.md) again** before loading bundles for that pass.

## Load

1. **Read [`context-loading.md`](context-loading.md) first** — principles; **B0–B5** definitions.
2. **Load:** **B0** — intent skill slice (roles, emit rules, steps)—[`../SKILL.md`](../SKILL.md) as needed; **B3** — parent chain up from the artifact if the change may affect boundaries; **B4** — peers if checking overlap or horizontal consistency; **B5** — CR/PDR/ADR templates + **exact scope** matching the artifact you changed when you will emit—[`emit-records.md`](emit-records.md).
3. **Identify** the **artifact under edit** and **change intent**.

## Review

1. **Read [`context-loading.md`](context-loading.md) first** if this is a **new session** since your last read (or you are switching from draft to review).
2. **Load:** **B2** — review criteria: [`review-product.md`](review-product.md) (product side), [`review-engineering.md`](review-engineering.md) (engineering side), and/or [`review-change-records.md`](review-change-records.md) (CR quality)—pick by artifact; **B1** — template for the artifact if revising structure; **B3**/**B4** as needed for consistency checks.

Structural consistency (vertical, horizontal, traceability) is covered in those review checklists—no separate consistency doc.

## Emit by phase (when using the full loop)

Apply the same bars as the scoped workflows. Scope **CR** to the **artifact you changed** (see **Scope reference** below). **PDR** and **ADR** are **decision** records—**not** substitutes for CRs; a CR may **reference** a PDR/ADR ([`emit-records.md`](emit-records.md)). Before each phase, **read [`context-loading.md`](context-loading.md) first**, then **B5** (and **B0** as needed) when emitting.

### Draft session

- **CR:** when this session produces **meaningful edits** not yet recorded at the right scope.
- **PDR:** only for a **new** product/strategic **decision** while editing **product** artifacts (`docs/product/…`)—typically under `docs/product/pdrs/` at the scope of the decision.
- **ADR:** only for a **new** **architectural** decision while editing **engineering** artifacts (`docs/engineering/…`)—under `docs/engineering/adrs/` or a component’s `adrs/` at the right scope.

### AI review session

- **CR:** if feedback drives **meaningful** edits **and** they are not yet covered by a CR—same scope as the artifact under review.
- **PDR:** if a **new** strategic decision appears (or was missed in draft)—product tree only.
- **ADR:** if a **new** architectural decision appears (or was missed in draft)—engineering tree only; **do not** emit a decision record every pass.

### Independent review

- **CR:** only if the reviewer still makes **meaningful** edits—or if a **CR** was **missing** for earlier work.
- **PDR:** only if a **new** strategic decision is recognized here—or if a **PDR** was **missing** for an earlier decision (product side).
- **ADR:** only if a **new** architectural decision is recognized here—or if an **ADR** was **missing** for an earlier decision (engineering side).

## Emit sub-step (PDR / ADR / CR)

Respective template from [`../assets/`](../assets/README.md) + minimal parent context + short summary of the decision or change already drafted.

## Scope reference

| You changed | CR scope (typical) |
|-------------|---------------------|
| `docs/product/README.md` | Product root |
| `docs/product/outcomes/.../README.md` | That outcome |
| Requirement under outcome | That requirement path |
| `docs/engineering/README.md` | Engineering root |
| Component under `components/` | That component |

Pair **PDR** with product parents; **ADR** with engineering parents—see [`emit-records.md`](emit-records.md).
