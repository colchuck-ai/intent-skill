# Canonical documentation layout

Use this **nested** layout for new work—not ad-hoc flat trees (for example, outcomes must live under `outcomes/`, not only at `docs/product/O001-…` without that segment). **One engineering tree** per **product** root.

**Filenames:** After each scoped ID segment, include a **kebab-case short name** (e.g. `PROD-CR001-changelog.md`, `O001-R001-CR001-typo-fix.md`). Root-level CRs under **`docs/product/crs/`** use the **`PROD-CR`** prefix (distinct from **PDR**); root-level CRs under **`docs/engineering/crs/`** use **`ENG-CR`**—so `PROD-CR001-…` and `ENG-CR001-…` do not collide. See [`../assets/CONVENTIONS.md`](../assets/CONVENTIONS.md).

## Product (`docs/product/`)

```txt
docs/product/
  README.md
  crs/
    PROD-CR001-changelog.md             # simple CR (product root)
    PROD-CR002-governance-update/       # complex CR
      README.md
  pdrs/
    PDR001-positioning.md               # simple PDR
    PDR002-platform-strategy/           # complex PDR
      README.md
  outcomes/
    O001-<slug>/
      README.md
      crs/
        O001-CR001-copy-edit.md         # simple CR (outcome scope)
        O001-CR002-scope-shift/         # complex CR
          README.md
      pdrs/
        O001-PDR001-naming-convention.md  # simple PDR
        O001-PDR002-research-synthesis/   # complex PDR
          README.md
      requirements/
        O001-R001-auth/
          README.md                       # complex requirement
          crs/
            O001-R001-CR001-typo-fix.md   # simple CR
            O001-R001-CR002-migration/    # complex CR
              README.md
          pdrs/
            O001-R001-PDR001-scope-tweak.md  # simple PDR
            O001-R001-PDR002-options-review/ # complex PDR
              README.md
        O001-R002-rate-limits.md          # simple requirement
```

## Engineering (`docs/engineering/`)

```txt
docs/engineering/
  README.md
  crs/
    ENG-CR001-readme-tweak.md           # simple CR (engineering root)
    ENG-CR002-table-overhaul/           # complex CR
      README.md
  adrs/
    ADR001-structured-logging.md        # simple ADR
    ADR002-data-layer/                  # complex ADR
      README.md
  components/
    C001-api-gateway/
      README.md                         # complex component
      crs/
        C001-CR001-readme-sync.md       # simple CR
        C001-CR002-contract-change/     # complex CR
          README.md
      adrs/
        C001-ADR001-timeout-defaults.md # simple ADR
        C001-ADR002-retries/            # complex ADR
          README.md
    C002-config-loader.md               # simple component
```

## Simple vs complex

- **Simple:** a single **`.md`** file.
- **Complex:** a **directory** with **`README.md`** as the canonical narrative; other files are supporting siblings.

### Examples (by artifact)

| Artifact | Simple | Complex |
|----------|--------|---------|
| **Requirement** | `O001-R002-rate-limits.md` | `O001-R001-auth/README.md` plus siblings under `O001-R001-auth/` |
| **Component** | `C002-config-loader.md` | `C001-api-gateway/README.md` plus siblings under `C001-api-gateway/` |
| **CR (product root)** | `PROD-CR001-changelog.md` | `PROD-CR002-governance-update/README.md` |
| **CR (engineering root)** | `ENG-CR001-readme-tweak.md` | `ENG-CR002-table-overhaul/README.md` |
| **CR (nested)** | `O001-CR001-copy-edit.md`, `O001-R001-CR001-typo-fix.md`, `C001-CR001-readme-sync.md` | `…/<kebab>/README.md` under `crs/` at outcome, requirement, or component scope |
| **PDR** | `PDR001-positioning.md`, `O001-PDR001-naming-convention.md` | `PDR002-platform-strategy/README.md` (and nested under `pdrs/` at any scope) |
| **ADR** | `ADR001-structured-logging.md`, `C001-ADR001-timeout-defaults.md` | `ADR002-data-layer/README.md` (and nested under `adrs/` at any scope) |

## IDs

Prefixes are **scoped per parent directory** (they need not be unique repo-wide). Padding (`O001`, `R001`, …) is a readability convention—align with [`../assets/CONVENTIONS.md`](../assets/CONVENTIONS.md).
