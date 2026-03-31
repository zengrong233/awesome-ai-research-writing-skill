# Awesome AI Research Writing Skill for Codex

[![Codex Skill](https://img.shields.io/badge/Codex-Skill-0A66C2)](https://github.com/zengrong233/awesome-ai-research-writing-skill)
[![Validation](https://img.shields.io/badge/quick__validate-passing-2EA043)](https://github.com/zengrong233/awesome-ai-research-writing-skill)
[![GitHub stars](https://img.shields.io/github/stars/zengrong233/awesome-ai-research-writing-skill?style=social)](https://github.com/zengrong233/awesome-ai-research-writing-skill)

[English README](./README.en.md)

把一个“提示词合集 / skills 导航型项目”改造成 Codex 可直接安装、可直接触发、可继续扩展的学术研究 skill 包。

这个仓库基于 [Leey21/awesome-ai-research-writing](https://github.com/Leey21/awesome-ai-research-writing) 的任务分类思路继续整理，并把你新增的科研 prompt 一并沉淀到了 `references/` 中，方便 Codex 按需加载。

## 这个仓库解决什么问题

原项目非常适合：

- 查阅论文写作 prompt
- 了解常见写作场景
- 发现其他好用的写作类 skills

但它本身不是一个可以被 Codex 直接安装的标准 skill 包。

这个仓库做的事情是把这些内容转换成 Codex 原生格式，让 Codex 能直接：

- 自动识别论文写作、论文分析、审稿、翻译、科研绘图等请求
- 直接执行任务，而不是只返回一段提示词
- 用 `references/` 管理不同 prompt 工作流，避免把全部内容堆在一个超长 README 里

## 原项目与本仓库的区别

| 项目 | 原项目 | 本仓库 |
| --- | --- | --- |
| 主要形态 | README 提示词合集 | 标准 Codex skill 包 |
| 能否直接装进 Codex | 不能 | 可以 |
| 是否依赖 `SKILL.md` 触发 | 否 | 是 |
| 最适合的用途 | 阅读 prompt、找工具 | 在 Codex 中直接完成研究与写作任务 |
| 核心改造 | 提示词与分类思路 | 触发描述、路由规则、输出约定、reference prompt 库 |

## Part I: 写作 Prompt 集合

- [中转英](./awesome-ai-research-writing/references/prompt-routing.md#cn-to-en)
- [英转中](./awesome-ai-research-writing/references/prompt-routing.md#en-to-cn)
- [中转中](./awesome-ai-research-writing/references/prompt-routing.md#cn-to-cn)
- [缩写](./awesome-ai-research-writing/references/prompt-routing.md#shorten)
- [扩写](./awesome-ai-research-writing/references/prompt-routing.md#expand)
- [表达润色（英文论文）](./awesome-ai-research-writing/references/prompt-routing.md#polish-en)
- [表达润色（中文论文）](./awesome-ai-research-writing/references/prompt-routing.md#polish-zh)
- [逻辑检查](./awesome-ai-research-writing/references/prompt-routing.md#logic-check)
- [去 AI 味（LaTeX 英文）](./awesome-ai-research-writing/references/translation-and-humanize.md#de-ai-latex-en)
- [去 AI 味（Word 中文）](./awesome-ai-research-writing/references/translation-and-humanize.md#de-ai-word-zh)
- [论文架构图](./awesome-ai-research-writing/references/diagram-and-modeling.md#paper-figure-prompts)
- [实验绘图推荐](./awesome-ai-research-writing/references/diagram-and-modeling.md#experiment-figure-recommendation)
- [生成图的标题](./awesome-ai-research-writing/references/prompt-routing.md#figure-title)
- [生成表的标题](./awesome-ai-research-writing/references/prompt-routing.md#table-title)
- [实验分析](./awesome-ai-research-writing/references/prompt-routing.md#experiment-analysis)
- [论文整体以 Reviewer 视角进行审视](./awesome-ai-research-writing/references/strict-review.md#reviewer-review)
- [模型选择](./awesome-ai-research-writing/references/research-assistant.md#model-selection)
- [结构化读论文框架](./awesome-ai-research-writing/references/paper-reading.md#structured-reading)
- [论文分析（方法、实验、创新点）](./awesome-ai-research-writing/references/paper-reading.md#paper-analysis)
- [科研专家（改模型代码与想点子）](./awesome-ai-research-writing/references/research-assistant.md#research-expert)
- [加强版 AI 助手（查资料与联网核验）](./awesome-ai-research-writing/references/research-assistant.md#verified-assistant)
- [科研绘图专家（三层级英文提示词）](./awesome-ai-research-writing/references/diagram-and-modeling.md#paper-figure-prompts)
- [系统建模分析师（UML）](./awesome-ai-research-writing/references/diagram-and-modeling.md#uml-modeling)
- [英语长难句翻译](./awesome-ai-research-writing/references/translation-and-humanize.md#long-sentence-translation)
- [严格送审评议](./awesome-ai-research-writing/references/strict-review.md#strict-thesis-review)

## Part II: 论文写作相关的 Skills

- [Skills 的配置](./awesome-ai-research-writing/SKILL.md)
- [Skills 总览](./awesome-ai-research-writing/references/prompt-index.md)
- [使用场景与示例 Prompt](./awesome-ai-research-writing/references/prompt-index.md#usage-examples)
- [上游 Skills 与衔接建议](./awesome-ai-research-writing/references/upstream-skills.md)

## 仓库结构

```text
awesome-ai-research-writing/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── prompt-index.md
    ├── prompt-routing.md
    ├── paper-reading.md
    ├── research-assistant.md
    ├── diagram-and-modeling.md
    ├── translation-and-humanize.md
    ├── strict-review.md
    └── upstream-skills.md
```

各文件作用如下：

- `SKILL.md`
  - 定义 skill 的能力边界
  - 告诉 Codex 在什么场景触发
  - 规定核心工作流和输出规则
- `references/prompt-index.md`
  - 提供目录式 prompt 入口和示例调用
- `references/prompt-routing.md`
  - 负责核心写作任务路由
- `references/paper-reading.md`
  - 负责结构化读论文和系统性论文分析
- `references/research-assistant.md`
  - 负责科研问答、模型改进、模型选择
- `references/diagram-and-modeling.md`
  - 负责论文配图提示词和 UML 建模
- `references/translation-and-humanize.md`
  - 负责长难句翻译和去 AI 味改写
- `references/strict-review.md`
  - 负责 reviewer 风格审查和送审评议
- `references/upstream-skills.md`
  - 说明什么时候应该优先使用更专业的上游 skill
- `agents/openai.yaml`
  - 提供 Codex UI 元数据

## 安装方式

默认假设你在仓库根目录。

### 方式 1：手动安装

复制到 `$CODEX_HOME/skills/`：

```bash
mkdir -p "$CODEX_HOME/skills"
cp -R awesome-ai-research-writing "$CODEX_HOME/skills/"
```

如果没有设置 `CODEX_HOME`，可以使用默认目录：

```bash
mkdir -p "$HOME/.codex/skills"
cp -R awesome-ai-research-writing "$HOME/.codex/skills/"
```

### 方式 2：通过 Codex skill-installer 安装

如果你的环境里已经有 Codex 的 `skill-installer`，可以直接从 GitHub 安装：

```bash
python "$CODEX_HOME/skills/.system/skill-installer/scripts/install-skill-from-github.py" \
  --repo zengrong233/awesome-ai-research-writing-skill \
  --path awesome-ai-research-writing
```

安装完成后，重启 Codex 使 skill 生效。

## 设计原则

这个 skill 故意把 `SKILL.md` 控制得比较轻。

主文件只保留：

- 触发描述
- 工作流规则
- 输出约定

更细的 prompt 和工作流放在 `references/` 中按需加载，这样更接近真实可用的 skill 包，而不是单纯的提示词堆叠。

## 致谢与说明

本仓库改造自以下项目的思路、任务分类与工作流意图：

- [Leey21/awesome-ai-research-writing](https://github.com/Leey21/awesome-ai-research-writing)

它并不试图替代原项目，而是把那类内容转换成 Codex 更容易直接消费的 skill 包格式。

## 许可证

本仓库包含面向 Codex 的原创打包工作，同时也包含对上游项目思路与部分表达方式的适配整理。
具体授权边界请查看 [LICENSE](./LICENSE)。
