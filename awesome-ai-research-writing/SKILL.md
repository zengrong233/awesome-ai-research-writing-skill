---
name: awesome-ai-research-writing
description: Academic paper writing and revision workflow kit for bilingual Chinese-English research writing. Use when Codex needs to draft, translate, polish, shorten, expand, humanize, logic-check, title/caption, analyze experiments, or reviewer-check paper content from notes, LaTeX, Markdown, Word-style text, or a full paper. Especially useful when the user wants direct writing help rather than a generic prompt template.
---
# Awesome AI Research Writing

## Overview

Use this skill to convert a prompt-library style repository into direct Codex writing behavior for academic work.
Default to completing the writing or review task itself, not merely returning a reusable prompt, unless the user explicitly asks for prompt templates.

## Workflow Decision Tree

1. Identify the source artifact and target output.
   - Chinese draft -> English LaTeX
   - English LaTeX -> Chinese reading version
   - Chinese draft -> Chinese academic prose
   - Existing paragraph -> shorten, expand, polish, or humanize
   - Figure/table description -> title or caption
   - Experimental results -> analysis paragraph
   - Full paper or PDF -> reviewer-style assessment
2. Match the task to the closest route in `references/prompt-routing.md`.
3. Produce the final artifact directly in the requested language and format.
4. If the user asks for external skill recommendations or installation advice, read `references/upstream-skills.md`.

## Core Operating Rules

1. Use Chinese for commentary and explanations by default unless the user requests another language.
2. Keep the main edited artifact in the user's requested target language.
3. For LaTeX tasks, preserve formulas, labels, and existing commands unless the user asks for structural edits.
4. Escape newly added LaTeX special characters such as `%`, `_`, and `&` when emitting LaTeX.
5. For paper prose, prefer connected paragraphs over bullet lists unless the user explicitly asks for outline form.
6. If evidence is insufficient, weaken claims instead of inventing results or overclaiming.
7. Treat prompt templates in the references as style guides and output contracts, not as default end products.
8. When the user explicitly asks for a reusable prompt, return a prompt template with clear input slots instead of doing the task.

## Task Routing

Load `references/prompt-routing.md` when handling any of these tasks:

- bilingual translation for papers
- English or Chinese academic polishing
- shortening or expanding a paragraph
- logic checking
- de-AI / humanizing text
- figure title, table title, or caption generation
- experiment analysis writing
- reviewer-style paper assessment

Load `references/upstream-skills.md` when:

- the user asks which skill to install or use
- the user wants a better tool for DOCX, long-form coauthoring, diagram creation, or full-paper authoring
- the task is better served by an upstream specialized skill than by direct local rewriting

## Output Contracts

1. For direct editing tasks, return the edited artifact first and the explanation second.
2. For evaluation tasks, list concrete findings before summaries.
3. For experiment analysis, tie every claim to an observed number or explicit trend.
4. For paper review, separate strengths, critical weaknesses, and revision advice.
5. For title and caption tasks, output concise publishable text rather than multiple casual variants unless the user asks for options.

## Related Skills

If the environment already has a stronger installed paper-writing skill, it is fine to combine this skill with it.
This skill is most useful as a bilingual routing and editing playbook built from a prompt collection, not as a replacement for every deeper domain skill.
