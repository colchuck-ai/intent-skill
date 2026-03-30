# intent-skill

An **[Agent Skill](https://agentskills.io)** for **intent documentation**: paired **product** and **engineering** trees under `docs/product/` and `docs/engineering/`, with a clear lifecycle from first draft through change and removal. The layout follows the open standard ([specification](https://agentskills.io/specification.md)): `SKILL.md` at the skill root, optional `assets/` and other supporting paths, all plain markdown—no bundled executables required.

The skill does not run code or validate your repo. It gives authors and assistants a **shared vocabulary**, **directory and naming rules**, **activity workflows** (develop, enumerate, modify, remove), and **templates** so intent stays traceable and reviewable. Any agent runtime that loads Agent Skills can use it; **Cursor** is one such host, not the only one.

## Contents

Everything you ship as the skill lives under **`intent/`**:

| Path | Role |
|------|------|
| [`intent/SKILL.md`](intent/SKILL.md) | Entrypoint: what the intent tree is, links to structure and workflows, high-level guidance. |
| [`intent/assets/`](intent/assets/) | Markdown templates for product and engineering artifacts. |
| [`intent/references/guides/`](intent/references/guides/) | **Structure** (trees, IDs, simple vs complex), optional **JTBD primer**, and **intent-tree phase** heuristics (`ls` / `grep`) for greenfield vs brownfield bias. |
| [`intent/references/workflows/`](intent/references/workflows/) | One file per activity workflow; each follows draft → AI-assisted review → independent review. |

Start from [`intent/SKILL.md`](intent/SKILL.md), then open [`intent/references/guides/structure.md`](intent/references/guides/structure.md) when you need paths and filenames, and [`intent/references/workflows/README.md`](intent/references/workflows/README.md) to pick a workflow.

## Using this repository

**As an Agent Skill:** install or register the `intent/` bundle per your tool’s Agent Skills workflow so assistants load [`intent/SKILL.md`](intent/SKILL.md) when intent documentation is relevant. Keep the directory structure intact so relative links resolve.

**In a product repo:** copy `intent/` beside your project (or use a release asset—see below) and maintain `docs/product/` and `docs/engineering/` as you prefer. The skill describes how those trees should look; it does not generate them automatically.

## Releases

[Semantic Release](https://semantic-release.gitbook.io/) tags versions from **conventional commits** and attaches the **`intent/`** directory as a GitHub release asset (see [`.releaserc.json`](.releaserc.json)). This package is **private** and is **not** published to npm.

## Development

```bash
npm ci
```

Hooks (via [Husky](https://typicode.github.io/husky/)) and [commitlint](https://commitlint.js.org/) enforce conventional commit messages locally. Use the same conventions on CI so release automation stays predictable.

## License

GPL-3.0 — see [`LICENSE`](LICENSE).
