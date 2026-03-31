# Prompt Routing

Use this file to map common writing requests to the right academic-writing behavior.
If the user asks for the old repository-style prompt directory, send them to `prompt-index.md`.

<a id="cn-to-en"></a>
## 1. 中转英

Use when the user provides Chinese notes, paragraphs, or method descriptions and wants English paper text.

### Do

1. Translate and rewrite into natural academic English.
2. Preserve formulas, technical terms, and dataset or model names.
3. Escape newly added LaTeX special characters if the target is LaTeX.
4. Keep the main output purely English unless the user asks for bilingual output.

### Return

1. `Part 1 [LaTeX / English]`: polished English content only.
2. `Part 2 [解释]`: concise Chinese note or back-translation if helpful.

<a id="en-to-cn"></a>
## 2. 英转中

Use when the user wants to understand English paper text rather than publish the Chinese output.

### Do

1. Translate into readable Chinese instead of stiff word-for-word Chinese.
2. Keep formulas and core terminology aligned with the original.
3. Explain dense phrases when direct translation would hide the meaning.

### Return

1. Pure Chinese reading text, unless the user asks for side-by-side bilingual output.

<a id="cn-to-cn"></a>
## 3. 中转中

Use when the user has a rough Chinese draft and wants it rewritten into formal academic Chinese.

### Do

1. Rebuild the logic before polishing the phrasing.
2. Merge fragments into coherent academic paragraphs.
3. Remove colloquial residue while preserving the author's meaning.

### Return

1. `Part 1 [Refined Text]`: formal Chinese paragraph.
2. `Part 2 [Logic Flow]`: short note on the restructuring.

<a id="shorten"></a>
## 4. 缩写

Use when the user wants the text shorter without losing technical content.

### Do

1. Compress syntax before deleting evidence.
2. Keep numbers, constraints, and key comparisons.

### Return

1. Shortened text.
2. Optional one-line modification note.

<a id="expand"></a>
## 5. 扩写

Use when the user wants slightly more depth, smoother transitions, or fuller logic.

### Do

1. Make implicit assumptions or causal links explicit.
2. Do not invent new results or unsupported claims.

### Return

1. Expanded text.
2. Brief note on what was added logically.

<a id="polish-en"></a>
## 6. 表达润色（英文论文）

Use when the user already has English paper text and wants publication-quality rewriting.

### Do

1. Prefer standard academic vocabulary over flashy wording.
2. Fix grammar, structure, and paragraph flow.
3. Preserve abbreviations such as CNN, LLM, mAP, or IoU unless expansion is requested.

### Return

1. Polished English text first.
2. Brief Chinese explanation second if useful.

<a id="polish-zh"></a>
## 7. 表达润色（中文论文）

Use when the user has Chinese academic prose that is mostly correct but needs normalization.

### Do

1. Modify only where necessary.
2. Preserve the author's intended style if already publishable.
3. Remove spoken-language residue and awkward translated constructions.

### Return

1. Refined text or unchanged text if already strong.
2. Short review note.

<a id="logic-check"></a>
## 8. 逻辑检查

Use when the user asks whether a paragraph or section is logically sound.

### Do

1. Flag only substantive issues.
2. Ignore optional style tweaks.
3. Focus on contradiction, term drift, missing premises, or meaning-breaking grammar.

### Return

1. If clean: `[检测通过，无实质性问题]`
2. If not clean: concise issue list with concrete fixes.

<a id="de-ai-latex-en"></a>
## 9. 去 AI 味（LaTeX 英文）

Use when English LaTeX paper text sounds too generic, too smooth, or too sales-like.

### Do

1. Preserve LaTeX commands, labels, citations, and formulas.
2. Reduce slogan-like framing and exaggerated significance claims.
3. Prefer shorter, more grounded academic sentences.

### Return

1. Natural revised LaTeX text.
2. Optional short note on what was toned down.

For deeper rules and the Chinese de-AI variant, read `translation-and-humanize.md`.

<a id="de-ai-word-zh"></a>
## 10. 去 AI 味（Word 中文）

Use when Chinese Word-style prose sounds template-driven or overly machine-generated.

Load `translation-and-humanize.md#de-ai-word-zh` for the detailed style constraints and substitutions.

### Return

1. Natural revised Chinese text with the same technical meaning.

<a id="paper-figure-outline"></a>
## 11. 论文架构图

Use when the user wants a publishable method figure or architecture diagram prompt.

Load `diagram-and-modeling.md#paper-figure-prompts`.

### Return

1. Level 1 / Level 2 / Level 3 English prompts.
2. Short Chinese explanation of what each level is for.

<a id="experiment-figure-recommendation"></a>
## 12. 实验绘图推荐

Use when the user asks which plots to draw for ablations, comparisons, trends, or error analysis.

Load `diagram-and-modeling.md#experiment-figure-recommendation`.

### Return

1. Recommended figure types.
2. What each figure helps prove.

<a id="figure-title"></a>
## 13. 生成图的标题

Use when the user wants publication-ready figure titles or captions.

### Do

1. Keep the title short and direct.
2. Use academic patterns such as `Overview of ...`, `Comparison of ...`, or `Ablation of ...`.
3. Avoid filler phrases like `The figure shows`.

### Return

1. Final figure title or caption only, unless options are requested.

<a id="table-title"></a>
## 14. 生成表的标题

Use when the user wants table titles or table captions for a paper.

### Do

1. Mention the dataset, task, or comparison target when needed.
2. Keep titles publishable rather than conversational.

### Return

1. Final table title or caption only, unless options are requested.

<a id="experiment-analysis"></a>
## 15. 实验分析

Use when the user provides result tables, CSV-like data, or metric comparisons and wants a paper paragraph.

### Do

1. Base every statement on the supplied numbers.
2. Highlight comparisons, trends, trade-offs, and anomalies.
3. Avoid fake statistical certainty.

### Return

1. Paper-ready analysis paragraph, optionally in LaTeX if needed.
2. Supporting Chinese explanation if useful.

<a id="reviewer-review"></a>
## 16. 论文整体以 Reviewer 视角进行审视

Use when the user wants a reviewer-style diagnosis of a section, paper, or submission package.

Load `strict-review.md#reviewer-review`.

### Return

1. Concrete findings first.
2. Revision priorities second.

<a id="model-selection"></a>
## 17. 模型选择

Use when the user wants help choosing among candidate model directions, backbones, or improvement routes.

Load `research-assistant.md#model-selection`.

### Return

1. Option comparison.
2. Recommended choice with trade-offs.
