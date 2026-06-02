---
title: Translations
description: How to translate the CDF NAC Protocol documentation into other languages.
tags:
  - community
  - translations
---

# Translations

Health information should not be locked behind a single language. Translations
are **highly welcome**.

## Available Languages

| Language | Status | Maintainer |
| --- | --- | --- |
| English | :white_check_mark: Source | community |

<!-- TODO: Add rows as translations are contributed, e.g.:
     | Deutsch | :construction: In progress | @handle | -->

## How to Translate

1. **Pick a page** to translate (start with high-value pages: the landing page
   and the NAC Protocol section).
2. **Create a translated copy** following the file-naming convention below.
3. **Keep the structure identical** — same headings, same admonitions, and the
   **same medical disclaimer** (translated).
4. **Open a Pull Request.** A maintainer who reads the language will review it.

## File-Naming Convention

Prefix translated files or directories with the
[ISO 639-1 language code](https://en.wikipedia.org/wiki/List_of_ISO_639_language_codes):

```
docs/de/nac-protocol/protocol.md   # German
docs/es/nac-protocol/protocol.md   # Spanish
```

The exact navigation structure for multi-language support will be finalised as
the first translations arrive — open an issue to coordinate before starting a
large effort, so we don't duplicate work.

## Translation Principles

- **Accuracy over fluency** for medical/scientific terms — keep Latin organism
  names and cite the same sources.
- **Never localise away the disclaimer.** Every translated protocol/supplement
  page must keep an equivalent medical disclaimer.
- **Mark machine-assisted drafts** as such so a human reviewer can check them.
