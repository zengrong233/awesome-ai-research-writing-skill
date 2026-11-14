# Translation and Natural Editing

Use for dense-sentence explanation and natural academic rewriting. “去 AI 味” means removing generic rhetoric, repetition, and awkward phrasing. Style editing cannot establish authorship or guarantee an AI-detector outcome; do not make such claims.

Follow the [shared editing contract](prompt-routing.md#shared-editing-contract): user format first, revised artifact first, optional explanations. Preserve evidence, technical content, and the author's level of certainty.

<a id="long-sentence-translation"></a>
## 1. 英语长难句翻译

Identify the main clause, subordinate clauses, modifier attachment, comparison/negation scope, and terms whose meaning depends on context. Explain only the grammar needed to understand this sentence. Preserve ambiguity when the context does not resolve it.

By default return `句子拆分`, `关键词汇与搭配`, `语法要点`, and `整句翻译`. If the user asks for translation only, omit the explanation. Make the final Chinese sentence fluent without changing the source claim. Use the manuscript/reading distinction in [英转中](prompt-routing.md#en-to-cn) for math and citations.

<a id="de-ai-latex-en"></a>
## 2. 去 AI 味（LaTeX 英文）

Replace empty promotional language and mechanical transitions with precise statements already supported by the source. Reduce redundancy and repair convoluted syntax. Keep a meaningful technical word even if it also occurs often in generated text; avoid word blacklists and arbitrary synonym swaps.

Preserve formulas, variables, numbers, citations, labels, commands, and useful environments. Do not strip itemized assumptions or procedural steps merely to create prose. Use context-appropriate tense and retain uncertainty and limitations.

Return revised English LaTeX, unchanged if already effective. Back-translation and a modification log are optional; when requested, explain concrete changes such as a removed unsupported superlative, not a claim that the text now passes detection.

<a id="de-ai-word-zh"></a>
## 3. 去 AI 味（Word 中文）

Use natural, precise academic Chinese. Replace empty slogans, repeated conclusions, awkward passive constructions, and nested modifiers where they obscure meaning. Retain numbered steps when sequence matters and keep accurate discipline-specific terms.

For Word-ready prose, output plain text without Markdown decoration. Preserve formulas, variables, citations, and necessary English terms even if they look visually complex. Do not remove evidence to improve flow.

Return the full revised text, or the original if no useful edit is needed. If a log is requested, state the specific language improvements or “原文表达清楚，建议保留。” Do not characterize the passage as proven human-authored or free of AI traces.
