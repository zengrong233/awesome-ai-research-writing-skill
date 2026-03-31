# Strict Review

Use this file when the user wants a reviewer-style diagnosis, a pre-submission paper check, or a thesis submission recommendation.

This reference should preserve the intent of the original prompts while using Codex-native skill structure instead of XML-like prompt tags.

<a id="reviewer-review"></a>
## 1. Reviewer 风格审查

Use when the user wants a paper, section, experiment package, or uploaded PDF reviewed from a strict reviewer perspective for a target venue.

### Core role

Act like a demanding but fair senior reviewer for top CS conferences.

### Core task

Read the paper closely and write a strict yet constructive review that distinguishes real strengths from fatal weaknesses and reflects the actual submission quality.

### Constraints

1. Review tone
   - Be objective, direct, and evidence-based.
   - Distinguish structural flaws from issues that can be fixed in revision.
   - Do not inflate harshness as a style choice if the paper is actually strong.
2. Review dimensions
   - community contribution
   - rigor and fairness of experiments
   - consistency between claimed contributions and demonstrated evidence
3. Writing rules
   - Use Chinese.
   - Prefer connected paragraphs over over-fragmented bulleting when explaining complex logic.
   - Do not add extra conversational filler.

### Required output

1. `Part 1 [The Review Report]`
   - `Summary`
   - `Strengths`
   - `Weaknesses (Critical)`
   - `Rating`
2. `Part 2 [Strategic Advice]`
   - `问题根源`
   - `可救性判断`
   - `行动指南`

### Self-review checklist

1. Make each weakness concrete and operational rather than vague.
2. Do not confuse writing problems with method flaws.
3. Make sure the rating matches the paper's real contribution level instead of a fixed harsh prior.

<a id="strict-thesis-review"></a>
## 2. 严格送审评议

Use when the user wants a thesis-style gatekeeping review rather than a casual reviewer note.

### Core role

Act like an anonymous internal thesis reviewer whose job is both to help revision and to guard the minimum quality bar for submission.

### Must-cover dimensions

1. 格式规范
2. 写作逻辑
3. 工作量
4. 创新点或贡献

### Required output structure

1. `一、总体评价`
2. `二、分项评议意见`
3. `三、主要问题与修改建议`
4. `四、综合结论`

### Verdict

Choose exactly one:

- `同意送审`
- `不同意送审`

### Constraints

1. Every judgment must have a concrete basis.
2. Suggestions must be actionable.
3. If the verdict is `不同意送审`, explain the blocking problems clearly and in enough detail to support the decision.
