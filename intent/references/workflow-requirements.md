# Workflow: Requirements

Procedure for **requirement one-liners / risks** on the outcome **`README.md`**, then **requirement detail** under **`outcomes/.../requirements/`**. Templates: [`../assets/requirement-simple.md`](../assets/requirement-simple.md), [`../assets/requirement-complex.md`](../assets/requirement-complex.md). Methodology: [`decomposing-requirements.md`](decomposing-requirements.md).

## Requirement index (tables on outcome README)

### Draft session

1. **Read [`context-loading.md`](context-loading.md) first** — principles; **B0–B5** definitions.
2. **Load:** **B0** — intent skill slice—[`../SKILL.md`](../SKILL.md) as needed; **B1** — [`outcome.md`](../assets/outcome.md) (tables live on outcome README); **B3** — product root + this outcome; **B4** — sibling requirements under other outcomes if checking cross-outcome conflicts; **B5** — CR/PDR templates + outcome-scope emit paths when you will emit records ([`emit-records.md`](emit-records.md)).
3. **Decompose** using [`decomposing-requirements.md`](decomposing-requirements.md); lock one-liners (and risk mappings) in the outcome **`README.md`** before expanding requirement files.
4. **Emit** per [`emit-records.md`](emit-records.md):
   - **CR:** for **meaningful edits** to **this outcome’s** **`README.md`** (index tables)—**outcome** scope (under that outcome’s `crs/`).
   - **PDR:** under **`outcomes/<O…>/pdrs/`** **only** when this session introduces a **new** product/strategic **decision** at **outcome** scope—use **`docs/product/pdrs/`** only when the decision belongs at **product root**; not for routine one-liner or risk-table edits.

### AI review session

1. **Read [`context-loading.md`](context-loading.md) first** — principles; **B0–B5** definitions.
2. **Load:** **B0** — intent skill slice—[`../SKILL.md`](../SKILL.md) as needed; **B2** — review criteria ([`review-product.md`](review-product.md), **Requirements (one-liners per outcome)** → **Before expanding requirement detail files**); **B1** — outcome template + draft outcome README; **B3**/**B4** as needed; **B5** — CR/PDR templates + scope if emitting this session.
3. **Review** against criteria; incorporate feedback.
4. **Emit** per [`emit-records.md`](emit-records.md):
   - **CR:** if edits from this session are **meaningful** and not yet covered—**outcome** scope.
   - **PDR:** if a **new** strategic decision appears while addressing feedback (or was missed in draft); **do not** create a PDR for every review pass.

### Independent review

1. **Read [`context-loading.md`](context-loading.md) first** — principles; **B0–B5** definitions.
2. **Load:** **B0** — intent skill slice—[`../SKILL.md`](../SKILL.md) as needed; **B2** — review criteria ([`review-product.md`](review-product.md), requirement index sections above); **B3** — short product-root + outcome context; **B5** — CR/PDR templates + scope if emitting this session.
3. **Emit** per [`emit-records.md`](emit-records.md):
   - **CR:** only if the reviewer still makes **meaningful** edits—or if a **CR** was **missing** for earlier work.
   - **PDR:** only if a **new** strategic decision is recognized at this gate—or if a **PDR** was **missing** for an earlier decision.

## Requirement detail

### Draft session

1. **Read [`context-loading.md`](context-loading.md) first** — principles; **B0–B5** definitions.
2. **Load:** **B0** — intent skill slice—[`../SKILL.md`](../SKILL.md) as needed; **B1** — requirement template (simple or complex); **B3** — outcome + parent chain; **B4** — sibling requirements as needed; optional minimal product trace (requirement IDs, component **names** only—not full mapping lists); **B5** — CR/PDR templates + requirement-scope emit paths when you will emit records ([`emit-records.md`](emit-records.md)).
3. **Draft** capability, acceptance, edge cases; keep mapping in **`docs/engineering/README.md`** only.
4. **Emit** per [`emit-records.md`](emit-records.md):
   - **CR:** for **meaningful edits** to **this requirement** artifact—**requirement** scope (under that requirement’s `crs/` when using complex layout).
   - **PDR:** under **`…/requirements/<O…-R…>/pdrs/`** **only** when this session introduces a **new** product/strategic **decision** at **requirement** scope—use a **parent** `pdrs/` folder (outcome or product root) when the decision spans more than this requirement; not for routine requirement wording.

### AI review session

1. **Read [`context-loading.md`](context-loading.md) first** — principles; **B0–B5** definitions.
2. **Load:** **B0** — intent skill slice—[`../SKILL.md`](../SKILL.md) as needed; **B2** — review criteria ([`review-product.md`](review-product.md), **Requirement artifact** + **Structural consistency (product tree)**); **B1** — requirement template + draft; **B3**/**B4** as needed; **B5** — CR/PDR templates + scope if emitting this session.
3. **Review** against criteria; incorporate feedback.
4. **Emit** per [`emit-records.md`](emit-records.md):
   - **CR:** if edits from this session are **meaningful** and not yet covered—**requirement** scope.
   - **PDR:** if a **new** strategic decision appears while addressing feedback (or was missed in draft); **do not** create a PDR for every review pass.

### Independent review

1. **Read [`context-loading.md`](context-loading.md) first** — principles; **B0–B5** definitions.
2. **Load:** **B0** — intent skill slice—[`../SKILL.md`](../SKILL.md) as needed; **B2** — review criteria ([`review-product.md`](review-product.md), **Requirement artifact**); **B3** — one-screen outcome context; **B5** — CR/PDR templates + scope if emitting this session.
3. **Emit** per [`emit-records.md`](emit-records.md):
   - **CR:** only if the reviewer still makes **meaningful** edits—or if a **CR** was **missing** for earlier work.
   - **PDR:** only if a **new** strategic decision is recognized at this gate—or if a **PDR** was **missing** for an earlier decision.
