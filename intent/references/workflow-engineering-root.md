# Workflow: Engineering root

Procedure for **`docs/engineering/README.md`**. Template: [`../assets/engineering-root.md`](../assets/engineering-root.md). Conventions: [`../assets/CONVENTIONS.md`](../assets/CONVENTIONS.md).

## Draft session

1. **Read [`context-loading.md`](context-loading.md) first** — principles; **B0–B5** definitions.
2. **Load:** **B0** — intent skill slice—[`../SKILL.md`](../SKILL.md) as needed; **B1** — engineering root template + [`CONVENTIONS.md`](../assets/CONVENTIONS.md); **B3** — product summary (root and/or outcome/requirement one-liners; avoid full trees unless necessary); **B5** — CR/ADR templates + engineering-root emit scope when you will emit records ([`emit-records.md`](emit-records.md)).
3. **Draft** architecture/system view and **components table** with **links to product requirements**—authoritative mapping lives here only.
4. **Emit** per [`emit-records.md`](emit-records.md):
   - **CR:** for **meaningful edits** to the engineering root **README** (including the components table)—engineering-root scope.
   - **ADR:** under `docs/engineering/adrs/` **only** when this session introduces a **new** root-level **architectural** decision—not for routine edits or table tweaks.

## AI review session

1. **Read [`context-loading.md`](context-loading.md) first** — principles; **B0–B5** definitions.
2. **Load:** **B0** — intent skill slice—[`../SKILL.md`](../SKILL.md) as needed; **B2** — review criteria ([`review-engineering.md`](review-engineering.md), **Engineering root README**); **B1** — template + conventions + draft; **B3** — product summary; **B5** — CR/ADR templates + engineering-root scope if emitting this session.
3. **Incorporate** feedback; re-review if material changes.
4. **Emit** per [`emit-records.md`](emit-records.md):
   - **CR:** if edits from this session (or any gap from draft) are **meaningful** and not yet covered by a CR—**CR** at engineering-root scope.
   - **ADR:** if a **new** architectural decision appears while addressing review feedback (or was missed in draft)—emit at root; **do not** create an ADR for every review pass.

## Independent review

1. **Read [`context-loading.md`](context-loading.md) first** — principles; **B0–B5** definitions.
2. **Load:** **B0** — intent skill slice—[`../SKILL.md`](../SKILL.md) as needed; **B2** — review criteria ([`review-engineering.md`](review-engineering.md), **Engineering root README**); **B3** — one-screen product summary; **B5** — CR/ADR templates + scope if emitting this session.
3. **Emit** per [`emit-records.md`](emit-records.md):
   - **CR:** only if the reviewer still makes **meaningful** edits to the README or table—or if a **CR** was **missing** for earlier work.
   - **ADR:** only if a **new** architectural decision is recognized at this gate—or if an ADR was **missing** for an earlier decision.

## Related

- [`workflow-components.md`](workflow-components.md) for component files under `docs/engineering/components/`.
