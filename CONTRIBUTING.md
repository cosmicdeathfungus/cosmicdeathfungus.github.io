# Contributing to the CDF NAC Protocol Documentation

Thank you for contributing. This document is the community's living record of the NAC Protocol. Every improvement matters.

## What You Can Contribute

| Type | Welcome? | Notes |
|---|---|---|
| Experience reports | ✅ Yes | First-person accounts in `docs/nac-protocol/experiences.md` or `docs/community/experiences.md` |
| Source citations | ✅ Yes | PubMed/DOI links strongly preferred |
| Corrections | ✅ Yes | If something is factually wrong, open an issue or PR |
| Translations | ✅ Yes | New file under `docs/` with language prefix (e.g. `de-protocol.md`) — see `docs/community/translations.md` |
| Protocol changes | ⚠️ Authors only | Core protocol changes require approval from Peribsen or MacLir |
| New supplement sections | ⚠️ Review required | Open an issue first |

## Workflow

1. **Fork** the repository
2. **Create a branch**: `git checkout -b your-branch-name`
3. **Make changes** — follow the style guide below
4. **Commit** with a clear message: `git commit -m "Add experience report: 6-week NAC protocol"`
5. **Open a Pull Request** against `main`
6. A maintainer reviews and merges

## Style Guide

### Markdown

- Use `##` for section headers, `###` for subsections
- Bold (`**`) for key terms on first use
- Use admonition blocks for warnings and notes:

```markdown
!!! warning "Important"
    Text here.

!!! note
    Text here.
```

### Citations

- Always prefer peer-reviewed sources
- Format: `[Author et al., Year](https://doi.org/...)`
- PubMed links: `https://pubmed.ncbi.nlm.nih.gov/PMID/`
- Do not cite social media posts as evidence for scientific claims
- Community experience counts as anecdote, not evidence — label it as such

### Tone

- Clear, direct, informative
- Avoid sensationalism
- Acknowledge uncertainty where it exists
- No medical claims — use "community members report" or "some evidence suggests"

### Disclaimer

Every page that describes a protocol or supplement must include the disclaimer admonition:

```markdown
!!! danger "Medical Disclaimer"
    This is not medical advice. This is community-documented information.
    Consult a qualified healthcare professional before beginning any protocol.
```

## File Naming

- Lowercase, hyphens: `black-seed-oil.md` ✅
- No spaces or underscores: `black_seed_oil.md` ❌

## Branch Protection

The `main` branch is protected. Direct pushes are disabled. All changes go through Pull Requests.

## Code of Conduct

Be accurate. Be respectful. Cite your sources. This community exists to preserve and share health information — that is a responsibility, not a platform.
