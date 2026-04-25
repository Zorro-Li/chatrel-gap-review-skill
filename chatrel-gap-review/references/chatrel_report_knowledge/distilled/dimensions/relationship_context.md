# 关系类型与场景 / `relationship_context`

- latest_status: 已覆盖
- audit_reason: `covered_with_evidence`
- evaluation_question: 两个人更像哪类关系场景？

## 应补进报告的判断点

- `address_terms`
- `topic_domains`
- `role_terms`
- `intimacy_terms`
- `task_terms`

## 输出字段

- `relationship_type_guess`
- `confidence`
- `supporting_markers`
- `alternative_types`

## 行为模式判断规则

- 把频率类指标、内容类指标和时间趋势拆开判断。
- 每个判断都需要聊天记录证据、论文证据和置信度说明。

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
- paper: 2026 Group Communication in Work-related Instant Messaging (IM): Request Strategies Among Adult Malay Speakers of English
- level: A_direct_chat_evidence
- doi: https://doi.org/10.17576/3l-2026-3201-20

### Evidence 4
- paper: 2026 Aligning Backchannel and Dialogue Context Representations via Contrastive LLM Fine-Tuning
- level: B_transferable_conversation_evidence

### Evidence 5
- paper: 2026 The AI Amplifier Effect: Defining Human-AI Intimacy and Romantic Relationships with Conversational AI
- level: B_transferable_conversation_evidence
