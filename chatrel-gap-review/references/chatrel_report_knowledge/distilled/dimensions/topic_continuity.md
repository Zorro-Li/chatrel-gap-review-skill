# 话题承接与对话连续性 / `topic_continuity`

- latest_status: 未覆盖
- audit_reason: `inbox_empty`
- evaluation_question: 两个人是否能延续彼此的话题？

## 应补进报告的判断点

- `topic_shift_rate`
- `follow_up_rate`
- `question_answer_pairs`
- `ignored_topic_count`
- `topic_repair_count`

## 输出字段

- `continuity_score`
- `ignored_topics`
- `follow_up_examples`
- `topic_shift_pattern`

## 行为模式判断规则

- 把频率类指标、内容类指标和时间趋势拆开判断。
- 每个判断都需要聊天记录证据、论文证据和置信度说明。

## RAG 论文证据

### Evidence 1
- paper: 2026 THE INTELLIGENT SILENCE ARCHITECTURE - TISA
- level: A_direct_chat_evidence
- doi: https://doi.org/10.5281/zenodo.19430906

### Evidence 2
- paper: 2026 THE INTELLIGENT SILENCE ARCHITECTURE - TISA
- level: A_direct_chat_evidence
- doi: https://doi.org/10.5281/zenodo.19430905

### Evidence 3
- paper: 2026 THE INTELLIGENT SILENCE ARCHITECTURE - TISA
- level: A_direct_chat_evidence
- doi: https://doi.org/10.5281/zenodo.19430906

### Evidence 4
- paper: 2026 Aligning Backchannel and Dialogue Context Representations via Contrastive LLM Fine-Tuning
- level: B_transferable_conversation_evidence

### Evidence 5
- paper: 2026 Aligning Backchannel and Dialogue Context Representations via Contrastive LLM Fine-Tuning
- level: B_transferable_conversation_evidence
