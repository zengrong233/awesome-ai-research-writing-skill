# Paper Reading

Use this file when the user wants to read, summarize, or analyze a paper systematically.

<a id="structured-reading"></a>
## 1. 结构化读论文框架

Use when the user uploads a paper or PDF and wants a guided reading report, especially for beginners.

### Core goals

1. Explain every important technical concept the first time it appears.
2. Help the reader understand not only what the paper does, but also why it matters.
3. Keep the response in Chinese unless the user explicitly asks for another language.

### Must-cover sections

1. 论文基本信息
   - 标题、作者、机构、年份、期刊或会议、摘要
2. 整体概括
   - 研究背景与动机
   - 核心贡献与主要发现
3. 方法
   - 核心思想
   - 关键模块
   - 输入、处理流程、目标实现路径
4. 数据集与评估指标
   - 数据来源、规模、特点、选择原因
   - 指标定义、计算方式、能衡量什么
5. 实验结果
   - 结果解读
   - 为什么会出现这些结果
   - 这些结果对读者有什么启发

### Output rules

1. Use Markdown headings and keep the report easy to scan.
2. Use `**加粗**` to mark key points.
3. When a figure is first mentioned, explain what it is trying to show in words.
4. Use LaTeX delimiters for formulas: `$...$` and `$$...$$`.
5. Prefer depth and completeness over aggressive shortening.

<a id="paper-analysis"></a>
## 2. 论文分析（方法、实验、创新点）

Use when the user wants a deeper academic dissection than a beginner-friendly reading note.

### Recommended structure

1. 研究背景
2. 相关工作
3. 预备知识
4. 方法详解
   - `What`
   - `Why`
   - 关键公式与变量解释
5. 创新点总结
6. 实验分析
   - 数据集
   - baseline
   - 主结果
   - 消融实验
7. 局限与展望

### Quality bar

1. Distinguish author claims from your own analysis.
2. Explain formulas with variable meanings instead of dropping raw notation only.
3. Read experiments critically rather than paraphrasing tables.
4. Point out missing baselines, weak ablations, or overclaimed conclusions when they exist.
