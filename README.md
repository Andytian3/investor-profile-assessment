# investor-profile-assessment

A Codex skill for investor profiling and risk preference assessment.

`investor-profile-assessment` 是一个用于 AI / Codex 工作流的投资者画像 skill。它通过情景题、开放式追问和评分框架，帮助用户识别自己的投资风格、风险偏好和真实决策约束，并输出一个可复用的结构化投资画像，供后续个性化投资分析继续使用。

## 这个 Skill 是干什么的

- 用真实投资决策场景，而不是表格式开户问卷，来识别用户的投资行为特征。
- 评估用户在流动性、回撤承受、FOMO、仓位集中、复杂产品接受度、研究方式等方面的偏好。
- 明确区分 `risk capacity` 和 `risk tolerance`，避免把客观承受能力和主观偏好混在一起。
- 把访谈结果整理成后续分析可复用的投资画像和决策约束。

## 适用场景

- 投资画像测试
- 风险偏好测试
- 投资风格访谈
- 个性化投资分析前的用户建档
- 为后续策略讨论建立 `hard constraints` 和 `soft preferences`

## 产出内容

- 一句话投资者总结
- 最有代表性的案例题反应
- 各维度评分与证据
- 主风格 / 次风格标签
- 后续分析必须遵守的约束条件
- 主要行为风险与建议 guardrails
- 一个可供后续 agent 继续复用的 machine-readable 结构化区块

## 仓库结构

- `SKILL.md`：skill 的核心执行说明
- `references/question-bank.md`：访谈题库
- `references/scoring-framework.md`：评分框架
- `references/output-template.md`：最终输出模板
- `agents/openai.yaml`：界面展示元数据

## 使用方式

在支持 Codex skills 的环境里调用 `$investor-profile-assessment`，即可启动一次投资者画像访谈并生成结构化结果。

默认会通过案例题和追问逐步判断用户的投资决策风格，再把结论沉淀为后续投资分析可直接复用的规则。

## Scope

这个 skill 用于投资决策风格分析，不构成法律、合规或券商 suitability advice。
