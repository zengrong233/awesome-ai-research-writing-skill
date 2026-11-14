# Scientific Data Figures

Use to recommend or produce quantitative research figures from data, tables, or experiment logs. For mechanisms and architecture, use [framework figures](framework-figures.md). In a mixed figure, apply these rules to every quantitative panel.

## 1. Identify the question and output

Start with the scientific comparison: what should a reader learn, from which observations, under what conditions? Reuse the requested figure type, journal/template, language, physical size, panel count, and formats. If a requested chart misrepresents the data, explain the specific issue and recommend a sound alternative.

Distinguish recommendation-only from actual plotting. An actual figure request requires a rendered artifact and reproducible/editable source when tools permit. Missing data permits a chart plan, not fabricated observations. Illustrative mock data must be explicitly requested or agreed, clearly labeled synthetic, and kept separate from reported results.

For venue-specific specifications, consult the current official author guidance and identify the applicable article type and submission stage. Do not treat one journal's column widths, font, color space, or resolution requirements as universal. If exact guidance is unavailable, use a stated working size and disclose that venue compliance is unverified.

## 2. Profile the supplied data

Inspect the actual file, schema, and relevant rows before choosing a chart. Use the existing project tools; preserve raw inputs. Record the details needed to interpret or reproduce the figure, in the code/caption or existing project documentation:

- source file/version and relevant columns or table cells;
- variable meaning, data type, units, metric direction, and grouping/order;
- numeric IDs that are identifiers rather than continuous or ordinal measurements;
- sample size per group, independent experimental unit, pairing/repeated measures, and replicate type;
- missing values, duplicate rows, outliers, and any exclusions;
- whether values are raw observations, per-run summaries, or aggregates.

Check that parsing has not changed decimal separators, units, category names, or missingness. Do not silently drop rows, impute values, normalize, smooth, or remove outliers. Make necessary transformations explicit and reproducible. Do not count technical replicates or repeated measurements as independent biological/experimental units without justification.

If a unit or grouping variable is ambiguous, resolve it before a misleading plot is produced. Work on unambiguous parts while a consequential question is pending.

## 3. Match the encoding to the evidence

Choose the simplest chart that answers the question and preserves the data structure:

| Question | Useful starting point | Important condition |
| --- | --- | --- |
| Compare methods or groups | Dot/interval plot; bars for appropriate magnitude/aggregate comparisons | Keep metric direction and common conditions visible; show raw points when available and informative |
| Compare paired measurements | Paired dots or slope plot | Connect the same experimental unit only |
| Change over ordered time/steps | Lines, with points or uncertainty where useful | Do not connect unordered categories as a continuous process |
| Show a distribution | Points, box plot, histogram, ECDF; density/violin when data support it | Small samples need visible observations; do not imply a stable density from sparse data |
| Show an association | Scatter plot | A fit needs a justified model; association alone does not establish causation |
| Show a trade-off | Accuracy/cost scatter or Pareto view | Match hardware/measurement conditions; define maximize/minimize directions |
| Show a matrix | Heatmap | Label both dimensions and disclose the scale/normalization |
| Classifier performance | PR/ROC or calibration plot as appropriate | Require scores/threshold data; one accuracy value cannot reconstruct a curve |
| Show composition | Stacked bars or a simple proportion chart | Identify the denominator, total, and whether categories are exhaustive |

Radar charts, dual axes, broken axes, and 3D effects are not defaults. Use them only when they communicate a justified relationship without misleading comparisons. Prefer small multiples when scales differ. A log scale needs valid values and clear labeling; normalization needs its formula and baseline disclosed. Bars encoding magnitude generally need a zero baseline; other plots may use a focused range with clearly labeled limits.

For recommendation-only requests, return 1–2 suitable options, the question each answers, required data, and the main encoding/statistical caveat. Do not recommend uncertainty bands or significance marks merely as visual decoration.

## 4. Preserve statistical meaning

Define each interval: SD, SE, confidence/credible interval, quantile range, or another stated quantity. Record its computation and the relevant `n`. An unexplained `±` in a source table must be clarified or labeled as unspecified; do not rename it a confidence interval.

- With small samples, show available observations and group `n`; choose summaries that do not hide the evidence. Avoid false precision.
- With summary-only data, plot supplied estimates and documented intervals. Do not synthesize raw points, box plots, violin densities, replicate counts, or bootstrap intervals from means alone.
- A confidence interval requires a defensible method and assumptions. A seed does not make an inappropriate bootstrap valid; respect pairing, grouping, and the independent unit.
- Add statistical significance only from a supplied or properly performed test, with test, comparison, correction where relevant, and exact/appropriately rounded values documented. Do not infer significance from a visible gap or non-overlap alone.
- Separate an exploratory trend, a model fit, and a tested hypothesis. Do not use causal wording for an observational association without supporting design.

If analysis is part of the request, use an appropriate existing statistical workflow and report its assumptions. If inferential analysis is outside the requested scope or inputs are insufficient, render the supported descriptive figure and identify the missing inferential information.

## 5. Compose at the intended size

Choose a clear visual hierarchy: data first, explanatory labels second, decorative structure last. Use consistent typography, units, decimal precision, category order, and group colors. Redundant markers/line styles/labels should preserve distinctions in grayscale and for readers with color-vision differences.

Use installed fonts with the required glyph coverage, including CJK if present. Verify actual glyph rendering; naming a font does not establish availability. Keep labels legible after insertion into the paper or slides. Place legends near the data without occlusion, simplify gridlines, and keep meaningful reference lines distinct from data.

<a id="multi-panel-figures"></a>
## 6. Multi-panel figures

Assign each panel an evidence role, such as main comparison, ablation, robustness, or failure case. Give the figure one coherent question and remove panels that repeat the same claim without adding evidence.

Align plotting regions for comparable panels and use consistent axes/encodings where comparison requires it. Share legends when appropriate. Do not force the same range on unrelated variables; label deliberate differences. Add panel letters in a stable reading order and explain them in the caption. Keep a schematic panel's illustrative quantities visibly distinct from measured results.

Inspect the complete layout at final physical size, including gutters, panel-label alignment, legend balance, and the smallest text. Individual panel exports are not sufficient proof that the assembled figure is readable.

## 7. Produce and verify

Use the existing Python/R/project plotting stack or an available plotting skill. Keep plotting code, transformations, input locations, and relevant dependencies discoverable through normal project conventions. Do not add a new runner or hidden state for a single plot.

When requested and supported, deliver vector PDF/SVG for line art and plots, plus a PNG preview at the required size/resolution. Raster source data such as microscopy images may remain raster inside a vector container; describe the actual output accurately. Keep text editable when required and supported; outlined glyphs preserve appearance but lose text editing/searchability.

Check computed values against source rows or table cells. Verify saved files open and contain the expected panels. Inspect rendered exports at final size for clipping, overlaps, missing glyphs, font fallback, axis/legend errors, color confusion, and invisible points. Check the actual PDF/SVG/PNG exports used for delivery, since they may differ from a notebook view. Fix the source and re-export when a defect is found.

Deliver the figure, reproducible source, and a caption explaining variables, units, group `n`, summaries/intervals, transformations, exclusions, and source attribution as applicable. State only checks actually performed. If rendering or a requested export is unavailable, deliver supported files and identify that specific gap.
