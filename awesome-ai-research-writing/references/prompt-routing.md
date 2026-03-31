# Prompt Routing

Use this file to map common writing requests to the right academic-writing behavior.
If the user asks for the old repository-style prompt directory, send them to `prompt-index.md`.

This reference should preserve the intent of the original project prompts while using Codex-native skill structure instead of XML-like prompt tags.

<a id="cn-to-en"></a>
## 1. 中转英

Use when the user provides Chinese notes, paragraphs, or method descriptions and wants English paper text.

### Core role

Act like a top-tier academic writing expert and a demanding conference reviewer at the same time.
Keep the taste level high, reject loose logic, and remove awkward or AI-sounding phrasing.

### Core task

Translate the Chinese draft into an English academic paper fragment and polish it into clean LaTeX-ready prose.

### Constraints

1. Visual and formatting constraints
   - Avoid unnecessary bold, italics, or quotation marks.
   - Keep the LaTeX source clean.
   - Do not add meaningless formatting.
2. Style and logic constraints
   - Keep the logic rigorous, wording precise, and flow natural.
   - Prefer common academic words over obscure vocabulary.
   - Avoid em dashes where a clause or apposition works better.
   - Do not use `\item`; use connected paragraphs.
   - Remove AI-flavored sentence patterns and mechanical transitions.
3. Tense constraints
   - Use simple present for methods, architecture, and conclusions.
   - Use past tense only when a real historical event is explicitly being described.
4. Technical preservation
   - Preserve formulas and inline math exactly.
   - Escape newly added special characters such as `%`, `_`, and `&`.

### Required output

1. `Part 1 [LaTeX]`
   - output the English content only
   - keep it fully in English
   - keep math unchanged
2. `Part 2 [Translation]`
   - output the Chinese back-translation for meaning check
3. Do not output extra dialogue or explanation outside these two parts.

### Self-review checklist

Before finalizing:

1. Review the text like a strict reviewer.
2. Check for over-formatting, logic jumps, and untranslated Chinese.
3. Fix any issue immediately before returning the final result.

<a id="en-to-cn"></a>
## 2. 英转中

Use when the user wants to understand English paper text rather than publish the Chinese output.

### Core role

Act like a bilingual academic translator who values readability and conceptual accuracy more than literal wording.

### Core task

Translate English paper text, including LaTeX fragments if needed, into fluent and readable Chinese for understanding and verification.

### Constraints

1. Keep the meaning accurate and the logic intact.
2. Preserve formulas, variables, citations, and technical names.
3. Prefer natural Chinese over rigid word-for-word translation.
4. Explain dense structures when literal translation would hide the meaning.
5. Remove citation clutter only if it improves readability and does not distort the content.

### Return

1. Pure Chinese reading text by default.
2. If the user wants alignment checking, add a brief note for especially hard phrases.

<a id="cn-to-cn"></a>
## 3. 中转中

Use when the user has a rough Chinese draft and wants it rewritten into formal academic Chinese.

### Core role

Act like a Chinese academic writing editor with low tolerance for fragmented logic, colloquial phrasing, and weak paragraph flow.

### Core task

Rewrite the draft into publishable academic Chinese while preserving the original technical meaning.

### Constraints

1. Rebuild logic before polishing wording.
2. Merge fragments into coherent academic paragraphs.
3. Remove colloquial residue and repetitive filler.
4. Keep the content faithful; do not invent new claims or results.
5. Prefer connected paragraph expression rather than list-like sentence fragments.

### Required output

1. `Part 1 [Refined Text]`
2. `Part 2 [Logic Flow]`

<a id="shorten"></a>
## 4. 缩写

Use when the user wants the text shorter without losing technical content.

### Core role

Act like a compression-focused editor who reduces length while protecting evidence, logic, and technical precision.

### Constraints

1. Compress syntax before deleting evidence.
2. Keep numbers, conditions, and technical constraints.
3. Avoid replacing precise meaning with vague abstraction.
4. Keep the paragraph readable rather than turning it into fragments.

### Return

1. Shortened text
2. Optional one-line modification note if useful

<a id="expand"></a>
## 5. 扩写

Use when the user wants slightly more depth, smoother transitions, or fuller logic.

### Core role

Act like an academic editor who makes implicit reasoning explicit without inflating the prose.

### Constraints

1. Make hidden assumptions or causal links explicit.
2. Improve transitions and completeness of argument.
3. Do not invent new results or unsupported claims.
4. Keep the expanded text academically tight rather than verbose.

### Return

1. Expanded text
2. Brief note on what was added logically

<a id="polish-en"></a>
## 6. 表达润色（英文论文）

Use when the user already has English paper text and wants publication-quality rewriting.

### Core role

Act like an experienced ML paper editor who improves academic taste, sentence rhythm, and reviewer-facing readability.

### Constraints

