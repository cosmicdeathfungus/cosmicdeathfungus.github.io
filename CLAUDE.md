# CLAUDE.md

Guidance for Claude Code (and any AI agent) working in this repository.

## What This Project Is

This is the **canonical, version-controlled, search-engine-indexed source** for
the community-maintained **CDF NAC Protocol** documentation, originally authored
by **Peribsen & MacLir**. It is published as a static site via **MkDocs +
Material theme** to GitHub Pages at <https://cosmicdeathfungus.github.io>.

The site exists so that health information that may be restricted or removed on
other platforms (e.g. Reddit) has a permanent, forkable, archival home. Reddit
is ephemeral; Git is archival.

## Critical Boundaries — Read First

This repository concerns a **health/medical protocol**. Two hard rules:

1. **NEVER invent, generate, or author medical content.** Do not write
   protocol steps, dosages, supplement recommendations, timing, or
   health claims from your own knowledge. The protocol content is the
   **authors' source of truth**. Your role is to build and maintain the
   *infrastructure* (site structure, navigation, build, CI, formatting) and to
   *transcribe/format* content that the authors or community explicitly provide
   (e.g. from the source PDF or a PR).
   - When content is missing, leave a clearly-marked placeholder:
     `<!-- TODO: Content to be supplied by authors from source PDF -->`
   - Generating medical dosing text from scratch will (correctly) be blocked by
     content-safety filters and is out of scope regardless.

2. **Every page describing a protocol or supplement must carry the medical
   disclaimer admonition** (see below). No exceptions.

## Architecture

```
cosmicdeathfungus.github.io/
├── docs/                       # All site content (Markdown). MkDocs source root.
│   ├── index.md                # Landing page (SEO-critical entry point)
│   ├── overview/               # What CDF is, the organisms involved
│   ├── origins-of-disease/     # Inflammation / disease-connection background
│   ├── nac-protocol/           # THE CORE. Highest-priority content.
│   ├── maintenance-protocol/   # Long-term maintenance
│   ├── science/                # Per-supplement evidence sections (cited)
│   ├── history/                # Mythological / contextual material (optional)
│   ├── community/              # Contributing, experiences, translations
│   ├── legal/                  # disclaimer.md, license.md
│   └── assets/                 # PDF source, images
├── mkdocs.yml                  # Site config + navigation. Edit nav here.
├── .github/workflows/deploy.yml# CI: builds with `mkdocs build --strict`, deploys to Pages
├── CNAME                       # Custom-domain placeholder (documented, inactive)
├── CODEOWNERS                  # Review authority (authors own protocol/legal)
├── CONTRIBUTING.md             # Contributor workflow + style guide
├── LICENSE                     # CC BY-SA 4.0 + medical disclaimer
└── README.md
```

## Common Commands

```bash
# Install toolchain
pip install mkdocs-material

# Live-preview locally at http://127.0.0.1:8000
mkdocs serve

# Build the static site into ./site (must pass before pushing)
mkdocs build --strict
```

The CI uses `--strict`, so **broken links, missing nav targets, or referenced
files that don't exist will fail the build**. Always run `mkdocs build --strict`
locally before committing structural changes. Every file listed in the `nav:`
block of `mkdocs.yml` must exist, and vice-versa.

## Content & Style Conventions

- Filenames: lowercase-with-hyphens (`black-seed-oil.md`), never underscores.
- Headings: `#` once per page (page title), `##`/`###` for structure.
- Citations: peer-reviewed sources preferred, format
  `[Author et al., Year](https://doi.org/...)` or PubMed links. Never cite
  social media as scientific evidence. Label community anecdotes as anecdote.
- Required disclaimer block on protocol/supplement pages:

  ```markdown
  !!! danger "Medical Disclaimer"
      This is not medical advice. This is community-documented information.
      Consult a qualified healthcare professional before beginning any protocol.
  ```

- Use Material admonitions (`!!! note`, `!!! warning`, `!!! danger`) for callouts.

## Editing Navigation

The nav tree lives in `mkdocs.yml` under `nav:`. When you add a page:
1. Create the `.md` file under `docs/`.
2. Add it to `nav:` in the correct section.
3. Run `mkdocs build --strict` to confirm it resolves.

The **NAC Protocol** section is the core artifact and should remain prominent in
the navigation order.

## Workflow & Git

- Default development happens on a feature branch; PRs target `main`.
- `main` is intended to be branch-protected; deploys trigger on push to `main`.
- **Direct `git push` from this environment is denied** (the credential lacks
  write scope). Use the GitHub MCP tools (`mcp__github__push_files`,
  `mcp__github__create_pull_request`, etc.) to write to the remote.
- Repo scope is restricted to `cosmicdeathfungus/cosmicdeathfungus.github.io`.
- Do NOT open a pull request unless explicitly asked.

## Versioning

Protocol versions are tracked as **git tags** (e.g. `v2.02`). A new protocol
release from the authors arrives as a PR and is tagged on merge.

## Licensing

Content is **CC BY-SA 4.0** (Attribution + ShareAlike). Any derivative must
remain under the same license. Do not introduce content under an incompatible
license.

## Resilience / Mirroring

The site is designed to survive platform takedowns. Long-term plans (not yet
configured): a Codeberg mirror (`git remote add codeberg ...`) and Wayback
Machine submissions after releases. Mention these when relevant but do not
configure external remotes without explicit instruction.
