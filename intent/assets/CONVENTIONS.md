# Template conventions (bundled docs layout)

These rules apply to all files under `intent/assets/` (document templates per [Agent Skills](https://agentskills.io/specification.md) `assets/`). Templates are for **human** authors; there is no automated lint or CI enforcement in this iteration.

## Root paths

- Product root: `docs/product/README.md`
- Engineering root: `docs/engineering/README.md`
- One **engineering** tree per **product** root.

## IDs and filenames

- **Scoped numbering:** Prefixes (`O`, `R`, `C`, `PDR`, `ADR`, `CR`) reset or vary **per parent folder**. The same numeric suffix may appear under different parents.
- **Placeholders** in templates use angle brackets: `<slug>`, `<Title>`, `<n>`, etc. Replace them with real values; **do not** leave placeholders in finished docs.
- **Numeric IDs in titles and examples:** **`NNN`** means **three decimal digits, zero-padded** (e.g. `001`, `012`, `120`). Examples: `# PDR<NNN>:`, `# ADR<NNN>:`, `# CR<NNN>:`, `# O<NNN>:`, `# O<NNN>-R<NNN>:`, `# C<NNN>:`—each **`<NNN>`** is replaced with the scoped id for that artifact (the same placeholder may appear multiple times; use distinct values per artifact when you instantiate the template).
- **Kebab short name in filenames:** After the scoped ID (or ID chain), include a **kebab-case** segment—do not end the filename on the number alone (prefer `PROD-CR001-changelog.md`, not `PROD-CR001.md`).
- **Root change records (avoid cross-tree collisions):** Files in **`docs/product/crs/`** use **`PROD-CR<NNN>-<kebab-slug>.md`** (or complex directory **`PROD-CR<NNN>-<kebab-slug>/`**). Files in **`docs/engineering/crs/`** use **`ENG-CR<NNN>-<kebab-slug>.md`** (or **`ENG-CR<NNN>-<kebab-slug>/`**). That way `PROD-CR001-…` and `ENG-CR001-…` never collide, and **`PROD-CR`** stays visually distinct from **PDR** (product decision record). Nested `crs/` (under outcomes, requirements, components) use the existing scope prefixes (`O001-CR…`, `O001-R001-CR…`, `C001-CR…`) plus kebab.
- **Suggested patterns** (align with your team’s padding rules if any):
  - Outcomes: `O001-<slug>/`, `O002-<slug>/`, … under `docs/product/outcomes/`
  - Requirements: `O001-R001-<slug>` under `outcomes/O001-<slug>/requirements/`
  - Components: `C001-<slug>` under `docs/engineering/components/`
  - PDR / ADR: `PDR001-<kebab>.md`, `ADR001-<kebab>.md`, … under the `pdrs/` or `adrs/` folder for that scope (complex: `PDR001-<kebab>/README.md`).

Nested path examples:

- Product root CR: `docs/product/crs/PROD-CR001-<kebab>.md`
- Engineering root CR: `docs/engineering/crs/ENG-CR001-<kebab>.md`
- Outcome-level CR: `outcomes/O001-<slug>/crs/O001-CR001-<kebab>.md`
- Requirement-level CR: `…/requirements/O001-R001-<slug>/crs/O001-R001-CR001-<kebab>.md`
- Component-level CR: `…/components/C001-<slug>/crs/C001-CR001-<kebab>.md`

## Simple vs complex

- **Simple artifact:** One **file** (e.g. `O001-R002-<slug>.md`, `C002-<slug>.md`).
- **Complex artifact:** A **directory** whose **`README.md`** is the **canonical** narrative; other files are supporting siblings (schemas, diagrams, exports). In complex templates, the **Supporting material** section **explains** what those siblings are for; link to specific files when it helps readers.

## Product ↔ engineering traceability

- **Requirement ↔ component** mapping appears only as **rows** in the **components table** in **`docs/engineering/README.md`**. Do **not** list the full mapping in requirement bodies or duplicate it in component bodies—the engineering root table is authoritative.
- A single requirement may appear on **multiple** rows (many-to-many: several components may satisfy one requirement).

## Section order

Each template defines a **fixed** heading order. Preserve that order in the final document so reviews and diffs stay predictable.

## Decomposition style

Product root templates: **simple** or **JTBD** (see [`README.md`](README.md)). Use **one** per product doc set; migrating later is allowed, but **do not mix** styles at once. The JTBD template lists optional sections—**omit** what you do not need; preserve order among **retained** headings.
