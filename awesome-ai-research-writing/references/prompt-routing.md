# Writing Workflows

Use the matching entry for direct academic editing. The [index](prompt-index.md) lists all entries. Existing anchors remain usable.

## Contents

- Translation: [中转英](#cn-to-en) · [英转中](#en-to-cn) · [中转中](#cn-to-cn)
- Editing: [缩写](#shorten) · [扩写](#expand) · [英文润色](#polish-en) · [中文润色](#polish-zh) · [逻辑检查](#logic-check)
- Natural prose: [LaTeX 英文](#de-ai-latex-en) · [Word 中文](#de-ai-word-zh)
- Figures: [架构图](#paper-figure-outline) · [实验选图](#experiment-figure-recommendation) · [图标题](#figure-title) · [表标题](#table-title)
- Analysis and decisions: [实验分析](#experiment-analysis) · [Reviewer 审查](#reviewer-review) · [模型选择](#model-selection)

## Shared editing contract

The user's requested language, length, format, and template take precedence over defaults here. Otherwise preserve the source format and return the edited text first. Provide back-translation, alternatives, or a change log only when requested or needed to explain a material ambiguity. If the user requests the legacy multi-part format, use `Part 1 [LaTeX / Refined Text]`, `Part 2 [Translation / Logic Flow / Review Comments]`, and, where requested, `Part 3 [Modification Log]`.

Preserve technical meaning, numbers, units, conditions, citation keys, math, labels, and commands. In LaTeX, escape new prose characters contextually; leave math subscripts, alignment symbols, and existing escapes intact. Use tense appropriate to the statement: descriptions and established facts often use present tense; completed experiments often use past tense. Follow field and manuscript conventions.

Improve clarity and logical connection using standard academic vocabulary. Keep useful lists, notation, and formatting; do not add decorative emphasis. Do not replace a precise term merely for variety. Flag unsupported claims instead of polishing them into greater certainty.

<a id="cn-to-en"></a>
## 1. 中转英

Translate Chinese notes or prose into precise English academic text. Infer the relationship between fragments only when the source supports it. Preserve established translations of terms and abbreviations; introduce a short terminology mapping only when consistency needs explanation.

Use LaTeX when requested or when editing a LaTeX source. For Word/plain-text input, do not add LaTeX commands by default. Keep meaning and qualifiers intact rather than translating colloquial emphasis into stronger scientific claims.

Return the English artifact. Add Chinese back-translation only on request; keep it separate from the copy-ready text.

<a id="en-to-cn"></a>
## 2. 英转中

Choose the mode from the request and source context:

- **Editable manuscript translation:** preserve LaTeX commands, math, citation keys, labels, and cross-references. Translate prose and translatable command arguments only; leave identifiers intact.
- **Reading version:** translate fluent Chinese and render math clearly. Convert formatting commands to readable text. Retain citation and cross-reference meaning with resolved numbers when available, or readable markers such as `[引用: smith2024]` and `[图: fig:overview]` when unresolved. Never invent a reference number. Remove indexing-only syntax only in this reading mode, without losing the source relationship.

If the request simply says “translate” and includes editable LaTeX, preserve that format. A request to explain or produce a reading version selects reading mode. Retain ambiguity in the source and briefly flag errors that affect interpretation; do not silently change the result being reported.

Return the Chinese translation; explain syntax only if asked.

<a id="cn-to-cn"></a>
## 3. 中转中

Turn rough Chinese research notes into connected academic prose, with one main point per paragraph. Reorder material when needed for a clear argument; do not fill missing mechanisms or results. Use contemporary academic Chinese, full-width punctuation, and accurate technical terms. Preserve a supplied Word, Markdown, or LaTeX format.

Return the revised text. Include a short logic-flow explanation only if requested or needed to explain a substantive reorganization.

<a id="shorten"></a>
## 4. 缩写

Meet the user's word/character limit or compression ratio. If no target is supplied, remove redundancy while retaining the argument and important detail; no fixed word reduction applies. For a strict limit, state the counting basis when it matters (e.g., English words excluding equations).

Compress repeated context, wordy clauses, and redundant transitions before deleting evidence. Preserve comparators, baselines, conditions, limitations, citations, and numeric values. If the limit cannot accommodate essential content, explain the specific conflict and offer a shorter version with any omitted detail identified outside the artifact.

Return the shortened text in the source format. Report the count when requested or necessary to demonstrate a hard limit.

<a id="expand"></a>
## 5. 扩写

Expand to the requested depth or length by explaining supported premises, definitions, and logical transitions. Without a target, add only what makes the supplied argument understandable. Do not manufacture a mechanism, result, citation, experiment, or causal explanation to reach a word count.

Separate proposed additions requiring evidence from the copy-ready paragraph. If a crucial premise is absent, ask a focused question or mark the gap explicitly in a working draft rather than presenting a guess as fact.

Return the expanded text, followed only by necessary evidence gaps or requested notes.

<a id="polish-en"></a>
## 6. 表达润色（英文论文）

Fix grammar, spelling, articles, punctuation, terminology, and unclear sentence structure. Keep already effective wording. Preserve the author's register and the venue's conventions; avoid contractions or informal language where inappropriate. Possessives, passive voice, and punctuation are choices governed by clarity, not universal bans.

Retain abbreviations, commands such as `\cite`, `\ref`, `\eg`, and `\ie`, and all math. Correct language without upgrading evidence or removing limitations. Return the polished English text in its original format.

<a id="polish-zh"></a>
## 7. 表达润色（中文论文）

Make necessary changes to unclear logic, grammar, colloquial wording, and inconsistent terminology. Keep publishable passages unchanged. Avoid officialese, redundant connectives, and translationese. For Word-ready requests, return plain text without Markdown decoration; preserve mathematical and technical content.

Return the full revised passage or the original if no change is needed. Add review comments only when requested or needed to clarify a substantive issue.

<a id="logic-check"></a>
## 8. 逻辑检查

Check contradictions, undefined or drifting terms, missing premises, unsupported causal or universal claims, inconsistent comparisons, and mismatches between numbers and conclusions. Distinguish scientific reasoning problems from optional stylistic edits. Do not assume prior revision or complete context.

Return concrete issues with a quoted phrase or location, the logical problem, and a repair direction. If none are found, say “在所提供文本范围内，未发现实质性逻辑问题。” Do not certify an unseen paper or unprovided experiments.

<a id="de-ai-latex-en"></a>
## 9. 去 AI 味（LaTeX 英文）

Use [natural English LaTeX editing](translation-and-humanize.md#de-ai-latex-en). Follow the shared editing contract; the legacy three-part format is available on request.

<a id="de-ai-word-zh"></a>
## 10. 去 AI 味（Word 中文）

Use [natural Chinese editing](translation-and-humanize.md#de-ai-word-zh). Return copy-ready prose first; a modification log is optional.

<a id="paper-figure-outline"></a>
## 11. 论文架构图

For actual editable figures, use [framework figures](framework-figures.md). For explicitly requested prompts, use [figure prompts](diagram-and-modeling.md#paper-figure-prompts). Keep the semantic structure grounded in the method rather than inventing modules for visual symmetry.

<a id="experiment-figure-recommendation"></a>
## 12. 实验绘图推荐

Use [plot recommendations](diagram-and-modeling.md#experiment-figure-recommendation) for advice or [scientific data figures](scientific-data-figures.md) to create the figure. State the question, required data, proposed encoding, and supported inference.

<a id="figure-title"></a>
## 13. 生成图的标题

Return the requested title or caption only, in the requested language; default to English when translating a Chinese description for an English paper. Follow the supplied venue/template capitalization and numbering. Otherwise use concise sentence case and omit an automatic `Figure 1:` prefix.

A title names the subject or comparison. A caption also explains panels, encodings, abbreviations, conditions, and uncertainty as needed for independent reading. Do not call a difference “significant” without supplied statistical support. Preserve symbols and apply LaTeX escaping only for LaTeX output.

<a id="table-title"></a>
## 14. 生成表的标题

Follow the same title/caption distinction and venue formatting as figure titles. Identify the dataset, comparison, or ablation precisely. Define units, metric direction, best-value formatting, and uncertainty in a full caption or note when supported. Do not invent the meaning of boldface or an unexplained `±`.

Return the title or caption only unless missing information prevents an accurate one.

<a id="experiment-analysis"></a>
## 15. 实验分析

Read the supplied table, logs, or values before drafting. Identify metric direction, comparable conditions, denominators, units, and whether values are per-run or aggregate. Calculate differences explicitly and check them: 80% to 84% is +4 percentage points or +5% relative, not +4% relative.

Lead with the main supported finding, then the comparison and its conditions, followed by a relevant trade-off or limit. Avoid restating every cell. Do not infer significance from point estimates or a causal mechanism from correlation alone. Label a mechanism as a hypothesis unless the experiment isolates it.

Return prose in the requested format. Use `\paragraph{...}` only if requested or consistent with the supplied template. For plots, use [scientific data figures](scientific-data-figures.md).

<a id="reviewer-review"></a>
## 16. 论文整体以 Reviewer 视角进行审视

Use [reviewer review](strict-review.md#reviewer-review). Findings need manuscript locations and evidence; partial input supports a partial review.

<a id="model-selection"></a>
## 17. 模型选择

Use [model selection](research-assistant.md#model-selection). Compare the actual constraints and recommend a testable choice with trade-offs.
