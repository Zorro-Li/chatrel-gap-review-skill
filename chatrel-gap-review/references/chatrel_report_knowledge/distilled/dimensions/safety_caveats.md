# 安全边界与不确定性 / `safety_caveats`

- latest_status: 未覆盖
- audit_reason: `inbox_empty`
- evaluation_question: 哪些判断需要降级为低置信度？

## 应补进报告的判断点

- `sample_size_limit`
- `missing_voice_transcripts`
- `missing_context`
- `single_sided_data`
- `sparse_periods`

## 输出字段

- `confidence_penalties`
- `unsafe_claims_to_avoid`
- `next_data_needed`

## 行为模式判断规则

- 把频率类指标、内容类指标和时间趋势拆开判断。
- 每个判断都需要聊天记录证据、论文证据和置信度说明。

## RAG 论文证据

### Evidence 1
- paper: 2026 The Effects of Chatbot Characteristics on Satisfaction and Continuance Intention: The Moderating Role of the Need for Human Interaction
- level: A_direct_chat_evidence
- doi: https://doi.org/10.3390/jtaer21040122

### Evidence 2
- paper: 2026 Group Communication in Work-related Instant Messaging (IM): Request Strategies Among Adult Malay Speakers of English
- level: A_direct_chat_evidence
- doi: https://doi.org/10.17576/3l-2026-3201-20

### Evidence 3
- paper: 2026 Effects of Framing and Identity Cues in Science Communication With and About AI
- level: A_direct_chat_evidence
- doi: https://doi.org/10.17645/mac.11350

### Evidence 4
- paper: 2026 Enabling Sensitive Conversations with Consent Boundaries: Moa, a Platform for Discussing PhD Advising Relationships
- level: B_transferable_conversation_evidence

### Evidence 5
- paper: 2026 Group Communication in Work-related Instant Messaging (IM): Request Strategies Among Adult Malay Speakers of English
- level: A_direct_chat_evidence
- doi: https://doi.org/10.17576/3l-2026-3201-20
