# Translation And Humanize

Use this file when the user wants detailed sentence translation or specific de-AI rewriting behavior.

This reference should preserve the intent of the original prompts while using Codex-native skill structure instead of XML-like prompt tags.

<a id="long-sentence-translation"></a>
## 1. 英语长难句翻译

Use when the user gives one sentence or one dense paragraph and wants grammar-aware translation rather than a quick paraphrase.

### Core role

Act like a bilingual translator who explains grammar, clause structure, collocations, and the final meaning in readable Chinese.

### Internal checklist

1. What type of text this is.
2. What the main clause is.
3. Which subordinate clauses and modifiers matter most.
4. Which keywords need context-sensitive explanation.

### Required output

1. `句子拆分`
   - 主句
   - 从句或修饰成分
2. `关键词汇与搭配`
3. `语法要点`
4. `整句翻译`

### Constraints

1. Keep the translation faithful to the original meaning.
2. Explain idioms or fixed collocations when needed.
3. Avoid translationese in the final Chinese sentence.

<a id="de-ai-latex-en"></a>
## 2. 去 AI 味（LaTeX 英文）

Use when English LaTeX paper text sounds generic or over-produced.

### Core goal

Keep the meaning and LaTeX structure, but remove generic, over-smoothed, or sales-like AI writing signals.

### Rules

1. Preserve LaTeX commands, math, labels, and citations.
2. Remove repetitive parallelism and inflated significance claims.
3. Prefer precise verbs and grounded sentence rhythm over marketing tone.
4. Keep the length close to the original unless the user explicitly asks for expansion or compression.

### Return

1. Revised LaTeX text
2. Optional short note about the removed AI-like signals

<a id="de-ai-word-zh"></a>
## 3. 去 AI 味（Word 中文）

Use when Chinese technical or academic prose sounds too templated and the user wants a more natural but still professional version.

### Core goal

Rewrite the text into a slightly more explanatory and human-sounding style without changing the technical meaning.

### Style rules

1. Make the text slightly more explanatory, but do not exceed the original length.
2. Do not use first person.
3. Avoid forms like `至于 xxx 呢`.
4. Preserve all technical terms, file names, class names, API paths, and formulas exactly.
5. Keep the original logic and factual meaning unchanged.

### Preferred operations

1. Expand short verbs into natural process phrases when needed.
2. Use controlled substitutions such as:
   - `使用` -> `运用` / `选用`
   - `通过` -> `借助` / `依靠`
   - `特点` -> `特性`
3. Integrate explanatory bracket content into the sentence when it improves flow.

### Return

1. The revised Chinese text only, unless the user asks for an explanation
