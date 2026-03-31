---
name: awesome-ai-research-writing
description: Academic paper writing, paper analysis, and research-side workflow kit for bilingual Chinese-English research work. Use when Codex needs to draft, translate, polish, shorten, expand, humanize, logic-check, explain long English sentences, read or analyze papers, produce reviewer-style reports, suggest model-improvement ideas from code or papers, generate paper-figure or UML prompts, or handle evidence-based research queries from notes, LaTeX, Markdown, PDFs, code, or full manuscripts. Especially useful when the user wants direct academic output rather than only a generic prompt template.
---
# Awesome AI Research Writing

## Overview

Use this skill to turn a prompt-library style repository into direct Codex behavior for academic writing, paper analysis, review, and research-side support.
Default to completing the task itself, not merely returning a reusable prompt, unless the user explicitly asks for prompt templates.

## Workflow Decision Tree

1. Identify the source artifact and target output.
   - Chinese draft -> English LaTeX
   - English LaTeX -> Chinese reading version
   - Chinese draft -> Chinese academic prose
   - Existing paragraph -> shorten, expand, polish, or humanize
   - English sentence -> grammar-aware Chinese translation
   - Paper or PDF -> structured reading or deep paper analysis
   - Thesis or full manuscript -> reviewer report or strict submission review
   - Experimental results -> analysis paragraph or plotting advice
   - Method description or code -> figure prompts, UML, or model-improvement suggestions
   - Fact-heavy research question -> verified answer with source-backed claims
2. Load the minimal reference file needed for the task.
3. Produce the final artifact directly in the requested language and format.
4. If the user asks for external skill recommendations or installation advice, read `references/upstream-skills.md`.

## Core Operating Rules

1. Use Chinese for commentary and explanations by default unless the user requests another language.
2. Keep the main edited artifact in the user's requested target language.
3. For LaTeX tasks, preserve formulas, labels, citations, and existing commands unless the user asks for structural edits.
4. Escape newly added LaTeX special characters such as `%`, `_`, and `&` when emitting LaTeX.
5. For paper prose, prefer connected paragraphs over bullet lists unless the user explicitly asks for outline form.
6. If evidence is insufficient, weaken claims instead of inventing results or overclaiming.
7. When a task is fact-heavy or time-sensitive, browse and verify before stating something as fact.
8. Treat prompt templates in the references as workflow guides and output contracts, not as the default end product.
9. When the user explicitly asks for a reusable prompt, return a prompt template with clear input slots instead of doing the task.

## Task Routing

Load `references/prompt-routing.md` when handling any of these tasks:

- bilingual translation for papers
- English or Chinese academic polishing
- shortening or expanding a paragraph
- logic checking
- figure title, table title, or caption generation
- experiment analysis writing
- lightweight reviewer-style review

Load `references/paper-reading.md` when:

- the user wants a structured reading framework for a paper or PDF
- the user wants a full paper analysis with background, method, experiments, and limitations

Load `references/research-assistant.md` when:

- the user wants evidence-backed research Q&A
- the user wants model-improvement ideas from code, papers, or experiment logs
- the user asks for model selection advice

Load `references/diagram-and-modeling.md` when:

- the user wants English prompts for academic figures
- the user asks what experiment plots to draw
- the user wants UML or system modeling output

Load `references/translation-and-humanize.md` when:

- the user wants long English sentence translation
- the user wants de-AI rewriting, especially Chinese Word-style text or English LaTeX text

Load `references/strict-review.md` when:

- the user wants a strict reviewer report
- the user wants a thesis-style submission review with a pass / no-pass recommendation

Load `references/prompt-index.md` when:

- the user asks what prompts or workflows this skill contains
- the user wants the repository-style directory of prompt entries

Load `references/upstream-skills.md` when:

- the user asks which skill to install or use
- the user wants a better tool for DOCX, full-paper authoring, or direct image generation
- the task is better served by a specialized upstream skill than by direct local rewriting

## Output Contracts

1. For direct editing tasks, return the edited artifact first and the explanation second.
2. For evaluation tasks, list concrete findings before summaries.
3. For experiment analysis, tie every claim to an observed number or explicit trend.
4. For paper analysis, distinguish author claims from your own interpretation.
5. For figure-prompt tasks, output the prompt set cleanly and keep the Chinese explanation brief.
6. For fact-verified answers, include concise source attribution after the answer.
7. For strict review tasks, keep the verdict explicit and tie it to concrete deficiencies.

## Related Skills

If the environment already has stronger installed skills such as `research-paper-writing` or `imagegen`, it is fine to combine this skill with them.
This skill is most useful as a bilingual routing and editing playbook built from a prompt collection, not as a replacement for every deeper domain skill.
