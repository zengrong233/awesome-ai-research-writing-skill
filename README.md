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

## Part I: Prompt 与工作流目录

完整、可点击、与 skill 实际能力同步的权威目录请看：

- [prompt-index.md](./awesome-ai-research-writing/references/prompt-index.md)

常见能力可以按 4 组理解：

- 翻译与改写：中转英、英转中、中转中、缩写、扩写、英文润色、中文润色、去 AI 味
- 阅读与分析：结构化读论文、论文分析、实验分析、科研问答、科研专家
- 审稿与决策：Reviewer 视角审视、严格送审评议、模型选择
- 图示与建模：论文架构图、实验绘图推荐、图标题、表标题、UML 建模

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

Unix-like / macOS / Linux：

```bash
mkdir -p "$CODEX_HOME/skills"
cp -R awesome-ai-research-writing "$CODEX_HOME/skills/"
```

如果没有设置 `CODEX_HOME`，可以使用默认目录：

```bash
mkdir -p "$HOME/.codex/skills"
cp -R awesome-ai-research-writing "$HOME/.codex/skills/"
```

Windows PowerShell：

```powershell
$codexHome = if ($env:CODEX_HOME) { $env:CODEX_HOME } else { Join-Path $env:USERPROFILE ".codex" }
New-Item -ItemType Directory -Force -Path (Join-Path $codexHome "skills") | Out-Null
Copy-Item -Recurse -Force ".\awesome-ai-research-writing" (Join-Path $codexHome "skills")
```

### 方式 2：通过 Codex skill-installer 安装

如果你的环境里已经有 Codex 的 `skill-installer`，可以直接从 GitHub 安装。

Unix-like / macOS / Linux：

```bash
python "$CODEX_HOME/skills/.system/skill-installer/scripts/install-skill-from-github.py" \
  --repo zengrong233/awesome-ai-research-writing-skill \
  --path awesome-ai-research-writing
```

Windows PowerShell：

```powershell
$codexHome = if ($env:CODEX_HOME) { $env:CODEX_HOME } else { Join-Path $env:USERPROFILE ".codex" }
python (Join-Path $codexHome "skills\.system\skill-installer\scripts\install-skill-from-github.py") `
  --repo zengrong233/awesome-ai-research-writing-skill `
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
