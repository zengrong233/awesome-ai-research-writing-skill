# Awesome AI Research Writing Skill for Codex

[![Codex Skill](https://img.shields.io/badge/Codex-Skill-0A66C2)](https://github.com/zengrong233/awesome-ai-research-writing-skill)
[![Validation](https://img.shields.io/badge/quick__validate-passing-2EA043)](https://github.com/zengrong233/awesome-ai-research-writing-skill)
[![GitHub stars](https://img.shields.io/github/stars/zengrong233/awesome-ai-research-writing-skill?style=social)](https://github.com/zengrong233/awesome-ai-research-writing-skill)

[English README](./README.en.md)

把一个“提示词合集 / skills 导航型项目”改造成 Codex 可直接安装和触发的 skill 包。

这个仓库基于 [Leey21/awesome-ai-research-writing](https://github.com/Leey21/awesome-ai-research-writing) 的任务分类和工作流思路，重新组织为 Codex 可识别的 `SKILL.md` 结构。

## 这个仓库解决什么问题

原项目非常适合：

- 查阅论文写作 prompt
- 了解常见写作场景
- 发现其他好用的写作类 skills

但它本身不是一个可以被 Codex 直接安装的标准 skill 包。

这个仓库做的事情是把这些内容转换成 Codex 原生格式，让 Codex 能直接：

- 自动识别论文写作类请求
- 直接执行写作、改写、翻译、审稿式检查
- 用 `references/` 管理任务细节，而不是把所有内容塞进一个超长 README

## 原项目与本仓库的区别

| 项目 | 原项目 | 本仓库 |
| --- | --- | --- |
| 主要形态 | README 提示词合集 | 标准 Codex skill 包 |
| 能否直接装进 Codex | 不能 | 可以 |
| 是否依赖 `SKILL.md` 触发 | 否 | 是 |
| 最适合的用途 | 阅读 prompt、找工具 | 在 Codex 中直接完成写作任务 |
| 核心改造 | 提示词与分类思路 | 触发描述、路由规则、输出约定、references |

## 常见提示词 / 触发示例

适合处理这些高频科研写作任务：

- 中文草稿 -> 英文学术 LaTeX
- 英文 LaTeX -> 可读中文
- 中文论文段落重写
- 英文学术润色
- 缩写或扩写段落
- 去 AI 味 / humanize
- 逻辑检查
- 图标题、表标题、caption
- 实验分析写作
- reviewer 视角的论文审查

直接在 Codex 中输入类似下面的话即可：

```text
Use $awesome-ai-research-writing to rewrite this Chinese method draft into English LaTeX.
Use $awesome-ai-research-writing to polish this Introduction and remove AI-sounding phrasing.
Use $awesome-ai-research-writing to shorten this paragraph by about 10 words without losing technical meaning.
Use $awesome-ai-research-writing to analyze the following experiment table in paper style.
Use $awesome-ai-research-writing to review this paper section from a strict reviewer perspective.
```

## 仓库结构

```text
awesome-ai-research-writing/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── prompt-routing.md
    └── upstream-skills.md
```

各文件作用如下：

- `SKILL.md`
  - 定义 skill 的能力边界
  - 告诉 Codex 在什么场景触发
  - 规定核心工作流和输出规则
- `references/prompt-routing.md`
  - 负责把用户需求路由到正确的写作行为
  - 把翻译、润色、缩写、扩写、实验分析、review 等细节从主 skill 文件里拆出来
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

更细的任务细节放在 `references/` 中按需加载，这样更接近真实可用的 skill 包，而不是单纯的提示词堆叠。

## 与上游 skills 的关系

这个仓库并不想替代所有更强的专业写作 skill。
它更像一层适合 Codex 的“双语学术写作路由器”。

尤其适合：

- 翻译
- 段落改写
- 论文润色
- reviewer 视角检查

如果任务更深、更专门，也可以继续衔接这些上游 skill：

- `research-paper-writing`
- `humanizer`
- `docx`
- `doc-coauthoring`
- `canvas-design`

## 致谢与说明

本仓库改造自以下项目的思路、任务分类与工作流意图：

- [Leey21/awesome-ai-research-writing](https://github.com/Leey21/awesome-ai-research-writing)

它并不试图替代原项目，而是把那类内容转换成 Codex 更容易直接消费的 skill 包格式。

## 许可证

本仓库包含面向 Codex 的原创打包工作，同时也包含对上游项目思路与部分表达方式的适配整理。
具体授权边界请查看 [LICENSE](./LICENSE)。
