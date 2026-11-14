# Diagram and Modeling

Use for figure prompts, chart recommendations, and UML. For actual artifacts, use [framework figures](framework-figures.md) or [scientific data figures](scientific-data-figures.md). User-specified language, format, and scope take precedence over defaults.

<a id="paper-figure-prompts"></a>
## 1. 科研绘图专家（三层级英文提示词）

Use when the user explicitly wants prompts for a paper figure. First recover the supported nodes, edges, variables, and training/inference distinctions using [framework figures](framework-figures.md). Do not use a visual prompt to fill missing method details.

Unless a single prompt or another structure is requested, provide:

1. `Level 1: 整体架构图` — overall method, inputs/outputs, module grouping, and main flow.
2. `Level 2: 核心模块图` — the actual new mechanism, local inputs/outputs, operations, and relation to the overview.
3. `Level 3: 算法流程图` — ordered training or inference procedure, with conditions and training-only branches distinguished.

Write prompt instructions in English by default. Figure-label language follows the paper/user requirement. Include a brief Chinese note explaining the use of each level. If the source does not support a level, state the missing details rather than inventing a more detailed prompt.

Each prompt should specify the scientific purpose, intended size/aspect ratio if known, layout and reading order, exact visible labels, nodes and directed edges, variable/legend meanings, and emphasis on the real contribution. Keep text concise and choose a coherent visual style appropriate to the manuscript. Describe output/editability needs accurately.

Include relevant exclusions: no unsupported module, changed arrow direction, fabricated numerical result, decorative quantitative plot, unreadable label, or unexplained icon. Pure white backgrounds, pastel colors, English labels, and three levels are defaults only when appropriate, not constraints that override the user. A generated raster candidate still needs semantic and text inspection.

<a id="experiment-figure-recommendation"></a>
## 2. 实验绘图推荐

Identify the research question and inspect the available data or supplied schema. Apply [scientific data figures](scientific-data-figures.md) for chart selection and statistical meaning. Return:

1. `推荐方案` — 1–2 useful chart choices and the question each answers.
2. `核心理由` — how the encoding fits the variable types, comparison, and available evidence.
3. `视觉设计规范` — axes/units/order, scale, legend, color plus redundant encoding, and statistical elements supported by the data.

State missing prerequisites. Means alone cannot support a violin plot or inferred confidence bands; a small sample should not be hidden behind a smooth density. Prefer simple comparable views over default radar charts, dual axes, or broken axes. Never recommend a plot merely because it makes a desired conclusion look stronger.

If the user asks to draw rather than recommend, continue through data inspection, source generation, export, and visual checks instead of ending with advice.

<a id="uml-modeling"></a>
## 3. 系统建模分析师（UML）

Use for use-case, class, sequence, state, or activity analysis from a system description or code. Establish system boundary, actors/entities, actual interactions, and the question the diagram must answer. Read relevant code paths when supplied; distinguish implemented behavior from proposed design.

Select the diagram type that fits the question. Use the notation/tool requested; otherwise provide supported Mermaid or another renderable source when useful. Do not describe a flowchart as a fully conformant UML use-case diagram when the renderer lacks that notation.

For class visibility, `+` is public, `-` private, `#` protected, and `~` package visibility. In Mermaid class diagrams, put the marker at the intended endpoint: `Child --|> Parent` is inheritance, `Whole o-- Part` aggregation, and `Whole *-- Part` composition. Verify syntax against the actual renderer instead of mixing dialects.

Check participants, message order, branches, multiplicity, ownership, transitions, and error paths against the source. Keep diagrams focused and separate distinct questions into appropriate views. Return the renderable/editable source and explain only non-obvious modeling choices; when a rendered diagram is requested and supported, render and inspect it.
