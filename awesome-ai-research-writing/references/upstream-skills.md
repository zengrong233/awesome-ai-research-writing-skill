# Upstream Skills

Use this file when the user asks what other skills to install, when a task is better served by a specialized skill, or when the user wants a tool recommendation rather than direct rewriting.

## Recommended Roles

### `research-paper-writing`

Use for full paper drafting, section-by-section rewriting, claim-evidence alignment, and reviewer-facing structure improvement.

Best fit:

1. Abstract, Introduction, Method, Experiments, Conclusion
2. end-to-end paper drafting from a repo or notes
3. adversarial self-review before submission

### `humanizer`

Use for de-AI rewriting after the text is already logically correct.

Best fit:

1. removing generic LLM tone
2. reducing exaggerated rhetoric
3. making final prose feel more natural

### `docx`

Use when the user is working inside Word templates or needs `.docx` editing rather than plain-text rewriting.

Best fit:

1. filling journal or conference Word templates
2. modifying existing `.docx` files
3. tracked-changes style edits

### `doc-coauthoring`

Use when the user wants a staged collaboration workflow instead of a one-shot rewrite.

Best fit:

1. writing a section interactively
2. brainstorming structure before drafting
3. multi-round coauthoring on a paper

### `canvas-design`

Use when the user needs a paper figure, system diagram, method overview, or other visual artifact.

Best fit:

1. pipeline overview figures
2. method comparison illustrations
3. concept diagrams for papers or slides

## Recommendation Rules

1. Recommend `research-paper-writing` for direct paper authoring and deep revision.
2. Recommend `humanizer` only after content and logic are already stable.
3. Recommend `docx` when formatting constraints live inside `.docx`.
4. Recommend `canvas-design` when the bottleneck is visual explanation rather than prose.
5. If the user already has one of these installed, prefer using it instead of re-explaining its workflow here.

## Installation Advice

When the user wants installation help:

1. Name the skill and why it matches the task.
2. If the user provides a GitHub repo or path, use the local skill installer workflow.
3. If the repo is only a README-style showcase and lacks `SKILL.md`, explain that it is not directly installable and identify the actual installable upstream skill package.
