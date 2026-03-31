# Awesome AI Research Writing for Codex

Turn a prompt-library style academic writing project into a Codex-native skill package.

This repository repackages the ideas and workflows from `Leey21/awesome-ai-research-writing` into a format that Codex can discover and use directly through `SKILL.md`.

## Why This Repo

The original project is strong as a prompt collection and skills index, but it is not a Codex-installable skill by itself.
This repository converts that material into a real Codex skill so the agent can:

- route writing tasks automatically
- draft or revise paper text directly instead of only returning prompts
- support bilingual Chinese-English academic writing
- keep detailed routing logic in references instead of bloating the main skill file

## Repository Overview

This repository currently provides one skill package:

- `awesome-ai-research-writing/`
  - `SKILL.md`: trigger description and working rules
  - `references/prompt-routing.md`: task routing for translation, polishing, shortening, expansion, logic check, de-AI rewriting, experiment analysis, and reviewer-style review
  - `references/upstream-skills.md`: guidance for when to use stronger upstream skills such as `research-paper-writing`, `humanizer`, `docx`, `doc-coauthoring`, and `canvas-design`
  - `agents/openai.yaml`: Codex UI metadata

## Typical Use Cases

- Draft an English paper paragraph from Chinese technical notes
- Translate English LaTeX into readable Chinese
- Polish Chinese or English academic prose
- Shorten or expand a paragraph while preserving technical content
- Humanize text that sounds AI-generated
- Generate figure titles, table titles, and captions
- Write experiment analysis from result tables
- Review a paper from a reviewer mindset

## Installation

Assume you are in the repository root.

### 1. Codex

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

After installation, restart Codex to pick up the new skill.

## Usage Example

Use `$awesome-ai-research-writing` to draft, polish, translate, or review an academic paper section.

Examples:

- `Use $awesome-ai-research-writing to rewrite this Chinese method draft into English LaTeX.`
- `Use $awesome-ai-research-writing to polish this Introduction and remove AI-sounding phrasing.`
- `Use $awesome-ai-research-writing to analyze the following experiment table in paper style.`
- `Use $awesome-ai-research-writing to review this paper section from a strict reviewer perspective.`

## Design Notes

This skill is intentionally lightweight in `SKILL.md`.
The main file only contains trigger logic, workflow rules, and output expectations.
Task-specific details are split into `references/` so Codex can load them only when needed.

This makes the skill more reliable than a plain README prompt dump while keeping context usage under control.

## Attribution

This repository is an adaptation of the ideas, prompt categories, and workflow intent from:

- `Leey21/awesome-ai-research-writing`

It does not aim to replace the original repository.
Instead, it converts that style of content into a Codex-friendly skill package format.
