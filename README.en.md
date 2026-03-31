# Awesome AI Research Writing Skill for Codex

[![Codex Skill](https://img.shields.io/badge/Codex-Skill-0A66C2)](https://github.com/zengrong233/awesome-ai-research-writing-skill)
[![Validation](https://img.shields.io/badge/quick__validate-passing-2EA043)](https://github.com/zengrong233/awesome-ai-research-writing-skill)
[![GitHub stars](https://img.shields.io/github/stars/zengrong233/awesome-ai-research-writing-skill?style=social)](https://github.com/zengrong233/awesome-ai-research-writing-skill)

[中文 README](./README.md)

Turn a prompt-library style academic writing project into a real Codex skill package.

This repository adapts the ideas and workflow categories from [Leey21/awesome-ai-research-writing](https://github.com/Leey21/awesome-ai-research-writing) into a format that Codex can discover and use directly through `SKILL.md`.

## Why This Exists

The original project is strong as a prompt collection and a curated index of writing-related skills, but it is not a Codex-installable skill by itself.

This repository converts that style of content into a Codex-native package so the agent can:

- route academic writing tasks automatically
- perform the writing task directly instead of only returning a prompt template
- support bilingual Chinese-English paper writing
- keep detailed task logic in `references/` without bloating the main skill file

## Original Project vs This Repository

| Item | Original Project | This Repository |
| --- | --- | --- |
| Main form | README-style prompt collection | Standard Codex skill package |
| Directly installable in Codex | No | Yes |
| Triggered by `SKILL.md` | No | Yes |
| Best use | Reading prompts, discovering tools | Direct writing, revision, and review inside Codex |
| Core adaptation | Prompt examples and workflow categories | Trigger description, routing rules, output contracts, references |

## What The Skill Covers

The skill is designed for common academic writing tasks such as:

- Chinese draft -> English LaTeX
- English LaTeX -> readable Chinese
- Chinese academic rewriting
- English academic polishing
- shortening or expanding a paragraph
- de-AI / humanizing text
- logic checking
- figure titles, table titles, and captions
- experiment analysis
- reviewer-style paper assessment

## Repository Overview

This repository currently provides one installable skill package:

```text
awesome-ai-research-writing/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── prompt-routing.md
    └── upstream-skills.md
```

### File Roles

- `SKILL.md`
  - defines what the skill does
  - tells Codex when to trigger it
  - provides core workflow and output rules
- `references/prompt-routing.md`
  - maps user requests to the right writing behavior
  - keeps task-specific details out of the main skill file
- `references/upstream-skills.md`
  - explains when to prefer stronger specialized skills such as `research-paper-writing`, `humanizer`, `docx`, `doc-coauthoring`, and `canvas-design`
- `agents/openai.yaml`
  - provides Codex UI metadata

## Installation

Assume you are in the repository root.

### Option 1: Manual Install

Copy the skill into `$CODEX_HOME/skills/`:

```bash
mkdir -p "$CODEX_HOME/skills"
cp -R awesome-ai-research-writing "$CODEX_HOME/skills/"
```

If `CODEX_HOME` is unset, use the default Codex directory:

```bash
mkdir -p "$HOME/.codex/skills"
cp -R awesome-ai-research-writing "$HOME/.codex/skills/"
```

### Option 2: Install With The Codex Skill Installer

If you already have the Codex `skill-installer` system skill available, install directly from GitHub:

```bash
python "$CODEX_HOME/skills/.system/skill-installer/scripts/install-skill-from-github.py" \
  --repo zengrong233/awesome-ai-research-writing-skill \
  --path awesome-ai-research-writing
```

After installation, restart Codex to pick up the new skill.

## Quick Start

Use `$awesome-ai-research-writing` to draft, polish, translate, or review academic writing.

Examples:

- `Use $awesome-ai-research-writing to rewrite this Chinese method draft into English LaTeX.`
- `Use $awesome-ai-research-writing to polish this Introduction and remove AI-sounding phrasing.`
- `Use $awesome-ai-research-writing to shorten this paragraph by about 10 words without losing technical meaning.`
- `Use $awesome-ai-research-writing to analyze the following experiment table in paper style.`
- `Use $awesome-ai-research-writing to review this paper section from a strict reviewer perspective.`

## Design Principles

This skill intentionally keeps `SKILL.md` lean.

The main file contains:

- trigger description
- workflow guidance
- output contracts

The details live in `references/`, so Codex can load them only when needed.
This keeps the skill closer to a real production package than to a long prompt dump.

## Relationship to Upstream Skills

This repository does not try to replace every specialized writing skill.
Instead, it acts as a practical bilingual writing-and-routing layer for Codex.

It is especially useful when the user wants direct help on:

- translation
- paragraph rewriting
- academic polishing
- reviewer-style diagnosis

For deeper workflows, the skill can defer to stronger upstream tools such as:

- `research-paper-writing`
- `humanizer`
- `docx`
- `doc-coauthoring`
- `canvas-design`

## Attribution

This repository is an adaptation of the ideas, task categories, and workflow intent from:

- [Leey21/awesome-ai-research-writing](https://github.com/Leey21/awesome-ai-research-writing)

It does not aim to replace the original repository.
It exists to convert that style of material into a Codex-friendly skill package format.

## License

This repository includes original packaging work for Codex plus adapted structure inspired by upstream material.
See [LICENSE](./LICENSE) for the exact scope and limitations.
