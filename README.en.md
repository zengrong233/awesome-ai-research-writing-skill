# Awesome AI Research Writing Skill for Codex

[![Codex Skill](https://img.shields.io/badge/Codex-Skill-0A66C2)](https://github.com/zengrong233/awesome-ai-research-writing-skill)
[![GitHub stars](https://img.shields.io/github/stars/zengrong233/awesome-ai-research-writing-skill?style=social)](https://github.com/zengrong233/awesome-ai-research-writing-skill)

[中文主页](README.md)

A Codex skill for bilingual academic writing, paper reading and review, research presentations, quantitative plots, and method diagrams. It completes the requested task directly; reusable prompts are returned when explicitly requested.

## Why This Exists

Carry the same evidence and formatting rules across research outputs:

| Work | Capabilities |
| --- | --- |
| Paper writing | Chinese/English translation, rewriting, polishing, target-based shortening/expansion, logic checks, captions, and result analysis |
| Reading and research | Guided reading, method/experiment analysis, verified Q&A, model selection, and improvement experiments |
| Review | Reviewer reports and thesis readiness assessments scoped to the supplied evidence |
| Research PPT | Journal clubs, group meetings, defenses, and conference talks; source-grounded stories, timing, editable PPTX, attribution, and speaker notes |
| Scientific figures | Comparisons, ablations, distributions, multi-panel results, framework diagrams, and training/inference paths; editable source, exports, and final-size inspection |
| Prompts and modeling | Three-level English figure prompts, chart recommendations, and UML |

Preserve equations, citation keys, values, units, and uncertainty. Distinguish editable translations from reading versions. Follow the requested length rather than a fixed word adjustment, and limit judgments when full manuscripts or statistical evidence are unavailable.

## Original Project vs This Repository

This package builds on the task taxonomy of [Leey21/awesome-ai-research-writing](https://github.com/Leey21/awesome-ai-research-writing), organizing workflows into an installable `SKILL.md` and references loaded on demand. It adds research presentations and scientific figures. Consult the original repository for its current capabilities and rights status.

## Part I: Prompt And Workflow Catalog

The [workflow catalog](awesome-ai-research-writing/references/prompt-index.md) is the single index of all routes, legacy prompt entries, and examples.

```text
Use $awesome-ai-research-writing to translate this method draft into English LaTeX. Preserve equations and citations; return only the text.
Use $awesome-ai-research-writing to turn this paper into a 12-minute journal-club PPT. Deliver editable PPTX with source attribution and speaker notes.
Use $awesome-ai-research-writing to plot this CSV comparison, showing raw observations and defining uncertainty. Deliver source, SVG, and PNG.
Use $awesome-ai-research-writing to draw an editable framework figure from the Method and code, distinguishing training from inference.
```

Outline-only, recommendation-only, and prompt-only requests are supported. For an existing deck, specify the target slides and what must be preserved.

## Part II: Related Skill Resources

- [Skill entry and routing](awesome-ai-research-writing/SKILL.md)
- [Research presentations](awesome-ai-research-writing/references/research-presentations.md)
- [Scientific data figures](awesome-ai-research-writing/references/scientific-data-figures.md)
- [Framework figures](awesome-ai-research-writing/references/framework-figures.md)
- [Reference projects, license evidence, and specialized tools](awesome-ai-research-writing/references/upstream-skills.md)

This package supplies instructions, not bundled slide renderers, Python/R plotting libraries, or image services. It uses tools or specialized skills available in the current environment. For file requests, create the actual artifact and inspect rendered output when possible. If a capability is missing, deliver usable source or a plan and identify the exact export or visual check still incomplete.

## Repository Overview

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

The installable unit remains `awesome-ai-research-writing/`; other directories do not belong in the skills installation.

## Installation

### Option 1: Manual Install

Run from the repository root. Back up and replace an existing installation deliberately to avoid mixing old and new files.

macOS / Linux:

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

Windows PowerShell:

```powershell
$skillHome = if ($env:CODEX_HOME) { $env:CODEX_HOME } else { Join-Path $env:USERPROFILE '.codex' }
$skillTarget = Join-Path $skillHome 'skills/awesome-ai-research-writing'
if (Test-Path -LiteralPath $skillTarget) {
    throw "Skill already exists: $skillTarget. Back it up and move it before installing."
}
New-Item -ItemType Directory -Force -Path (Join-Path $skillHome 'skills') -ErrorAction Stop | Out-Null
Copy-Item -Recurse '.\awesome-ai-research-writing' -Destination $skillTarget -ErrorAction Stop
```

### Option 2: Install With The Codex Skill Installer

Use when `skill-installer` is available. This installs the published remote version; use manual installation for local changes.

macOS / Linux:

```bash
python "${CODEX_HOME:-$HOME/.codex}/skills/.system/skill-installer/scripts/install-skill-from-github.py" \
  --repo zengrong233/awesome-ai-research-writing-skill \
  --path awesome-ai-research-writing
```

Windows PowerShell:

```powershell
$skillHome = if ($env:CODEX_HOME) { $env:CODEX_HOME } else { Join-Path $env:USERPROFILE '.codex' }
python (Join-Path $skillHome 'skills\.system\skill-installer\scripts\install-skill-from-github.py') `
  --repo zengrong233/awesome-ai-research-writing-skill `
  --path awesome-ai-research-writing
```

Restart Codex after installation and invoke `$awesome-ai-research-writing`.

## Design Principles

Keep shared rules and routing in the entrypoint; load detailed workflows on demand. User formats and templates take precedence. Editing does not force back-translation or logs. Quantitative panels and schematic panels use distinct evidence rules. Editability, export success, and visual verification depend on the actual delivered files.

Maintainers can run the installed skill-creator validator (Python and PyYAML required):

```bash
python "${CODEX_HOME:-$HOME/.codex}/skills/.system/skill-creator/scripts/quick_validate.py" awesome-ai-research-writing
```

Windows PowerShell:

```powershell
$skillHome = if ($env:CODEX_HOME) { $env:CODEX_HOME } else { Join-Path $env:USERPROFILE '.codex' }
python (Join-Path $skillHome 'skills/.system/skill-creator/scripts/quick_validate.py') .\awesome-ai-research-writing
```

Also check local links, legacy anchors, UI metadata, and representative tasks. Package validation does not replace visual inspection of generated decks or figures.

## Attribution

The writing taxonomy references Leey21's original collection. Presentation and figure workflows draw design lessons from [Nature Skills](https://github.com/Yuan1z0825/nature-skills), [Paper Framework Figure Studio Pro](https://github.com/c-narcissus/paper-framework-figure-studio-pro), and [SciPilot Figure](https://github.com/Haojae/scipilot-figure-skill). Inspected revisions, adaptation scope, and license evidence are recorded in [provenance](awesome-ai-research-writing/references/upstream-skills.md#reference-projects). Their runtimes and assets are not bundled.

## License

See [LICENSE](LICENSE) for original packaging rights and the upstream-material limitation. Each referenced project's license applies to its own material; it does not establish a single license for all historical content here.
