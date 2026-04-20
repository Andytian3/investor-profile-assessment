---
name: investor-profile-assessment
description: Assess a person's investment style and risk preference to build a reusable investor profile. Use when Codex needs to run 投资画像测试、风险偏好测试、投资风格访谈、个性化投资决策分析前的画像采集，或把访谈结果整理为结构化投资画像与决策约束。
---

# Investor Profile Assessment

Run this skill to interview a person, infer their investment style and risk preference, and output a profile that can be reused in later investment analysis.

## Select The Depth

- Use `quick` for a fast screening. Ask `6` case cards plus `2-3` open questions.
- Use `standard` by default. Ask `8-10` case cards plus `6` open questions and resolve the main contradictions.
- Use `deep` for high-stakes profiling. Ask `12+` case cards, add asset-specific cards, and run a stronger contradiction check.

## Run The Interview

1. Explain in one sentence that this is not a brokerage questionnaire; it is a decision-style reading based on real scenarios.
2. Start with case cards, not factual form-filling.
3. Ask users to answer most case cards with only `是` or `否`.
4. Keep the rhythm fast: `3-4` case cards per turn.
5. After each cluster, reflect back what you are seeing in plain Chinese so the interview feels alive.
6. Ask open questions later to capture hard constraints, actual drawdown history, current acceptable future drawdown, real capital horizon, and monitoring budget.
7. Distinguish `risk capacity` from `risk tolerance`. Do not merge them.
8. Ask follow-up questions only when uncertainty is still material.
9. Stop when the main dimensions are scoreable and the major contradictions have been checked.

Use [question-bank.md](./references/question-bank.md) as the main interview source.

## Cover The Modules In Order

1. Use core case cards to read first-order signals: liquidity discipline, drawdown tolerance, FOMO, concentration, style, process, and complexity appetite.
2. Use open questions to capture hard constraints: real money horizon, actual investment history, target return, maximum lived drawdown, acceptable future drawdown, and monitoring budget.
3. Add asset-specific case cards only when the user actively invests in crypto, leverage, options, private assets, or concentrated single names.
4. Run contradiction checks if stated goals and case-card behavior do not match.

Avoid the tone of a securities suitability survey. The conversation should feel like discussing real investment decisions, not filling out compliance paperwork.

## Resolve Contradictions Explicitly

Ask at least one reconciliation question if any of the following appear:

- The user wants high returns but cannot accept normal equity drawdowns.
- The user claims to be long-term but needs the money within 12 months.
- The user prefers concentrated bets but lacks research depth or decision discipline.
- The user wants complex products but cannot explain how losses happen.
- The user reports calm behavior but their historical actions show panic-selling or FOMO-chasing.

Use contradiction probes from [question-bank.md](./references/question-bank.md) instead of guessing.

## Score The Profile

Score each dimension using [scoring-framework.md](./references/scoring-framework.md).

Always do the following:

- Score from clustered case-card evidence plus open-question evidence, not from one impressive answer.
- Leave a dimension as `unknown` when the evidence is weak.
- Separate `hard constraints` from `soft preferences`.
- Distinguish `lived drawdown` from `acceptable future drawdown`. The first informs tolerance; the second constrains future recommendations.
- Cap the final risk band when objective capacity is low, even if stated tolerance is high.
- Add an execution-risk warning when ambition and complexity are high but discipline is weak.

## Produce The Output

Use [output-template.md](./references/output-template.md) for the final deliverable.

The output should contain:

- A one-sentence investor summary.
- A short readout of the most revealing case-card reactions.
- Structured dimension scores with evidence.
- Primary and secondary style labels.
- Hard constraints for future analysis.
- Behavioral risks and suggested guardrails.
- A machine-readable block for future personalized investment analysis.

## Translate The Profile Into Future Decision Rules

Convert the profile into actionable analysis rules. At minimum, define:

- acceptable drawdown range
- preferred holding period
- liquidity requirements
- position concentration comfort
- acceptable complexity level
- preferred evidence type
- decision cadence and review triggers
- maximum monitoring load the user can realistically sustain
- strategies or instruments that should be avoided unless explicitly approved

Future investment analysis should be judged against these rules instead of generic “good or bad” opinions.

## Stay Within Scope

- Do not present the profile as legal suitability advice.
- Do not assume that age, income, or experience alone determines risk preference.
- Do not force a single archetype if the user is clearly hybrid.
- Do not hide uncertainty. Call out missing data and confidence level.
