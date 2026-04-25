# 数据充分性 / `data_sufficiency`

- latest_status: 未覆盖
- audit_reason: `inbox_empty`
- evaluation_question: 这份聊天记录是否足够支持关系分析？

## 应补进报告的判断点

- `message_count`
- `speaker_count`
- `time_span_days`
- `text_message_count`
- `voice_count`
- `image_count`
- `missing_text_ratio`

## 输出字段

- `sufficiency_score`
- `coverage`
- `main_limits`
- `minimum_next_data_needed`

## 行为模式判断规则

- 先判定消息量、时间跨度、说话人数量、文本/语音/图片缺失比例。
- 样本很短、语音未转写、只有单方记录时，结论降为低置信度。

## RAG 论文证据

### Evidence 1
- paper: 2026 Group Communication in Work-related Instant Messaging (IM): Request Strategies Among Adult Malay Speakers of English
- level: A_direct_chat_evidence
- doi: https://doi.org/10.17576/3l-2026-3201-20

### Evidence 2
- paper: 2026 Effects of Framing and Identity Cues in Science Communication With and About AI
- level: A_direct_chat_evidence
- doi: https://doi.org/10.17645/mac.11350

### Evidence 3
- paper: 2026 Enabling Sensitive Conversations with Consent Boundaries: Moa, a Platform for Discussing PhD Advising Relationships
- level: B_transferable_conversation_evidence

### Evidence 4
- paper: 2026 Group Communication in Work-related Instant Messaging (IM): Request Strategies Among Adult Malay Speakers of English
- level: A_direct_chat_evidence
- doi: https://doi.org/10.17576/3l-2026-3201-20

### Evidence 5
- paper: 2025 NaturalTurn: a method to segment speech into psychologically meaningful conversational turns
- level: B_transferable_conversation_evidence
- doi: https://doi.org/10.1038/s41598-025-24381-1
