# 冲突、破裂与修复 / `conflict_repair`

- latest_status: 已覆盖
- audit_reason: `covered_with_evidence`
- evaluation_question: 冲突之后，两个人如何恢复沟通？

## 应补进报告的判断点

- `conflict_marker_count`
- `withdrawal_count`
- `repair_attempt_count`
- `apology_count`
- `repair_latency`
- `post_conflict_recovery`

## 输出字段

- `conflict_score`
- `repair_score`
- `rupture_windows`
- `repair_quality`

## 行为模式判断规则

- 先定位冲突窗口，再看谁发起修复、修复延迟、道歉质量和复聊质量。
- 冲突强度和修复质量分开判断，避免把吵架次数直接等同于关系差。

## RAG 论文证据

### Evidence 1
- paper: 2026 Dyadic Emotional Dialogue Among Early Childhood Educators: Exploring an Understudied Aspect of Educational Climate
- level: B_transferable_conversation_evidence
- doi: https://doi.org/10.20944/preprints202602.0838.v1

### Evidence 2
- paper: 2010 The origins of 12-month attachment: A microanalysis of 4-month mother–infant interaction
- level: A_direct_chat_evidence
- doi: https://doi.org/10.1080/14616730903338985

### Evidence 3
- paper: 2026 From imperial examination to digital soloing: why Generation Z resist mandatory cooperation in Chinese higher education
- level: A_direct_chat_evidence
- doi: https://doi.org/10.3389/fpsyg.2026.1800462

### Evidence 4
- paper: 2026 Dyadic Emotional Dialogue Among Early Childhood Educators: Exploring an Understudied Aspect of Educational Climate
- level: B_transferable_conversation_evidence
- doi: https://doi.org/10.20944/preprints202602.0838.v1

### Evidence 5
- paper: 2026 From imperial examination to digital soloing: why Generation Z resist mandatory cooperation in Chinese higher education
- level: A_direct_chat_evidence
- doi: https://doi.org/10.3389/fpsyg.2026.1800462
