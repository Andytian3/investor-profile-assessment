# 投资画像输出模板

在完成访谈后，按下面的结构输出。先给人读版本，再给机器读版本。

## 人读版本

```markdown
# 个人投资画像

## 一句话画像
[用一句话概括这个人的风险风格、决策方式和主要约束]

## 核心标签
- 风险标签：[资本保全型 / 稳健收益型 / 均衡成长型 / 进取增长型 / 高波动机会型]
- 主风格：[style]
- 副风格：[style]
- 画像置信度：[低 / 中 / 高]

## 关键案例信号
- [例如：C2 是 -> 对单标的短期大跌容忍度较高]
- [例如：C4 否 -> 不容易因为他人暴赚而冲动入场]
- [例如：C8 是 -> 愿意用仓位表达高信念]
- [例如：C9 是 -> 决策过程结构化程度较高]

## 维度评分
| 维度 | 分数 | 关键证据 |
| --- | --- | --- |
| Risk Capacity | [1-5] | [...] |
| Risk Tolerance | [1-5] | [...] |
| Return Ambition | [1-5] | [...] |
| Horizon Commitment | [1-5] | [...] |
| Liquidity Flexibility | [1-5] | [...] |
| Concentration Preference | [1-5] | [...] |
| Process Structure | [1-5] | [...] |
| Behavioral Discipline | [1-5] | [...] |
| Complexity Appetite | [1-5] | [...] |

## 评分校准与警报
- 基础风险分：[例如 3.64]
- 最终风险分：[例如 3.64 / 3.14]
- 触发修正：[例如 容量封顶 / 纪律降档 / 无]
- 执行警报：[例如 execution-risk-warning / drawdown-gap-warning / 无]

## 硬约束
- 当前可接受组合回撤：[例如 10%-15% / 20%-25%]
- 单个高信念仓位可接受回撤：[例如 20%-30% / 30%-40%]
- 流动性要求：[高 / 中 / 低]
- 推荐复杂度上限：[低 / 中 / 高]
- 每周可投入时间：[例如 3 小时 / 10 小时]
- 可接受维护方式：[低频复盘 / 每周跟踪 / 高频盯盘]
- 不宜触碰的策略或工具：[...]
- 必须额外说明风险的场景：[...]

## 风格偏好
- 偏好的收益来源：[估值修复 / 成长复利 / 趋势 / 现金流 / 事件驱动 / 主题弹性]
- 偏好的持有周期：[短 / 中 / 长]
- 偏好的组合形态：[分散 / 核心-卫星 / 高集中]
- 偏好的决策依据：[基本面 / 技术面 / 宏观 / 系统规则 / 混合]

## 行为风险与干预建议
- 主要行为偏差：[FOMO / 损失厌恶 / 锚定 / 过度自信 / 从众 / 回避复盘]
- 触发场景：[...]
- 推荐护栏：[仓位上限 / 分批建仓 / 预设失效条件 / 周期复盘 / 降低盯盘频率 / 强制记录理由]

## 未来个性化分析规则
- 以后给这个人的投资建议时，应优先匹配：[...]
- 以后应避免默认推荐：[...]
- 每次分析必须显式说明的项目：[预期收益、最大回撤、持有周期、流动性、核心风险、失效条件、仓位逻辑、维护要求]
- 如果建议与其画像冲突，要先指出冲突点，再决定是否继续分析。

## 待补充信息
- [...]
```

## 机器读版本

```json
{
  "profile_version": "1.1",
  "assessment_mode": "quick|standard|deep",
  "summary": "",
  "confidence": "low|medium|high",
  "risk_band": "",
  "style_primary": "",
  "style_secondary": "",
  "case_signals": [
    {
      "card_id": "",
      "answer_raw": "",
      "answer_normalized": "yes|no|mixed|conditional",
      "inference": []
    }
  ],
  "scores": {
    "risk_capacity": null,
    "risk_tolerance": null,
    "return_ambition": null,
    "horizon_commitment": null,
    "liquidity_flexibility": null,
    "concentration_preference": null,
    "process_structure": null,
    "behavioral_discipline": null,
    "complexity_appetite": null
  },
  "evidence": {
    "risk_capacity": [],
    "risk_tolerance": [],
    "return_ambition": [],
    "horizon_commitment": [],
    "liquidity_flexibility": [],
    "concentration_preference": [],
    "process_structure": [],
    "behavioral_discipline": [],
    "complexity_appetite": []
  },
  "risk_scoring": {
    "base_risk_score": null,
    "final_risk_score": null,
    "adjustments": [],
    "warnings": []
  },
  "hard_constraints": {
    "max_drawdown_tolerance": "",
    "target_portfolio_drawdown_pct": null,
    "target_single_position_drawdown_pct": null,
    "liquidity_need": "",
    "complexity_ceiling": "",
    "monitoring_hours_per_week": null,
    "monitoring_style": "",
    "forbidden_or_sensitive_instruments": [],
    "capital_use_horizon": ""
  },
  "preferences": {
    "preferred_return_source": [],
    "preferred_holding_period": "",
    "preferred_portfolio_shape": "",
    "preferred_evidence_type": [],
    "review_cadence": ""
  },
  "behavioral_biases": [],
  "guardrails": [],
  "future_analysis_rules": {
    "prefer": [],
    "avoid_by_default": [],
    "must_disclose_each_time": [
      "expected_return",
      "expected_drawdown",
      "holding_period",
      "liquidity",
      "core_risks",
      "invalidation_conditions",
      "position_sizing_logic",
      "monitoring_requirement"
    ],
    "conflict_policy": "If an idea conflicts with the profile, explain the mismatch before recommending it."
  },
  "contradictions": [],
  "unknowns": []
}
```

## 输出要求

- 证据字段尽量引用用户原意，不必长篇摘录。
- 不要因为需要完整 JSON 就虚构缺失信息。
- 如果画像存在明显内部冲突，在 `unknowns` 或总结中明确写出。
- 如果未来分析要调用这份画像，优先使用 `hard_constraints` 和 `future_analysis_rules`。
- `confidence` 统一使用 `low|medium|high`，不要临时扩展成 `medium-high` 之类的新枚举。
