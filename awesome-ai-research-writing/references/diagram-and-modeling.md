# Diagram And Modeling

Use this file when the user wants prompts for paper figures, experiment-plot planning, or UML-style modeling output.

This reference should preserve the intent of the original prompts while using Codex-native skill structure instead of XML-like prompt tags.

<a id="paper-figure-prompts"></a>
## 1. 科研绘图专家（三层级英文提示词）

Use when the user provides a paper abstract, method description, code, or module explanation and wants a prompt for a publishable paper figure.

### Core role

Act like a top-tier scientific illustrator for CVPR-, NeurIPS-, or ICLR-style papers.

### Core task

Recover the method's key mechanism, module structure, and data flow, then convert that understanding into a professional academic figure prompt.

### Visual constraints

1. Style
   - Use a professional, clean, modern, minimal paper-figure style.
   - Prefer flat vector illustration with clean lines and an academic aesthetic similar to DeepMind or OpenAI figures.
   - Use a pure white background.
2. Color
   - Use pastel or soft tones.
   - Avoid oversaturated or heavy dark colors.
   - Use color differences to distinguish module types clearly.
3. Content and layout
   - Turn the method into clear modules and arrow-based data flow.
   - Highlight the true novelty rather than drawing every detail equally.
   - Use simple vector icons only when they improve clarity.
4. Text rules
   - All labels inside the figure must be in English.
   - Add readable labels for key modules or equations when they matter.
   - Do not place long sentences or complex formulas inside the figure.
5. Negative constraints
   - No photorealistic imagery.
   - No sketchy lines.
   - No unreadable text.
   - No cheap 3D shading artifacts.

### Required output

1. `Level 1: 整体架构图`
   - an English prompt for the full method figure
2. `Level 2: 核心模块图`
   - an English prompt focused on the main novelty module
3. `Level 3: 算法流程图`
   - an English prompt for training or inference logic
4. A brief Chinese note explaining what each level is best used for

### Prompt-writing rules

1. Write the final prompts in English.
2. Use correct CS and AI terms such as `feature map`, `fusion`, `attention weights`, `decoder`, or `loss`.
3. Keep the logic visually consistent with the provided method description.
4. If the user only wants one prompt, output the best single English prompt first.

<a id="experiment-figure-recommendation"></a>
## 2. 实验绘图推荐

Use when the user asks which figures should be drawn for results, ablations, trends, distributions, or trade-offs.

### Core role

Act like a high-end academic data-visualization expert who selects the chart that best proves the user's experimental claim.

### Preferred academic chart library

1. Method comparison
   - grouped bar chart
   - horizontal bar chart when labels are long or methods are many
   - Pareto frontier for accuracy-efficiency trade-offs
   - radar chart for balanced multi-metric comparison
   - stacked bar chart for decomposed cost or time
2. Trend and convergence
   - line chart with confidence band
   - line chart with zoomed inset
   - scatter plot with fitted curve
3. Evaluation and classification
   - ROC curve
   - Precision-Recall curve for class imbalance
4. Matrix and relationship visualization
   - heatmap
   - scatter plot with diagonal reference line
   - bubble chart for adding parameter or cost scale
5. Distribution and composition
   - violin plot
   - box plot
   - donut chart when proportion display is truly necessary
6. Composite layouts
   - dual-axis chart
   - bar-line combination chart
   - faceted small-multiple grid

### Constraints

1. Prefer the chart types listed above before proposing anything custom.
2. If the data comes from multiple runs, recommend error bars or confidence intervals.
3. If value ranges are extremely uneven, suggest one of:
   - axis break for preserving raw scale perception
   - log scale for order-of-magnitude variation
   - normalization for emphasizing relative gain
4. Choose horizontal or vertical layout based on label length and density.
5. Keep the recommendation academic rather than commercial-dashboard styled.

### Required output

1. `推荐方案`
   - 1 to 2 best chart types
2. `核心理由`
   - why these charts best support the scientific story
3. `视觉设计规范`
   - x-axis and y-axis meaning and units
   - scale handling if needed
   - statistical elements such as error bars, fitted curves, or significance marks
   - color and line-style suggestions

<a id="uml-modeling"></a>
## 3. 系统建模分析师（UML）

Use when the user provides a system description or code and wants use-case, class, sequence, state, or activity analysis.

### Core role

Act like a modeling analyst who can turn system descriptions into clean UML-style abstractions.

### Internal checklist

1. What the system boundary is.
2. Who the actors are.
3. What the core entities and interactions are.
4. Which diagram type best answers the user's question.

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
