# Diagram And Modeling

Use this file when the user wants prompts for paper figures, experiment-plot planning, or UML-style modeling output.

<a id="paper-figure-prompts"></a>
## 1. 科研绘图专家（三层级英文提示词）

Use when the user provides research code, a paper, or a method description and wants figure prompts for image-generation tools or design drafting.

### Output format

1. `Level 1: 整体架构图`
   - Purpose: Figure 1 or Figure 2
   - Goal: show the full pipeline and data flow
2. `Level 2: 核心模块图`
   - Purpose: zoom into the key contribution
   - Goal: show internal interactions and signals
3. `Level 3: 算法流程图`
   - Purpose: explain training or inference logic
   - Goal: show ordered steps and branches clearly

### Rules

1. Write the final prompts in English.
2. Use accurate CS/AI terms such as `feature map`, `concatenation`, `attention weights`, or `tensor`.
3. Prefer clean academic visual styles: white background, controlled color palette, explicit arrows.
4. Keep the Chinese explanation short and put the prompt blocks first.

<a id="experiment-figure-recommendation"></a>
## 2. 实验绘图推荐

Use when the user asks which figures should be drawn for results, ablations, trends, or comparisons.

### Recommend based on data shape

1. Single-metric method comparison -> bar chart
2. Multi-metric trade-off -> radar chart or grouped bars
3. Trend across epochs or settings -> line chart
4. Module contribution -> ablation table plus bar chart
5. Error distribution or category sensitivity -> heatmap
6. Precision-recall behavior -> PR curve

### Return

1. Figure type
2. What question it helps answer
3. Suggested title or caption direction

<a id="uml-modeling"></a>
## 3. 系统建模分析师（UML）

Use when the user provides a system description or code and wants use-case, class, sequence, state, or activity analysis.

### Workflow

1. Identify system boundary, actors, and core entities.
2. Decide which diagram type best matches the question.
3. Output using Markdown-friendly UML notation or Mermaid if the user wants renderable diagrams.

### Useful targets

1. 用例图
2. 类图
3. 顺序图
4. 状态图
5. 活动图
6. 综合建模说明

### Notation reminders

1. `+` public, `-` private, `#` protected, `~` package
2. `--|>` inheritance
3. `--o` aggregation
4. `--*` composition
5. `-->` dependency
