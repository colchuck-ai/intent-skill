# Structure

Where intent docs live, how folders nest, and how names are formed. **One engineering tree** (`docs/engineering/`) pairs with **one product root** (`docs/product/README.md`).

---

## Directory layout

Use this **nested** layout for new work. Outcomes always sit under `outcomes/`; requirements under each outcome’s `requirements/`; components under `components/`. Do not flatten those segments away.

### Product (`docs/product/`)

```txt
docs/product/
  README.md
  crs/
  pdrs/
  outcomes/
    O<NNN>-<kebab>/
      README.md
      crs/
      pdrs/
      requirements/
        O<NNN>-R<NNN>-<kebab>.md
        O<NNN>-R<NNN>-<kebab>/
          README.md
          crs/
          pdrs/
```

### Engineering (`docs/engineering/`)

```txt
docs/engineering/
  README.md
  crs/
  adrs/
  components/
    C<NNN>-<kebab>.md
    C<NNN>-<kebab>/
      README.md
      crs/
      adrs/
```

`crs/`, `pdrs/`, and `adrs/` at each scope hold **change records**, **product decision records**, and **architectural decision records** (see below). Empty folders may be omitted until first use.

---

## IDs and names

**Numeric part:** Use **three zero-padded digits** (`001`, `012`, `120`) unless your team agrees otherwise. **`NNN`** in templates means that pattern.

**Scope:** Prefixes (`O`, `R`, `C`, `PDR`, `ADR`, `CR`) are **scoped per parent folder**. `O001` under one outcome path does not claim to be unique repo-wide; the same digits may appear under another parent.

**Kebab segment:** After the id (or id chain), always add a **kebab-case short name**. Do not end a path on the number alone—prefer `O001-auth-hardening`, not bare `O001`.

**Templates:** Placeholders like `<slug>` or `<NNN>` must be replaced in finished docs.

**Requirement ↔ component links** live as **table rows** in `docs/engineering/README.md` only; do not treat requirement or component bodies as the master mapping list.

---

## Simple vs complex

| | **Simple** | **Complex** |
|---|------------|-------------|
| **Shape** | A single **`.md`** file | A **directory** whose **`README.md`** is the canonical narrative; other files are siblings (diagrams, exports, etc.) |
| **PDR / ADR / CR** | `PDR001-topic.md`, `ADR001-topic.md`, `O001-CR001-topic.md` | `PDR001-topic/README.md`, same for ADR/CR under `pdrs/`, `adrs/`, `crs/` |
| **Requirement** | `O001-R002-rate-limits.md` | `O001-R001-auth/README.md` plus siblings |
| **Component** | `C002-config-loader.md` | `C001-gateway/README.md` plus siblings |

The same artifact type can be simple in one place and complex in another; pick what the content needs.

---

## Artifacts by path pattern

### Product root

- **Path:** `docs/product/README.md` (single file).
- **Role:** Product statement; outcome **one-liners** land here when you enumerate outcomes.
- **Template style:** Choose **one** of simple or JTBD for the life of the tree; do not mix.

### Outcome (directory)

- **Path:** `docs/product/outcomes/O<NNN>-<kebab>/`
- **Role:** Container for one outcome. Always a **directory** so nested `crs/`, `pdrs/`, and `requirements/` have a home.

### Outcome (file)

- **Path:** `docs/product/outcomes/O<NNN>-<kebab>/README.md`
- **Role:** Canonical outcome narrative (problem, success, risks, requirement index tables, etc.). This is the **file** authors edit for the outcome in the complex sense; there is no separate “simple outcome file” off to the side—the folder plus `README.md` is the unit.

### Requirement (file or directory)

- **Simple file:** `…/requirements/O<NNN>-R<NNN>-<kebab>.md`
- **Complex directory:** `…/requirements/O<NNN>-R<NNN>-<kebab>/README.md` plus siblings
- **Role:** One testable slice of intent under an outcome.

### Engineering root

- **Path:** `docs/engineering/README.md`
- **Role:** Architecture narrative, principles, and the **components table** (component id, responsibility, requirement links).

### Component (file or directory)

- **Simple file:** `docs/engineering/components/C<NNN>-<kebab>.md`
- **Complex directory:** `docs/engineering/components/C<NNN>-<kebab>/README.md` plus siblings
- **Role:** Tangible buildable piece; links to product requirements via the engineering root table, not via a parallel matrix in the spec.

### PDR (product decision record)

- **Scope folders:** `docs/product/pdrs/`, or `…/outcomes/…/pdrs/`, or `…/requirements/…/pdrs/`
- **Pattern:** `PDR<NNN>-<kebab>.md` or `…/PDR<NNN>-<kebab>/README.md` when complex
- **Role:** Records a **new** product or strategic **decision**—not every edit.

### ADR (architectural decision record)

- **Scope folders:** `docs/engineering/adrs/`, or `…/components/…/adrs/`
- **Pattern:** `ADR<NNN>-<kebab>.md` or `…/ADR<NNN>-<kebab>/README.md` when complex
- **Role:** Records a **new** technical or architectural **decision**.

### CR (change record)

- **Product root (avoid colliding with PDR and engineering tree):** `docs/product/crs/PROD-CR<NNN>-<kebab>.md` or complex `PROD-CR<NNN>-<kebab>/README.md`
- **Engineering root:** `docs/engineering/crs/ENG-CR<NNN>-<kebab>.md` or complex `ENG-CR<NNN>-<kebab>/README.md`
- **Nested** (under outcome, requirement, or component): `O001-CR<NNN>-<kebab>`, `O001-R001-CR<NNN>-<kebab>`, `C001-CR<NNN>-<kebab>`, each `.md` or `…/<kebab>/README.md` when complex
- **Role:** Explains a **meaningful change** to docs at that scope for traceability—separate from recording a brand-new decision (PDR/ADR), though a CR may **point to** one.

---

## Templates

Shells under [`../../assets/`](../assets/) use a **fixed heading order** per template type—keep that order in finished docs so diffs stay readable.
