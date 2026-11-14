# Framework Figures

Use for method/framework/architecture diagrams, scientific mechanisms, and conceptual schematics. For measured quantities use [scientific data figures](scientific-data-figures.md). For prompt-only requests use [diagram prompts](diagram-and-modeling.md#paper-figure-prompts) after grounding the semantics here.

## 1. Define the figure's job

Identify the audience, source version, intended placement/size, language, and requested output: editable diagram, final image, alternative layout, or prompt. Reuse the manuscript terminology and existing style constraints. A complete figure should answer a concrete question, such as how inputs become outputs or where a new mechanism changes the baseline.

Read the relevant Method, equations, algorithms, and code when provided. Use paper section/page/equation anchors or code file/symbol locations for important mechanisms. An abstract alone rarely establishes internal connections. Ask for the missing mechanism when necessary; meanwhile draft only the supported high-level structure and mark uncertainty in working notes.

If paper and code disagree, identify the discrepancy and target version before asserting a definitive graph. Do not invent attention, fusion, feedback, loss terms, or a branch simply because the layout would look balanced.

## 2. Recover the semantic graph

Before styling, make a compact working description of the entities and relationships. This may be a short node/edge table or a source diagram; it need not become a separate report.

For each important node, establish its name, role, input/output, operation, and source anchor. For each edge, establish source, destination, carried variable or signal, direction, and meaning. Distinguish data/tensor flow, control, supervision, parameter sharing, aggregation, and conceptual association.

Check the graph against the source:

- input modalities and their preprocessing;
- module order, branches, merging points, and any repeated/shared blocks;
- variable names and tensor dimensions when actually specified;
- training-only inputs, losses, labels, teacher paths, or gradients;
- inference inputs and outputs, including removed training branches;
- boundary between established components and the proposed contribution.

A loss edge is not automatically a forward inference edge. A bidirectional arrow requires a bidirectional relationship. A dashed edge needs a defined meaning, not merely a visual preference. Avoid drawing mathematical gradients or feedback loops unless supported.

Where details are unknown, omit them or visibly label a draft placeholder; do not let an unresolved assumption become an unlabeled scientific claim in a final figure.

## 3. Translate semantics into a visual layout

Choose a primary reading direction and a small number of meaningful groups. Separate an overview from a detailed inset when one scale cannot show both. Give the real contribution visual emphasis through placement, boundary, or a restrained accent; leave routine components quieter.

The semantic graph and the visual layout have different roles. Routing a line around a box must not change its endpoint or imply an extra computation. Grouping nodes must not hide a required branch. Repeating a visual component must not imply independent parameters when weights are shared.

Set a concise, consistent visible-label vocabulary using the manuscript's module names and variables. Keep long explanations in the caption. Use meaningful labels on ambiguous arrows and legends for non-obvious encodings. Follow the user's language; English labels are a reasonable default for an English paper, not a universal requirement.

Prefer clean, readable geometry and typography suited to the target publication. Use color to encode roles consistently and pair it with shapes, line styles, or labels. White backgrounds, muted palettes, and vector line art may be useful defaults for a paper, but obey the actual template and figure content. Avoid decorative icons or pseudo-3D effects that obscure the mechanism.

## 4. Choose an editable production route

Use a supported drawing/vector tool or a reproducible source suitable for the project: for example, diagram source, SVG with text/shapes, or a drawing script. Follow the current tool's documented interfaces and preserve a source that a researcher can reopen and revise without this chat.

- For an editable deliverable, keep module labels, boxes, arrows, and legends editable where feasible. A PNG embedded in SVG/PPTX is still a raster image.
- For a raster illustration request, use available image-generation/editing tools and inspect every label and connection. Provide a separate editable diagram if required and possible; do not claim a generated raster has editable objects.
- If the user requests prompts only, return prompts rather than images. Include exact labels, node relationships, arrow meanings, output constraints, and semantic exclusions; visual style alone is insufficient.
- For existing-figure edits, preserve supported semantics and change the requested part. Inspect the original and avoid unrelated redesign.

Create a representative complete draft early enough to inspect composition and legibility. Refine it based on source fidelity and visual quality. Do not require a fixed number of layout candidates, image generations, or approval gates unless the user asks for an exploratory selection process.

<a id="multi-panel-figures"></a>
## 5. Multi-panel figures

Assign distinct roles to panels: problem/setup, full pipeline, key-module detail, training/inference difference, or evidence. Keep the same symbols, group colors, and module names across overview and inset. Use explicit correspondence marks when a block is expanded elsewhere.

Let each panel answer a different part of the figure's question. Avoid repeating the same full pipeline at multiple sizes without a useful distinction. Quantitative panels must use their actual data and the [data-figure workflow](scientific-data-figures.md), not plausible-looking decorative curves.

Align panel boundaries, labels, and reading order; retain enough space for arrowheads and legends at the final size. Check the assembled figure, not just the individual panels.

## 6. Validate meaning and appearance

Perform a semantic pass against the paper/code: node names, edge endpoints/directions, carried variables, formulas, shared parameters, and training versus inference. Check each highlighted novelty against the actual contribution. A visually polished diagram with the wrong edge is still wrong.

Then render the requested export and inspect at the intended insertion size:

- legible labels and equations, correct glyphs, and consistent typography;
- arrowheads that visibly terminate at the intended ports;
- crossings, overlaps, clipped text, ambiguous grouping, and disconnected edges;
- clear primary path and readable secondary detail;
- color/line-style meanings that remain understandable without color;
- caption and panel references that match the figure.

For journal-specific dimensions or export requirements, verify current official guidance for the relevant stage; do not assert generic “Nature/IEEE compliant” status from appearance alone. Fix the editable source, regenerate, and inspect the affected result. If a renderer is unavailable, report that visual validation remains incomplete.

## Delivery

Return the actual figure in the requested format, the editable/reproducible source when requested or feasible, a preview, and a caption identifying the mechanism and any panel/edge conventions. Preserve source attribution for adapted figures. Distinguish original illustration, adaptation, and reproduction as appropriate.

State concrete unresolved semantic details or output limitations. A high-level draft based on incomplete input must be labeled accordingly; a prompt set is not a completed diagram. Keep any necessary recreation instructions with the source through normal project documentation, without requiring session-specific paths or hidden agent state.
