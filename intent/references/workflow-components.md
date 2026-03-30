# Workflow: Components

Procedure for **component** artifacts under **`docs/engineering/components/`** (simple file or complex directory with **`README.md`**). Templates: [`../assets/component-simple.md`](../assets/component-simple.md), [`../assets/component-complex.md`](../assets/component-complex.md). Conventions: [`../assets/CONVENTIONS.md`](../assets/CONVENTIONS.md).

## Draft session

1. **Read [`context-loading.md`](context-loading.md) first** — principles; **B0–B5** definitions.
2. **Load:** **B0** — intent skill slice—[`../SKILL.md`](../SKILL.md) as needed; **B1** — component template (simple or complex); **B3** — **`docs/engineering/README.md`** and the table row you will add or update; **B4** — sibling components when checking overlap; minimal product trace (requirement IDs); **B5** — CR/ADR templates + component (and engineering-root if needed) emit scope when you will emit records ([`emit-records.md`](emit-records.md)).
3. **Draft** component doc; **update** the engineering root **components table** to match.
4. **Emit** per [`emit-records.md`](emit-records.md):
   - **CR:** for **meaningful edits** to the **component** artifact **and**, when the table row changed, the **engineering root README**—emit **CRs** at **component** scope (and engineering-root scope if you meaningfully changed the shared table there—see [`emit-records.md`](emit-records.md)).
   - **ADR:** under that component’s `adrs/` or under `docs/engineering/adrs/` **only** when this session introduces a **new** **architectural** decision at the right scope—not for routine component doc edits.

## AI review session

1. **Read [`context-loading.md`](context-loading.md) first** — principles; **B0–B5** definitions.
2. **Load:** **B0** — intent skill slice—[`../SKILL.md`](../SKILL.md) as needed; **B2** — review criteria ([`review-engineering.md`](review-engineering.md), **Component**); **B1** — template + draft + updated table snippet; **B4** — sibling components as needed; **B5** — CR/ADR templates + scope if emitting this session.
3. **Incorporate** feedback; re-review if material changes.
4. **Emit** per [`emit-records.md`](emit-records.md):
   - **CR:** if edits from this session are **meaningful** and not yet covered—**component** scope (and engineering-root **CR** if the components table still needs one).
   - **ADR:** if a **new** architectural decision appears while addressing feedback (or was missed in draft)—emit at component or engineering scope as appropriate; **do not** create an ADR for every review pass.

## Independent review

1. **Read [`context-loading.md`](context-loading.md) first** — principles; **B0–B5** definitions.
2. **Load:** **B0** — intent skill slice—[`../SKILL.md`](../SKILL.md) as needed; **B2** — review criteria ([`review-engineering.md`](review-engineering.md), **Component**); **B3** — relevant engineering root row(s); **B5** — CR/ADR templates + scope if emitting this session.
3. **Emit** per [`emit-records.md`](emit-records.md):
   - **CR:** only if the reviewer still makes **meaningful** edits—or if a **CR** was **missing** for earlier work (component and/or engineering root as needed).
   - **ADR:** only if a **new** architectural decision is recognized at this gate—or if an **ADR** was **missing** for an earlier decision.

## Related

- [`workflow-engineering-root.md`](workflow-engineering-root.md) for the parent README.
