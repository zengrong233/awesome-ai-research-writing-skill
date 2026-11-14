# Upstream Skills and Provenance

Use for specialized-tool routing, installation advice, and the provenance of this package's research workflows. Check the current environment before naming a skill or tool as available. A referenced project is not an installed dependency.

## Tool selection

| Need | Selection rule |
| --- | --- |
| Full manuscript authoring | Use an installed academic-writing skill if it adds section-level planning, evidence alignment, or manuscript integration. Retain this package's bilingual editing contract. |
| Word/PDF editing | Use the environment's document/PDF skill for the actual file format, layout preservation, and rendering. Plain-text revision alone does not edit a DOCX or PDF. |
| Editable research PPT | Use an available presentation skill or established slide-authoring tool that can create the requested format. Inspect its documented export and rendering support. |
| Quantitative figures | Prefer the project's existing Python/R plotting stack or an available plotting skill. Keep transformations and statistical summaries reproducible. |
| Editable framework diagrams | Use an available vector/diagram tool or a reproducible drawing source. Verify actual text/object editability. |
| Raster illustration | Use an available image-generation/editing skill when requested or suitable. Check labels and scientific semantics; a raster image is not an editable vector diagram. |
| Natural prose editing | An installed humanizing/editorial skill can help after content and logic are stable; retain citations, evidence, and uncertainty. |

Use actual installed names and supported interfaces rather than assuming `docx`, `imagegen`, or any particular renderer exists. Do not add API credentials, global preferences, hosted services, or a separate runtime as an implicit requirement of this package.

## Reference projects

The following revisions were checked on **2026-11-14**. These are reference sources for workflow design, not bundled runtimes. The new workflows are written for this package; upstream scripts, templates, images, and archives are not redistributed here.

### Original writing collection

[Leey21/awesome-ai-research-writing](https://github.com/Leey21/awesome-ai-research-writing) supplied the original task taxonomy and prompt-workflow intent. Existing attribution and the historical upstream-rights limitation remain in the repository [LICENSE](https://github.com/zengrong233/awesome-ai-research-writing-skill/blob/main/LICENSE). Do not infer a license for the original collection from the licenses of the later references below.

### Nature Skills

- Inspected revision: [`7bff1d0`](https://github.com/Yuan1z0825/nature-skills/tree/7bff1d0539c0dfad6c30178bb93ce6dd8a5cebf8).
- Relevant entries: [nature-paper2ppt](https://github.com/Yuan1z0825/nature-skills/blob/7bff1d0539c0dfad6c30178bb93ce6dd8a5cebf8/skills/nature-paper2ppt/SKILL.md) and [nature-figure](https://github.com/Yuan1z0825/nature-skills/blob/7bff1d0539c0dfad6c30178bb93ce6dd8a5cebf8/skills/nature-figure/SKILL.md).
- License evidence: repository [Apache-2.0 LICENSE](https://github.com/Yuan1z0825/nature-skills/blob/7bff1d0539c0dfad6c30178bb93ce6dd8a5cebf8/LICENSE).
- Design lessons used: classify the research story, connect slides/panels to source evidence, preserve terminology, edit existing decks locally, distinguish data and schematic figures, and inspect the rendered artifact at its final size.
- Adaptation: [research presentations](research-presentations.md), [scientific data figures](scientific-data-figures.md), and [framework figures](framework-figures.md) use portable instructions. They do not assume Nature Skills manifests, scripts, image backends, or a universal journal specification.

### Paper Framework Figure Studio Pro

- Inspected revision: [`7755741`](https://github.com/c-narcissus/paper-framework-figure-studio-pro/tree/77557418b4ca8c24fa8961206bf9b8f7f6d030e1), README for the v3.2.15f release family.
- License evidence: its [README license section](https://github.com/c-narcissus/paper-framework-figure-studio-pro/blob/77557418b4ca8c24fa8961206bf9b8f7f6d030e1/README.md#许可) declares MIT-0. This records the README declaration, not a separate license-file audit of every archived asset.
- Design lessons used: recover paper facts before drawing, distinguish semantic graph from visual layout, track nodes/edges/variables, constrain visible labels, and make the real contribution visually legible.
- Adaptation: [framework figures](framework-figures.md) supports a direct editable-diagram route and a separate prompt route. It does not import the upstream fixed candidate counts, staged checkpoint archives, or ChatGPT Web image-generation flow. Raster candidates remain raster outputs.

### SciPilot Figure

- Inspected revision: [`43098dd`](https://github.com/Haojae/scipilot-figure-skill/tree/43098ddb9e6a6d142218540c114f9ed38922fc42).
- Relevant entry: [SKILL.md](https://github.com/Haojae/scipilot-figure-skill/blob/43098ddb9e6a6d142218540c114f9ed38922fc42/SKILL.md).
- License evidence: repository [MIT LICENSE](https://github.com/Haojae/scipilot-figure-skill/blob/43098ddb9e6a6d142218540c114f9ed38922fc42/LICENSE).
- Design lessons used: profile data before choosing a chart, treat numeric identifiers as identifiers, disclose missingness and sample sizes, use redundant visual encoding, and inspect fonts, clipping, legends, and exports.
- Adaptation: [scientific data figures](scientific-data-figures.md) keeps those scientific checks without assuming upstream profiling/export scripts are installed or imposing one chart policy on every discipline.

## Installation and reuse

When asked to install a specialized skill, identify its current installable `SKILL.md` path, supported host, dependencies, license, and fit for the task. Use the host's installer workflow when available and remain within the user's authorized scope. A showcase README or downloadable archive alone does not establish direct compatibility with the current host.

If copying upstream code, templates, text, or assets in a later change, review that material's license and carry the required notices then. Merely citing these projects does not relicense third-party material or install their capabilities.
