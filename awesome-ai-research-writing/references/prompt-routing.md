# Prompt Routing

Use this file to map a user request to the right academic-writing behavior.

## 1. Chinese Draft -> English LaTeX

Use when the user provides Chinese notes, paragraphs, or method descriptions and wants English paper text.

### Do

1. Translate and rewrite into natural academic English.
2. Preserve formulas and technical names.
3. Escape newly added LaTeX special characters.
4. Keep the main output purely English.

### Return

1. `Part 1 [LaTeX]`: polished English content only.
2. `Part 2 [Translation]`: concise Chinese back-translation for meaning check.

## 2. English LaTeX -> Chinese Reading Version

Use when the user wants to understand an English paper snippet rather than publish the Chinese output.

### Do

1. Remove citation clutter if it harms readability.
2. Explain formulas in readable Chinese when needed.
3. Keep sentence alignment close to the original.

### Return

1. Pure Chinese reading text, unless the user asks for a structured dual-language output.

## 3. Chinese Draft -> Chinese Academic Prose

Use when the user has a rough Chinese draft for a thesis, report, or paper and wants it rewritten into formal academic Chinese.

### Do

1. Rebuild logic before sentence-level polishing.
2. Merge fragments into one coherent paragraph per idea.
3. Remove colloquial phrasing.

### Return

1. `Part 1 [Refined Text]`: formal Chinese paragraph.
2. `Part 2 [Logic Flow]`: short note on restructuring logic.

## 4. Shorten a Paragraph

Use when the user wants a small reduction in length without dropping core content.

### Do

1. Compress syntax rather than delete evidence.
2. Keep numbers, conditions, and technical constraints.

### Return

1. Shortened text.
2. Short modification log if helpful.

## 5. Expand a Paragraph

Use when the user wants slightly more depth, smoother transitions, or fuller logic.

### Do

1. Make implicit assumptions or causal links explicit.
2. Do not invent new results or claims.

### Return

1. Expanded text.
2. Brief note on what was added logically.

## 6. English Academic Polishing

Use when the user already has English paper text and wants publication-quality rewriting.

### Do

1. Prefer simple, standard academic vocabulary.
2. Fix grammar, structure, and flow.
3. Preserve domain abbreviations such as LLM or CNN unless the user requests expansion.
4. Avoid unnecessary typographic emphasis.

### Return

1. Polished English text first.
2. Chinese explanation or back-translation second if useful.

## 7. Chinese Academic Polishing

Use when the user has Chinese academic prose that is mostly correct but needs normalization.

### Do

1. Modify only where necessary.
2. Preserve the author's intended style if already publishable.
3. Remove spoken-language residue and awkward Europeanized constructions.

### Return

1. Refined text or unchanged text if already strong.
2. Short review comment.

## 8. Logic Check

Use when the user asks whether a paragraph or section is logically sound.

### Do

1. Flag only substantive issues.
2. Ignore optional style tweaks.
3. Focus on contradiction, term drift, or meaning-breaking grammar.

### Return

1. If clean: `[检测通过，无实质性问题]`
2. If not clean: concise issue list with concrete fixes.

## 9. Humanize / De-AI

Use when the user says a paragraph sounds AI-generated, too smooth, too sales-like, or too generic.

### Do

1. Reduce slogan-like framing, repetitive parallelism, and inflated significance claims.
2. Introduce more grounded sentence rhythm and clearer commitment.
3. Preserve meaning rather than merely swapping adjectives.

### Return

1. Natural revised text.
2. Optional note on what AI-like signals were removed.

## 10. Figure Title / Table Title / Caption

Use when the user wants publication-ready labels for figures or tables.

### Do

1. Keep titles short and direct.
2. Use common academic patterns such as `Comparison With ...`, `Ablation Study on ...`, or `Results on ...`.
3. Avoid filler phrases like `The figure shows`.

### Return

1. Final title or caption text only, unless the user asks for multiple options.

## 11. Experiment Analysis

Use when the user provides result tables, CSV-like data, or metric comparisons and wants a paper paragraph.

### Do

1. Base every statement on the supplied numbers.
2. Highlight comparisons, trends, trade-offs, and anomalies.
3. Avoid fake statistical certainty.

### Return

1. Paper-ready analysis paragraph, optionally in LaTeX if the user is writing a paper.
2. Supporting explanation in Chinese if needed.

## 12. Reviewer-Style Full-Paper Review

Use when the user wants a strict paper review, submission risk scan, or rebuttal-oriented diagnosis.

### Do

1. Summarize the claimed contribution in one sentence.
2. Separate strengths from critical weaknesses.
3. Distinguish fixable writing issues from structural method or experiment gaps.

### Return

1. `Part 1 [The Review Report]`
2. `Part 2 [Strategic Advice]`

## 13. When the User Wants Prompts Instead of Work

If the user explicitly asks for a reusable prompt:

1. Return a prompt template rather than executing the task.
2. Keep placeholders explicit, such as `[paste paragraph here]`.
3. State the target language and expected output format in the prompt itself.
