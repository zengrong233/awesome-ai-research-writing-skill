# Awesome AI Research Writing Skill for Codex

[![Codex Skill](https://img.shields.io/badge/Codex-Skill-0A66C2)](https://github.com/zengrong233/awesome-ai-research-writing-skill)
[![Validation](https://img.shields.io/badge/quick__validate-passing-2EA043)](https://github.com/zengrong233/awesome-ai-research-writing-skill)
[![GitHub stars](https://img.shields.io/github/stars/zengrong233/awesome-ai-research-writing-skill?style=social)](https://github.com/zengrong233/awesome-ai-research-writing-skill)

[中文 README](./README.md)

Turn a prompt-library style academic writing project into a real Codex skill package, then extend it with reusable prompts for paper reading, review, translation, diagram planning, and research-side analysis.

This repository adapts the workflow categories from [Leey21/awesome-ai-research-writing](https://github.com/Leey21/awesome-ai-research-writing) into a Codex-native structure and adds a larger prompt library under `references/`.

## Why This Exists

The original project is strong as a prompt collection and a curated index of writing-related skills, but it is not a Codex-installable skill by itself.

This repository converts that style of content into a Codex-native package so the agent can:

- route academic writing and analysis tasks automatically
- complete the task directly instead of only returning a prompt template
- support bilingual Chinese-English research workflows
- keep specialized prompt logic in `references/` without bloating the main skill file

## Original Project vs This Repository

| Item | Original Project | This Repository |
| --- | --- | --- |
| Main form | README-style prompt collection | Standard Codex skill package |
| Directly installable in Codex | No | Yes |
| Triggered by `SKILL.md` | No | Yes |
| Best use | Reading prompts, discovering tools | Direct writing, revision, review, and research-side workflows inside Codex |
| Core adaptation | Prompt examples and workflow categories | Trigger description, routing rules, output contracts, references |

## Part I: Prompt And Workflow Catalog

For the authoritative clickable catalog that stays aligned with the actual skill references, see:

- [prompt-index.md](./awesome-ai-research-writing/references/prompt-index.md)

The capability surface is easiest to think about in four groups:

- Translation and rewriting: Chinese-English conversion, Chinese rewriting, shortening, expansion, polishing, and de-AI rewriting
- Reading and analysis: structured paper reading, paper analysis, experiment analysis, verified Q&A, and research-improvement planning
- Review and decision support: reviewer-style review, strict thesis review, and model selection
- Figures and modeling: paper figures, experiment plot recommendation, figure/table titles, and UML-style modeling

## Part II: Related Skill Resources

- [Skill configuration](./awesome-ai-research-writing/SKILL.md)
- [Prompt catalog](./awesome-ai-research-writing/references/prompt-index.md)
- [Usage examples](./awesome-ai-research-writing/references/prompt-index.md#usage-examples)
- [Upstream skill handoff advice](./awesome-ai-research-writing/references/upstream-skills.md)

## Repository Overview

```text
awesome-ai-research-writing/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── prompt-index.md
    ├── prompt-routing.md
    ├── paper-reading.md
    ├── research-assistant.md
    ├── diagram-and-modeling.md
    ├── translation-and-humanize.md
    ├── strict-review.md
    └── upstream-skills.md
```

## Installation

Assume you are in the repository root.

### Option 1: Manual Install

Unix-like / macOS / Linux:

```bash
mkdir -p "$CODEX_HOME/skills"
cp -R awesome-ai-research-writing "$CODEX_HOME/skills/"
```

If `CODEX_HOME` is unset, use the default Codex directory:

```bash
mkdir -p "$HOME/.codex/skills"
cp -R awesome-ai-research-writing "$HOME/.codex/skills/"
```

Windows PowerShell:

```powershell
$codexHome = if ($env:CODEX_HOME) { $env:CODEX_HOME } else { Join-Path $env:USERPROFILE ".codex" }
New-Item -ItemType Directory -Force -Path (Join-Path $codexHome "skills") | Out-Null
Copy-Item -Recurse -Force ".\awesome-ai-research-writing" (Join-Path $codexHome "skills")
```

### Option 2: Install With The Codex Skill Installer

If you already have the Codex `skill-installer` system skill available, install directly from GitHub.

Unix-like / macOS / Linux:

```bash
python "$CODEX_HOME/skills/.system/skill-installer/scripts/install-skill-from-github.py" \
  --repo zengrong233/awesome-ai-research-writing-skill \
  --path awesome-ai-research-writing
```

Windows PowerShell:

```powershell
$codexHome = if ($env:CODEX_HOME) { $env:CODEX_HOME } else { Join-Path $env:USERPROFILE ".codex" }
python (Join-Path $codexHome "skills\.system\skill-installer\scripts\install-skill-from-github.py") `
  --repo zengrong233/awesome-ai-research-writing-skill `
  --path awesome-ai-research-writing
```

After installation, restart Codex to pick up the new skill.

## Design Principles

This skill intentionally keeps `SKILL.md` lean.

The main file only keeps:

- trigger description
- workflow guidance
- output contracts

Detailed prompt logic lives in `references/`, so Codex can load it on demand instead of carrying everything in one oversized skill file.

## Attribution

This repository is an adaptation of the ideas, task categories, and workflow intent from:

- [Leey21/awesome-ai-research-writing](https://github.com/Leey21/awesome-ai-research-writing)

It does not aim to replace the original repository.
It exists to convert that style of material into a Codex-friendly skill package format.

## License

This repository includes original packaging work for Codex plus adapted structure inspired by upstream material.
See [LICENSE](./LICENSE) for the exact scope and limitations.
