# Upstream Skills

Use this file when the user asks what other skills to install, when a task is better served by a specialized skill, or when the user wants a tool recommendation rather than direct rewriting.

## Recommended Roles

### `research-paper-writing`

Use for full paper drafting, section-by-section rewriting, claim-evidence alignment, and reviewer-facing structure improvement.

Best fit:

1. Abstract, Introduction, Method, Experiments, Conclusion
2. End-to-end paper drafting from a repo or notes
3. Adversarial self-review before submission

### `humanizer`

Use for de-AI rewriting after the content and logic are already stable.

Best fit:

1. Removing generic LLM tone
2. Reducing exaggerated rhetoric
3. Making final prose feel more natural

### `docx`

Use when the user is working inside Word templates or needs `.docx` editing rather than plain-text rewriting.

Best fit:

1. Filling journal or conference Word templates
2. Modifying existing `.docx` files
3. Tracked-changes style edits

### `doc-coauthoring`

Use when the user wants a staged collaboration workflow instead of a one-shot rewrite.

Best fit:

1. Writing a section interactively
2. Brainstorming structure before drafting
3. Multi-round coauthoring on a paper

### `imagegen`

Use when the user does not only want figure prompts, but also wants an actual raster image generated or edited.

Best fit:

1. Turning a diagram prompt into a draft figure
2. Producing background-clean academic illustrations
3. Creating figure variants after the visual plan is stable

## Recommendation Rules

1. Recommend `research-paper-writing` for direct paper authoring and deep revision.
2. Recommend `humanizer` only after content and logic are already stable.
3. Recommend `docx` when formatting constraints live inside `.docx`.
4. Recommend `imagegen` when the bottleneck is actual image creation rather than prompt planning.
5. If the user already has one of these installed, prefer using it instead of re-explaining its workflow here.

## Installation Advice

When the user wants installation help:

1. Name the skill and why it matches the task.
2. If the user provides a GitHub repo or path, use the local skill installer workflow.
3. If the repo is only a README-style showcase and lacks `SKILL.md`, explain that it is not directly installable and identify the actual installable upstream skill package.
