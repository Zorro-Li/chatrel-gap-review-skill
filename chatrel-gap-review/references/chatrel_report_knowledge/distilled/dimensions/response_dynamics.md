# 回复节奏与可获得性 / `response_dynamics`

- latest_status: 未覆盖
- audit_reason: `inbox_empty`
- evaluation_question: 两个人在时间上是否能接住对方？

## 应补进报告的判断点

- `median_response_latency`
- `late_reply_rate`
- `same_day_reply_rate`
- `silence_gaps`
- `turn_taking_balance`

## 输出字段

- `availability_score`
- `response_latency_pattern`
- `silence_pattern`
- `turn_taking_notes`

## 行为模式判断规则

- 按会话轮次计算回复延迟、中断、沉默间隔和同日回复率。
- 把慢回复分成稳定慢、冲突后慢、单方慢和关系冷却期慢。

## RAG 论文证据

### Evidence 1
- paper: 2025 NaturalTurn: a method to segment speech into psychologically meaningful conversational turns
- level: B_transferable_conversation_evidence
- doi: https://doi.org/10.1038/s41598-025-24381-1

### Evidence 2
- paper: 2026 THE INTELLIGENT SILENCE ARCHITECTURE - TISA
- level: A_direct_chat_evidence
- doi: https://doi.org/10.5281/zenodo.19430905

### Evidence 3
- paper: 2026 THE INTELLIGENT SILENCE ARCHITECTURE - TISA
- level: A_direct_chat_evidence
- doi: https://doi.org/10.5281/zenodo.19430906

### Evidence 4
- paper: 2025 NaturalTurn: a method to segment speech into psychologically meaningful conversational turns
- level: B_transferable_conversation_evidence
- doi: https://doi.org/10.1038/s41598-025-24381-1

### Evidence 5
- paper: 2025 NaturalTurn: a method to segment speech into psychologically meaningful conversational turns
- level: B_transferable_conversation_evidence
- doi: https://doi.org/10.1038/s41598-025-24381-1
