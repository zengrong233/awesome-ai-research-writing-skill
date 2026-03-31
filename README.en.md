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

## Part I: Prompt Collection

- [Chinese to English](./awesome-ai-research-writing/references/prompt-routing.md#cn-to-en)
- [English to Chinese](./awesome-ai-research-writing/references/prompt-routing.md#en-to-cn)
- [Chinese to Chinese rewriting](./awesome-ai-research-writing/references/prompt-routing.md#cn-to-cn)
- [Shorten](./awesome-ai-research-writing/references/prompt-routing.md#shorten)
- [Expand](./awesome-ai-research-writing/references/prompt-routing.md#expand)
- [English polishing](./awesome-ai-research-writing/references/prompt-routing.md#polish-en)
- [Chinese polishing](./awesome-ai-research-writing/references/prompt-routing.md#polish-zh)
- [Logic check](./awesome-ai-research-writing/references/prompt-routing.md#logic-check)
- [De-AI for English LaTeX](./awesome-ai-research-writing/references/translation-and-humanize.md#de-ai-latex-en)
- [De-AI for Chinese Word-style text](./awesome-ai-research-writing/references/translation-and-humanize.md#de-ai-word-zh)
- [Paper architecture figure](./awesome-ai-research-writing/references/diagram-and-modeling.md#paper-figure-prompts)
- [Experiment figure recommendation](./awesome-ai-research-writing/references/diagram-and-modeling.md#experiment-figure-recommendation)
- [Figure title generation](./awesome-ai-research-writing/references/prompt-routing.md#figure-title)
- [Table title generation](./awesome-ai-research-writing/references/prompt-routing.md#table-title)
- [Experiment analysis](./awesome-ai-research-writing/references/prompt-routing.md#experiment-analysis)
- [Reviewer-style full review](./awesome-ai-research-writing/references/strict-review.md#reviewer-review)
- [Model selection](./awesome-ai-research-writing/references/research-assistant.md#model-selection)
- [Structured paper reading](./awesome-ai-research-writing/references/paper-reading.md#structured-reading)
- [Paper analysis](./awesome-ai-research-writing/references/paper-reading.md#paper-analysis)
- [Research expert for code and ideas](./awesome-ai-research-writing/references/research-assistant.md#research-expert)
- [Verified research assistant](./awesome-ai-research-writing/references/research-assistant.md#verified-assistant)
- [Scientific figure prompt generator](./awesome-ai-research-writing/references/diagram-and-modeling.md#paper-figure-prompts)
- [UML modeling analyst](./awesome-ai-research-writing/references/diagram-and-modeling.md#uml-modeling)
- [Long English sentence translation](./awesome-ai-research-writing/references/translation-and-humanize.md#long-sentence-translation)
- [Strict thesis submission review](./awesome-ai-research-writing/references/strict-review.md#strict-thesis-review)

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
