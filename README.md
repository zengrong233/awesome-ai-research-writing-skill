# Awesome AI Research Writing Skill for Codex

[![Codex Skill](https://img.shields.io/badge/Codex-Skill-0A66C2)](https://github.com/zengrong233/awesome-ai-research-writing-skill)
[![GitHub stars](https://img.shields.io/github/stars/zengrong233/awesome-ai-research-writing-skill?style=social)](https://github.com/zengrong233/awesome-ai-research-writing-skill)

[English README](README.en.md)

面向中英文学术研究的 Codex skill：从论文写作、翻译、阅读和审稿，到科研 PPT、实验数据图和方法框架图。默认直接完成任务；明确要求提示词时才返回模板。

## 这个仓库解决什么问题

让研究材料沿同一套证据与格式规则进入不同成果：

| 工作 | 能力 |
| --- | --- |
| 论文写作 | 中英互译、中文改写、润色、按目标缩写/扩写、逻辑检查、图表标题与实验分析 |
| 阅读与研究 | 结构化读论文、方法与实验分析、资料核验、模型选择和改进实验设计 |
| 审稿 | Reviewer 报告、送审评议；结论与实际提供的材料范围一致 |
| 科研 PPT | 文献汇报、组会、答辩、会议报告；证据故事线、时间安排、可编辑 PPTX、来源与演讲备注 |
| 科研论文绘图 | 数据对比、消融、分布与多面板图；方法框架图、训练/推理路径；源码、成图与最终尺寸检查 |
| 提示词与建模 | 三层级英文绘图提示词、实验选图建议、UML |

保留公式、引用键、数值、单位和不确定性。翻译区分可编辑稿与阅读版；缩写不再固定减少几个单词；缺少全文或统计证据时说明可判断范围。

## 原项目与本仓库的区别

本仓库沿用 [Leey21/awesome-ai-research-writing](https://github.com/Leey21/awesome-ai-research-writing) 的写作任务分类，将工作流整理为可安装的 `SKILL.md` 与按需加载的参考文件，并扩展科研演示和论文绘图能力。原项目的当前能力与授权以其仓库为准。

## Part I: Prompt 与工作流目录

完整入口、旧提示词条目与调用示例统一维护在 [工作流目录](awesome-ai-research-writing/references/prompt-index.md)。

快速使用：

```text
用 $awesome-ai-research-writing 把下面的方法草稿翻译成英文 LaTeX，保留公式和引用，只返回正文。
用 $awesome-ai-research-writing 将这篇论文做成 12 分钟中文组会 PPT，交付可编辑 PPTX，附来源和讲稿。
用 $awesome-ai-research-writing 根据 CSV 绘制对比图，标明原始点与误差线含义，交付源码、SVG 和 PNG。
用 $awesome-ai-research-writing 根据 Method 和代码画框架图，区分训练和推理，交付可编辑源文件。
```

也可以只要求大纲、绘图建议或提示词；技能会遵循指定交付形式。修改已有 PPT 时，说明目标页和保留要求即可。

## Part II: 论文写作相关的 Skills

- [技能入口与路由](awesome-ai-research-writing/SKILL.md)
- [科研 PPT 工作流](awesome-ai-research-writing/references/research-presentations.md)
- [实验数据绘图](awesome-ai-research-writing/references/scientific-data-figures.md)
- [论文框架绘图](awesome-ai-research-writing/references/framework-figures.md)
- [参考项目、许可记录与专业工具衔接](awesome-ai-research-writing/references/upstream-skills.md)

本包提供工作流指令，不捆绑 PPT 渲染器、Python/R 绘图库或图像生成服务。生成文件时复用当前环境的工具或已安装的专业 skill。请求实际 PPT/成图时会在工具允许下创建文件，并检查渲染结果；缺少能力时交付可用源码或方案，明确尚未完成的导出或视觉检查。

## 仓库结构

```text
awesome-ai-research-writing/
├── SKILL.md
├── agents/openai.yaml
└── references/
    ├── prompt-index.md
    ├── prompt-routing.md
    ├── paper-reading.md
    ├── research-assistant.md
    ├── strict-review.md
    ├── translation-and-humanize.md
    ├── research-presentations.md
    ├── scientific-data-figures.md
    ├── framework-figures.md
    ├── diagram-and-modeling.md
    └── upstream-skills.md
```

安装单元仍是 `awesome-ai-research-writing/`；其他目录不需要复制进 skills。

## 安装方式

### 方式 1：手动安装

在仓库根目录执行。已有同名安装时先备份并按需替换，避免混入旧版本文件。

macOS / Linux：

```bash
skill_home="${CODEX_HOME:-$HOME/.codex}"
skill_target="$skill_home/skills/awesome-ai-research-writing"
if [ -e "$skill_target" ] || [ -L "$skill_target" ]; then
  printf '%s\n' "Skill already exists: $skill_target. Back it up and move it before installing." >&2
  exit 1
fi
mkdir -p "$skill_home/skills"
cp -R awesome-ai-research-writing "$skill_target"
```

Windows PowerShell：

```powershell
$skillHome = if ($env:CODEX_HOME) { $env:CODEX_HOME } else { Join-Path $env:USERPROFILE '.codex' }
$skillTarget = Join-Path $skillHome 'skills/awesome-ai-research-writing'
if (Test-Path -LiteralPath $skillTarget) {
    throw "Skill already exists: $skillTarget. Back it up and move it before installing."
}
New-Item -ItemType Directory -Force -Path (Join-Path $skillHome 'skills') -ErrorAction Stop | Out-Null
Copy-Item -Recurse '.\awesome-ai-research-writing' -Destination $skillTarget -ErrorAction Stop
```

### 方式 2：通过 Codex skill-installer 安装

适用于环境已有 `skill-installer` 的情况。安装远端已发布的版本；本地修改请使用手动安装。

macOS / Linux：

```bash
python "${CODEX_HOME:-$HOME/.codex}/skills/.system/skill-installer/scripts/install-skill-from-github.py" \
  --repo zengrong233/awesome-ai-research-writing-skill \
  --path awesome-ai-research-writing
```

Windows PowerShell：

```powershell
$skillHome = if ($env:CODEX_HOME) { $env:CODEX_HOME } else { Join-Path $env:USERPROFILE '.codex' }
python (Join-Path $skillHome 'skills\.system\skill-installer\scripts\install-skill-from-github.py') `
  --repo zengrong233/awesome-ai-research-writing-skill `
  --path awesome-ai-research-writing
```

安装后重启 Codex，并使用 `$awesome-ai-research-writing` 调用。

## 设计原则

主入口保留路由与共同约束，具体工作流按需加载。用户指定的格式与模板优先；文本编辑不强加回译或修改日志；数据和示意图分别处理，所有定量结论有来源。PPT 与成图的可编辑性、导出和视觉检查以实际文件为准。

维护时可运行已安装的 skill-creator 校验器（需要 Python 及 PyYAML）：

```bash
python "${CODEX_HOME:-$HOME/.codex}/skills/.system/skill-creator/scripts/quick_validate.py" awesome-ai-research-writing
```

Windows PowerShell：

```powershell
$skillHome = if ($env:CODEX_HOME) { $env:CODEX_HOME } else { Join-Path $env:USERPROFILE '.codex' }
python (Join-Path $skillHome 'skills/.system/skill-creator/scripts/quick_validate.py') .\awesome-ai-research-writing
```

同时检查本地链接、旧锚点、UI 元数据和代表性任务。这个结构检查不替代 PPT 或图像的视觉验收。

## 致谢与说明

写作分类参考 Leey21 的原始合集；科研 PPT 与绘图工作流参考 [Nature Skills](https://github.com/Yuan1z0825/nature-skills)、[Paper Framework Figure Studio Pro](https://github.com/c-narcissus/paper-framework-figure-studio-pro) 和 [SciPilot Figure](https://github.com/Haojae/scipilot-figure-skill)。参考版本、借鉴范围及许可依据见 [来源记录](awesome-ai-research-writing/references/upstream-skills.md#reference-projects)。本包未附带这些项目的运行时或素材。

## 许可证

本仓库原创建包与上游适配内容的授权边界见 [LICENSE](LICENSE)。参考项目的许可各自适用，不能据此推定所有历史内容具有同一许可。
