# Intent tree phase (quick read)

Use this when you need a **rough sense** of how mature an intent tree is—mostly **greenfield** (still being stood up) versus **brownfield** (already populated and evolving)—so you can **bias** toward **develop / enumerate** workflows versus **modify / remove** ones. This is heuristics, not a linter.

**Probing is intentionally limited to `ls` and `grep`** (including recursive grep). No scripts, no required tooling beyond the shell.

Paths below assume the usual layout from [`structure.md`](structure.md): `docs/product/`, `docs/engineering/`.

---

## What to run

**1. See whether the trees exist and what is at the top**

```bash
ls -la docs/product
ls -la docs/engineering
```

**2. Count shape: outcomes, requirements, components**

```bash
ls docs/product/outcomes 2>/dev/null
ls docs/engineering/components 2>/dev/null
```

If those directories are missing or empty, you are looking at an early or product-only tree.

**3. Sample depth with grep (optional but fast)**

Rough presence of requirement files and component files (adjust patterns if your ids differ):

```bash
grep -r "O[0-9][0-9][0-9]" docs/product/outcomes --include='*.md' -l 2>/dev/null | wc -l
grep -r "C[0-9][0-9][0-9]" docs/engineering/components --include='*.md' -l 2>/dev/null | wc -l
```

If your `grep` does not support `--include`, drop that flag and narrow the path, or count matching lines instead.

Use **grep** to spot whether key roots are still placeholders:

```bash
grep -n "outcomes" docs/product/README.md
grep -n "^## Components" docs/engineering/README.md
```

**4. Change and decision history (optional signal)**

```bash
ls docs/product/crs docs/product/pdrs 2>/dev/null
ls docs/engineering/crs docs/engineering/adrs 2>/dev/null
ls docs/product/outcomes/*/crs 2>/dev/null
```

Many `crs/` entries with real files often mean the tree has been **living** for a while; absence does not prove greenfield (teams skip CRs), but **presence** of layered records is a brownfield hint.

---

## How to read the signals

| Signal | Often means |
|--------|-------------|
| No `docs/product/README.md` or it is tiny / placeholder | **Greenfield** on product; start with **Develop product** (`DEV-PROD`). |
| Product README exists but **no** `outcomes/` or it is empty | **Greenfield** product expansion; **Enumerate outcomes** (`ENUM-OUT`) then **Develop outcome** (`DEV-OUT`). |
| Outcomes exist but **no** `requirements/` under them (or empty) | **Greenfield** decomposition; **Enumerate requirements** (`ENUM-REQ`) then **Develop requirement** (`DEV-REQ`). |
| `docs/engineering/README.md` missing or no components table | **Greenfield** engineering; after product intent is credible, **Develop architecture** (`DEV-ARCH`) then **Enumerate components** (`ENUM-COMP`) / **Develop component** (`DEV-COMP`). |
| Populated `outcomes/`, `requirements/`, `components/`, plus `crs/` or `adrs/` | **Brownfield**; bias toward **Modify** (`MOD-*`) workflows when the user is changing scope or behavior. |
| User explicitly wants to delete or retire scope | **Removal** (`REMOVE-*`) regardless of maturity—confirm with them, then follow cascade in those workflows. |

**Greenfield bias** (build the tree): `DEV-PROD` → `ENUM-OUT` → `DEV-OUT` → `ENUM-REQ` → `DEV-REQ` → `DEV-ARCH` → `ENUM-COMP` → `DEV-COMP` (order is flexible, but **product before engineering** is strongly recommended).

**Brownfield bias** (evolve what exists): `MOD-PROD`, `MOD-OUT`, `MOD-REQ`, `MOD-ARCH`, `MOD-COMP` as the edit touches.

**Removal bias**: `REMOVE-OUT`, `REMOVE-REQ`, `REMOVE-COMP` when the work is about deleting or retiring artifacts.

---

## Limits

- **False greenfield:** a repo may have sparse docs on purpose; **ask** the user if unsure.
- **False brownfield:** lots of files may be boilerplate; **read** the product root and one outcome before you trust counts alone.
- **CR** volume is a weak signal—teams vary in discipline.

When in doubt, use **modify** workflows on the artifact you touched; they are safe even when the tree is young.