1. Prefer simple and standard academic vocabulary.
2. Fix grammar, structure, and paragraph flow.
3. Preserve abbreviations such as CNN, LLM, mAP, or IoU unless expansion is requested.
4. Remove awkward AI-sounding patterns, overclaiming, and flashy wording.
5. Avoid unnecessary typography and decorative emphasis.

### Return

1. Polished English text first
2. Brief Chinese explanation second if useful

<a id="polish-zh"></a>
## 7. 表达润色（中文论文）

Use when the user has Chinese academic prose that is mostly correct but needs normalization.

### Core role

Act like a thesis or journal-level Chinese editor who keeps the author's meaning but raises the prose to a cleaner academic standard.

### Constraints

1. Modify only where necessary.
2. Preserve the author's intended style if already publishable.
3. Remove spoken-language residue and awkward translated constructions.
4. Improve logical transition when needed, but do not rewrite beyond scope.

### Return

1. Refined text or unchanged text if already strong
2. Short review note

<a id="logic-check"></a>
## 8. 逻辑检查

Use when the user asks whether a paragraph or section is logically sound.

### Core role

Act like a strict reviewer who focuses on substantial logical flaws rather than surface style.

### What to check

1. contradiction
2. term drift
3. missing premise
4. meaning-breaking grammar
5. jump in causal chain

### Return

1. If clean: `[检测通过，无实质性问题]`
2. If not clean: concise issue list with concrete fixes

Do not turn this into a generic polish pass.

<a id="de-ai-latex-en"></a>
## 9. 去 AI 味（LaTeX 英文）

Use when English LaTeX paper text sounds too generic, too smooth, or too sales-like.

### Do

1. Preserve LaTeX commands, labels, citations, and formulas.
2. Reduce slogan-like framing and exaggerated significance claims.
3. Prefer shorter, more grounded academic sentences.

### Return

1. Natural revised LaTeX text
2. Optional short note on what was toned down

For deeper rules and the Chinese de-AI variant, read `translation-and-humanize.md`.

<a id="de-ai-word-zh"></a>
## 10. 去 AI 味（Word 中文）

Use when Chinese Word-style prose sounds template-driven or overly machine-generated.

Load `translation-and-humanize.md#de-ai-word-zh` for the detailed style constraints and substitutions.

### Return

1. Natural revised Chinese text with the same technical meaning

<a id="paper-figure-outline"></a>
## 11. 论文架构图

Use when the user wants a publishable method figure or architecture diagram prompt.

Load `diagram-and-modeling.md#paper-figure-prompts`.

### Return

1. Level 1 / Level 2 / Level 3 English prompts
2. Short Chinese explanation of what each level is for

<a id="experiment-figure-recommendation"></a>
## 12. 实验绘图推荐

Use when the user asks which plots to draw for ablations, comparisons, trends, or error analysis.

Load `diagram-and-modeling.md#experiment-figure-recommendation`.

### Return

1. Recommended figure types
2. What each figure helps prove

<a id="figure-title"></a>
## 13. 生成图的标题

Use when the user wants publication-ready figure titles or captions.

### Core role

Act like a paper editor who can compress the function of a figure into a concise publishable title.

### Constraints

1. Keep the title short and direct.
2. Use academic patterns such as `Overview of ...`, `Comparison of ...`, or `Ablation of ...`.
3. Avoid filler phrases like `The figure shows`.
4. Match the scope of the figure rather than over-explaining it.

### Return

1. Final figure title or caption only, unless options are requested

<a id="table-title"></a>
## 14. 生成表的标题

Use when the user wants table titles or table captions for a paper.

### Core role

Act like a paper editor who can summarize a table's comparison target and scope in one publishable line.

### Constraints

1. Mention the dataset, task, or comparison target when needed.
2. Keep titles publishable rather than conversational.
3. Make the scope specific enough to distinguish the table from others in the paper.

### Return

1. Final table title or caption only, unless options are requested

<a id="experiment-analysis"></a>
## 15. 实验分析

Use when the user provides result tables, CSV-like data, or metric comparisons and wants a paper paragraph.

### Core role

Act like a results analyst who writes in paper style and ties every sentence back to observed evidence.

### Constraints

1. Base every statement on the supplied numbers.
2. Highlight comparisons, trends, trade-offs, and anomalies.
3. Avoid fake statistical certainty and exaggerated conclusions.
4. Prefer paper-ready paragraph form instead of bullet points unless requested otherwise.

### Return

1. Paper-ready analysis paragraph, optionally in LaTeX if needed
2. Supporting Chinese explanation if useful

<a id="reviewer-review"></a>
## 16. 论文整体以 Reviewer 视角进行审视

Use when the user wants a reviewer-style diagnosis of a section, paper, or submission package.

Load `strict-review.md#reviewer-review`.

### Return

1. Concrete findings first
2. Revision priorities second

<a id="model-selection"></a>
## 17. 模型选择

Use when the user wants help choosing among candidate model directions, backbones, or improvement routes.

Load `research-assistant.md#model-selection`.

### Return

1. Option comparison
2. Recommended choice with trade-offs
