# Remove requirement

**`REMOVE-REQ`**

You are **removing** a requirement: deleting the artifact and **updating** the **outcome README** index (and risk table if it referenced this line). **Ripple** crosses into **engineering**: **`docs/engineering/README.md`** must drop or rewrite rows that pointed at this requirement; **component** specs may need edits if they no longer have that obligation.

**Context span:** requirement path, **parent outcome** README, **engineering root** table, **components** that listed the requirement. If the requirement was the **only** mitigator for a risk, the risk row on the outcome may need a **new** mitigating requirement or a **revised** risk.

**Records:** **CRs** at requirement scope (if something meaningful remains to say), **outcome** scope, and **`ENG-CR…`** when the table moves. **PDRs** are uncommon but possible if removal reflects a **strategic** pullback.

---

### Draft

**Example:** remove a requirement file, then scrub the outcome tables, then adjust the engineering table so no row links to a ghost. **Example:** if two components shared the requirement, both specs may need a sentence removed or replaced.

### AI-assisted review

Search for broken links and orphaned table cells. **CRs** to cover the narrative of what changed.

### Independent review

Confirm the outcome still hangs together and engineering no longer promises the removed work.
