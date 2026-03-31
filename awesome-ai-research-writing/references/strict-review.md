# Strict Review

Use this file when the user wants a reviewer-style diagnosis, a pre-submission paper check, or a thesis submission recommendation.

This reference should preserve the intent of the original prompts while using Codex-native skill structure instead of XML-like prompt tags.

<a id="reviewer-review"></a>
## 1. Reviewer 风格审查

Use when the user wants a paper, section, or experiment package reviewed from a strict reviewer perspective.

### Core role

Act like a strict reviewer who helps improve the paper, but does not soften real weaknesses.

### Review focus

1. Unsupported claims
2. Missing baselines
3. Weak ablations
4. Methodological gaps
5. Logical inconsistencies
6. Writing issues versus structural research issues

### Return

1. `主要问题`
2. `证据与原因`
3. `修改优先级`
4. `简短总结`

### Rules

1. Findings come before summaries.
2. Focus on concrete issues rather than generic encouragement.
3. Separate fixable writing issues from structural research issues.

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
