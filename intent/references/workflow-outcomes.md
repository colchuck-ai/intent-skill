# Workflow: Outcomes

Procedure for (1) **outcomes list** on **`docs/product/README.md`** and (2) **per-outcome** **`docs/product/outcomes/O001-<slug>/README.md`**. Template: [`../assets/outcome.md`](../assets/outcome.md). You may **detail outcomes first** (problem, success, boundaries) before fully developing risks and requirement one-liners in a later pass—do not drop risks/requirements.

## Outcomes on product root

### Draft session

1. **Read [`context-loading.md`](context-loading.md) first** — principles; **B0–B5** definitions.
2. **Load:** **B0** — intent skill slice—[`../SKILL.md`](../SKILL.md) as needed; **B1** — product root template as reference for the outcomes list; **B4** — other outcome one-liners when checking overlap; **B5** — CR/PDR templates + product-root emit scope when you will emit records ([`emit-records.md`](emit-records.md)).
3. **Draft** or revise the **outcomes list** (one-liners) on **`docs/product/README.md`**.
4. **Emit** per [`emit-records.md`](emit-records.md):
   - **CR:** for **meaningful edits** to **`docs/product/README.md`**—product-root scope (e.g. `docs/product/crs/` with **`PROD-CR`** naming per [`../assets/CONVENTIONS.md`](../assets/CONVENTIONS.md)).
   - **PDR:** under `docs/product/pdrs/` **only** when this session introduces a **new** product/strategic **decision**—not for routine outcome-line edits.

### AI review session

1. **Read [`context-loading.md`](context-loading.md) first** — principles; **B0–B5** definitions.
2. **Load:** **B0** — intent skill slice—[`../SKILL.md`](../SKILL.md) as needed; **B2** — review criteria ([`review-product.md`](review-product.md), **Outcomes (list / one-liners in root)**); **B1** — product root template + draft README; **B3**/**B4** as needed; **B5** — CR/PDR templates + product-root scope if emitting this session.
3. **Review** against criteria; incorporate feedback.
4. **Emit** per [`emit-records.md`](emit-records.md):
   - **CR:** if edits from this session (or gaps from draft) are **meaningful** and not yet covered by a CR—product-root scope.
   - **PDR:** if a **new** strategic decision appears while addressing feedback (or was missed in draft)—emit under `docs/product/pdrs/`; **do not** create a PDR for every review pass.

### Independent review

1. **Read [`context-loading.md`](context-loading.md) first** — principles; **B0–B5** definitions.
2. **Load:** **B0** — intent skill slice—[`../SKILL.md`](../SKILL.md) as needed; **B2** — review criteria ([`review-product.md`](review-product.md), **Outcomes (list / one-liners in root)**); **B3** — short parent / charter summary; **B5** — CR/PDR templates + scope if emitting this session.
3. **Emit** per [`emit-records.md`](emit-records.md):
   - **CR:** only if the reviewer still makes **meaningful** edits to the product root README—or if a **CR** was **missing** for earlier work.
   - **PDR:** only if a **new** strategic decision is recognized at this gate—or if a **PDR** was **missing** for an earlier decision.

## Outcome README

### Draft session

1. **Read [`context-loading.md`](context-loading.md) first** — principles; **B0–B5** definitions.
2. **Load:** **B0** — intent skill slice—[`../SKILL.md`](../SKILL.md) as needed; **B1** — [`outcome.md`](../assets/outcome.md) template; **B3** — product root; **B4** — other outcome READMEs for horizontal checks; **B5** — CR/PDR templates + outcome-scope emit paths when you will emit records ([`emit-records.md`](emit-records.md)).
3. **Draft** outcome detail; add risks/requirements tables when in scope for this session.
4. **Emit** per [`emit-records.md`](emit-records.md):
   - **CR:** for **meaningful edits** to **this outcome’s** **`README.md`**—**outcome** scope (under that outcome’s `crs/`).
   - **PDR:** under **`outcomes/<O…>/pdrs/`** **only** when this session introduces a **new** product/strategic **decision** at **outcome** scope—use **`docs/product/pdrs/`** only when the decision belongs at **product root**; not for routine outcome text or table edits.

### AI review session

1. **Read [`context-loading.md`](context-loading.md) first** — principles; **B0–B5** definitions.
2. **Load:** **B0** — intent skill slice—[`../SKILL.md`](../SKILL.md) as needed; **B2** — review criteria ([`review-product.md`](review-product.md), **Outcome README (detail phase)**); **B1** — outcome template + draft; **B3**/**B4** as needed; **B5** — CR/PDR templates + scope if emitting this session.
3. **Review** against criteria; incorporate feedback.
4. **Emit** per [`emit-records.md`](emit-records.md):
   - **CR:** if edits from this session are **meaningful** and not yet covered—**outcome** scope.
   - **PDR:** if a **new** strategic decision appears while addressing feedback (or was missed in draft); **do not** create a PDR for every review pass.

### Independent review

1. **Read [`context-loading.md`](context-loading.md) first** — principles; **B0–B5** definitions.
2. **Load:** **B0** — intent skill slice—[`../SKILL.md`](../SKILL.md) as needed; **B2** — review criteria ([`review-product.md`](review-product.md), **Outcome README (detail phase)**); **B3** — one-screen product-root summary; **B5** — CR/PDR templates + scope if emitting this session.
3. **Emit** per [`emit-records.md`](emit-records.md):
   - **CR:** only if the reviewer still makes **meaningful** edits—or if a **CR** was **missing** for earlier work.
   - **PDR:** only if a **new** strategic decision is recognized at this gate—or if a **PDR** was **missing** for an earlier decision.

## Related

- Requirements decomposition: [`decomposing-requirements.md`](decomposing-requirements.md), [`workflow-requirements.md`](workflow-requirements.md).
