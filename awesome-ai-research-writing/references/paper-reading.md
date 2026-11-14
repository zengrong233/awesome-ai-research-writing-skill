# Paper Reading

Use for guided reading or critical paper analysis. Read the supplied paper, not just its title or an abstract returned by search. For PDFs, use available extraction and page images where tables, equations, or diagrams require visual inspection. Note unreadable pages or unavailable supplements and limit conclusions accordingly.

## Shared evidence rules

Record title, version, year, venue, and authors only when available from the source; mark missing metadata as “未提供” or “未核实”. For a preprint, do not infer acceptance from its subject or author reputation.

Attach section, page, equation, table, or figure anchors to important claims. Distinguish the authors' findings, your interpretation, and unanswered questions. Explain specialized terms at first use for beginner readers. Keep equations faithful and define variables using the paper; flag undefined variables instead of inventing definitions.

For external context or novelty comparisons, verify primary literature and cite it. A supplied-paper summary can proceed without a literature search; do not present unverified novelty as an established fact.

<a id="structured-reading"></a>
## 1. 结构化读论文框架

Use for a systematic, beginner-friendly reading report. Adjust depth to the user's background and requested length. Cover applicable sections without padding empty categories:

1. **论文基本信息与一句话概括** — identify the source and the problem/result in plain language.
2. **背景与动机** — what limitation motivates the work; why the stated problem matters.
3. **方法路径** — inputs, key steps/modules, outputs, training or inference distinction, and the role of the central formula.
4. **数据与评估** — source and scale, splits, unit of evaluation, metric definitions/directions, and relevant baselines.
5. **结果与证据** — the main comparison with table/figure anchors, ablations, uncertainty if reported, and the scope of support.
6. **局限与阅读提示** — missing evidence, assumptions, and the next section or figure worth reading.

Explain each key figure in words: what is encoded, what comparison is visible, and which conclusion it supports. Treat explanations for why a result occurs as hypotheses unless tested. If only an abstract is supplied, give an abstract-level note and identify which method or result details cannot be recovered.

Use Chinese by default, readable headings, and mathematical notation when helpful. Reserve emphasis for the few points that guide understanding.

<a id="paper-analysis"></a>
## 2. 论文分析（方法、实验、创新点）

Use for a deeper critique. Organize around the paper's argument rather than following every section mechanically:

- **研究背景 / 相关工作 / 预备知识:** define the problem and the actual comparison set; cite verified context where used.
- **方法详解:** explain what each mechanism does, why it is introduced, its input/output and assumptions, and the meaning of central equations.
- **创新点总结:** separate claimed contributions from differences demonstrated against prior work. An architectural rename alone does not establish novelty.
- **实验分析:** examine datasets, split leakage risks, baseline fairness, compute/training conditions, main results, ablations, and robustness or uncertainty where relevant.
- **局限与展望:** distinguish demonstrated failures, acknowledged limits, and your proposed follow-up experiments.

For each major criticism, identify the source location, why it affects the claim, and the evidence that would resolve it. Absence from the supplied excerpt is not proof of absence from the full paper. Prioritize issues that change interpretation; do not manufacture weaknesses to fill a quota.

For a talk based on the analysis, continue with [research presentations](research-presentations.md); for figure reconstruction, use [framework figures](framework-figures.md).
