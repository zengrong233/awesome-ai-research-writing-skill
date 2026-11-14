# Prompt Index

Use this catalog to find a workflow or a reusable-prompt entry. Default behavior is to complete the task; ask explicitly for a prompt template when that is the desired output.

## Part I: 写作 Prompt 集合

| 场景 | 入口 |
| --- | --- |
| 中转英 / 英转中 / 中转中 | [中转英](prompt-routing.md#cn-to-en) · [英转中](prompt-routing.md#en-to-cn) · [中转中](prompt-routing.md#cn-to-cn) |
| 缩写 / 扩写 | [缩写](prompt-routing.md#shorten) · [扩写](prompt-routing.md#expand) |
| 表达润色 | [英文论文](prompt-routing.md#polish-en) · [中文论文](prompt-routing.md#polish-zh) |
| 逻辑检查 | [文本逻辑与证据](prompt-routing.md#logic-check) |
| 去 AI 味 | [LaTeX 英文](translation-and-humanize.md#de-ai-latex-en) · [Word 中文](translation-and-humanize.md#de-ai-word-zh) |
| 英语长难句翻译 | [语法拆解与翻译](translation-and-humanize.md#long-sentence-translation) |
| 结构化读论文 / 深入论文分析 | [入门阅读](paper-reading.md#structured-reading) · [方法、实验、创新点](paper-reading.md#paper-analysis) |
| 实验分析 | [从数据到分析段落](prompt-routing.md#experiment-analysis) |
| 科研问答 / 科研专家 / 模型选择 | [联网核验](research-assistant.md#verified-assistant) · [改模型代码与想点子](research-assistant.md#research-expert) · [模型选择](research-assistant.md#model-selection) |
| Reviewer 视角 / 严格送审评议 | [Reviewer 审查](strict-review.md#reviewer-review) · [送审评议](strict-review.md#strict-thesis-review) |
| 生成图标题 / 表标题 | [图标题与图注](prompt-routing.md#figure-title) · [表标题与表注](prompt-routing.md#table-title) |

## 科研 PPT 与论文绘图

| 场景 | 入口与交付 |
| --- | --- |
| 论文转科研 PPT；组会、文献汇报、答辩、会议报告 | [科研演示](research-presentations.md)：证据、故事线、时间、可编辑 PPTX、讲稿与渲染检查 |
| 修改已有 PPT | [保留模板并定点修改](research-presentations.md#edit-existing-decks) |
| 实验数据图；对比、消融、分布、收敛、权衡 | [数据绘图](scientific-data-figures.md)：数据核查、统计含义、可复现源码与矢量导出 |
| 论文框架图、方法架构图、机制示意图 | [框架绘图](framework-figures.md)：语义节点与边、视觉布局、可编辑源与成图 |
| 多面板论文图 | [数据面板](scientific-data-figures.md#multi-panel-figures) · [机制面板](framework-figures.md#multi-panel-figures) |
| 论文架构图 / 科研绘图专家（三层级英文提示词） | [Level 1/2/3 提示词](diagram-and-modeling.md#paper-figure-prompts) |
| 实验绘图推荐 | [选图与视觉编码建议](diagram-and-modeling.md#experiment-figure-recommendation) |
| 系统建模分析师（UML） | [UML 建模](diagram-and-modeling.md#uml-modeling) |

生成实际文件需要当前环境具备相应的编辑、绘图和导出工具。模块会按可用能力执行，并明确未完成的导出或视觉检查；只有大纲或提示词时不会称作已生成 PPT 或成图。

## Part II: 论文写作相关的 Skills

- [Skills 的配置与任务路由](../SKILL.md)
- [上游 Skills、参考来源与工具衔接](upstream-skills.md)

<a id="usage-examples"></a>
## 使用场景与示例 Prompt

- `用 $awesome-ai-research-writing 把下面的方法草稿翻译成英文 LaTeX，只返回正文，保留所有公式和引用。`
- `用 $awesome-ai-research-writing 把这段缩至 150 个英文单词以内，保留实验条件和数值。`
- `用 $awesome-ai-research-writing 分析这篇论文，标出关键结论对应的章节、表和图。`
- `用 $awesome-ai-research-writing 审查这份论文摘要，指出可见的问题和需要全文才能判断的事项。`
- `用 $awesome-ai-research-writing 将这篇论文做成 12 分钟中文组会 PPT，交付可编辑 PPTX，附来源和演讲备注。`
- `用 $awesome-ai-research-writing 只给这篇论文的 8 页会议报告大纲，标明每页核心结论、证据和用时。`
- `用 $awesome-ai-research-writing 修改现有答辩 PPT 的第 6–8 页，保留模板与其他页面。`
- `用 $awesome-ai-research-writing 根据 CSV 绘制两组实验对比图，保留原始点，说明误差线含义，交付源码、SVG 和 PNG。`
- `用 $awesome-ai-research-writing 根据 Method 与代码画可编辑框架图，区分训练和推理路径，保留模块名与变量。`
- `用 $awesome-ai-research-writing 生成 Level 1/2/3 英文绘图提示词，不生成图片。`
- `用 $awesome-ai-research-writing 比较这些候选 backbone，按目标硬件延迟、数据量和实现成本推荐一个，并给出验证实验。`
