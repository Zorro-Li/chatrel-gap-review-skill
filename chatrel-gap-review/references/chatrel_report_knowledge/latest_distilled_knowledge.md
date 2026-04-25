# Chatrel Report Distilled Knowledge

Public redacted merge of `distilled/dimensions/*.md`.

<!-- source: distilled/dimensions/conflict_repair.md -->
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

<!-- source: distilled/dimensions/data_sufficiency.md -->
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

<!-- source: distilled/dimensions/emotion_affect.md -->
# 情绪状态与情绪同步 / `emotion_affect`

- latest_status: 已覆盖
- audit_reason: `covered_with_evidence`
- evaluation_question: 两个人的情绪表达如何互相影响？

## 应补进报告的判断点

- `positive_affect_rate`
- `negative_affect_rate`
- `emotion_shift`
- `emotion_contagion`
- `emotion_recovery_time`

## 输出字段

- `emotion_score`
- `dominant_affects`
- `synchrony_notes`
- `emotion_turning_points`

## 行为模式判断规则

- 把频率类指标、内容类指标和时间趋势拆开判断。
- 每个判断都需要聊天记录证据、论文证据和置信度说明。

## RAG 论文证据

### Evidence 1
- paper: 2026 Negative evaluation fear and sharing avoidance on WeChat Moments: exhaustion and face
- level: A_direct_chat_evidence
- doi: https://doi.org/10.3389/fpsyg.2026.1793555

### Evidence 2
- paper: 2026 Tied In on TikTok: Tie Strength and Emotional Dynamics in Algorithmic Communities
- level: B_transferable_conversation_evidence

### Evidence 3
- paper: 2026 VividListener: Expressive and Controllable Listener Dynamics Modeling for Multi-Modal Responsive Interaction
- level: B_transferable_conversation_evidence
- doi: https://doi.org/10.1609/aaai.v40i8.37567

### Evidence 4
- paper: 2026 VividListener: Expressive and Controllable Listener Dynamics Modeling for Multi-Modal Responsive Interaction
- level: B_transferable_conversation_evidence
- doi: https://doi.org/10.1609/aaai.v40i8.37567

### Evidence 5
- paper: 2026 VividListener: Expressive and Controllable Listener Dynamics Modeling for Multi-Modal Responsive Interaction
- level: B_transferable_conversation_evidence
- doi: https://doi.org/10.1609/aaai.v40i8.37567

<!-- source: distilled/dimensions/lexical_alignment.md -->
# 语言风格匹配 / `lexical_alignment`

- latest_status: 未覆盖
- audit_reason: `inbox_empty`
- evaluation_question: 两个人的表达方式是否出现靠近或单向适应？

## 应补进报告的判断点

- `shared_terms`
- `function_word_similarity`
- `emoji_similarity`
- `sentence_length_similarity`
- `style_shift_by_time`

## 输出字段

- `style_alignment_score`
- `mutual_alignment`
- `one_sided_adaptation`
- `style_change_points`

## 行为模式判断规则

- 观察词汇、表情、句长、功能词和口头禅是否随时间趋同。
- 区分双向靠近和单向适应，单向适应常指向投入或权力不平衡。

## RAG 论文证据

### Evidence 1
- paper: 2026 ConversationAlign: Open-source software for analyzing patterns of lexical use and alignment in conversation transcripts
- level: B_transferable_conversation_evidence
- doi: https://doi.org/10.3758/s13428-026-02954-w

### Evidence 2
- paper: 2026 Linguistic Accommodation Between Neurodivergent Communities on Reddit:A Communication Accommodation Theory Analysis of ADHD and Autism Groups
- level: A_direct_chat_evidence

### Evidence 3
- paper: 2026 ConversationAlign: Open-source software for analyzing patterns of lexical use and alignment in conversation transcripts
- level: B_transferable_conversation_evidence
- doi: https://doi.org/10.3758/s13428-026-02954-w

### Evidence 4
- paper: 2026 Linguistic Accommodation Between Neurodivergent Communities on Reddit:A Communication Accommodation Theory Analysis of ADHD and Autism Groups
- level: A_direct_chat_evidence

### Evidence 5
- paper: 2026 Linguistic Accommodation Between Neurodivergent Communities on Reddit:A Communication Accommodation Theory Analysis of ADHD and Autism Groups
- level: A_direct_chat_evidence

<!-- source: distilled/dimensions/modality_media.md -->
# 媒介使用模式 / `modality_media`

- latest_status: 未覆盖
- audit_reason: `inbox_empty`
- evaluation_question: 文字、语音、图片、表情在关系里承担什么功能？

## 应补进报告的判断点

- `text_ratio`
- `voice_ratio`
- `image_ratio`
- `emoji_ratio`
- `media_after_conflict`
- `voice_for_sensitive_topics`

## 输出字段

- `media_profile`
- `modality_asymmetry`
- `media_function_notes`

## 行为模式判断规则

- 把频率类指标、内容类指标和时间趋势拆开判断。
- 每个判断都需要聊天记录证据、论文证据和置信度说明。

## RAG 论文证据

### Evidence 1
- paper: 2026 Effects of Framing and Identity Cues in Science Communication With and About AI
- level: A_direct_chat_evidence
- doi: https://doi.org/10.17645/mac.11350

### Evidence 2
- paper: 2026 Enabling Sensitive Conversations with Consent Boundaries: Moa, a Platform for Discussing PhD Advising Relationships
- level: B_transferable_conversation_evidence

### Evidence 3
- paper: 2026 Group Communication in Work-related Instant Messaging (IM): Request Strategies Among Adult Malay Speakers of English
- level: A_direct_chat_evidence
- doi: https://doi.org/10.17576/3l-2026-3201-20

### Evidence 4
- paper: 2026 Communication Modality and Communication Satisfaction in Relationships
- level: B_transferable_conversation_evidence

### Evidence 5
- paper: 2026 Group Communication in Work-related Instant Messaging (IM): Request Strategies Among Adult Malay Speakers of English
- level: A_direct_chat_evidence
- doi: https://doi.org/10.17576/3l-2026-3201-20

<!-- source: distilled/dimensions/power_role.md -->
# 权力、角色与主导结构 / `power_role`

- latest_status: 已覆盖
- audit_reason: `covered_with_evidence`
- evaluation_question: 谁更常主导、要求、解释、配合或让步？

## 应补进报告的判断点

- `directive_rate`
- `explanation_rate`
- `apology_rate`
- `question_rate`
- `topic_control`
- `refusal_space`

## 输出字段

- `power_asymmetry_score`
- `dominance_markers`
- `compliance_markers`
- `role_pattern`

## 行为模式判断规则

- 统计请求、命令、解释、让步、道歉、拒绝和话题控制的方向。
- 主导结构要结合场景判断，例如客服、医患、师生天然存在角色差异。

## RAG 论文证据

### Evidence 1
- paper: 2026 Enabling Sensitive Conversations with Consent Boundaries: Moa, a Platform for Discussing PhD Advising Relationships
- level: B_transferable_conversation_evidence

### Evidence 2
- paper: 2026 THE INTELLIGENT SILENCE ARCHITECTURE - TISA
- level: A_direct_chat_evidence
- doi: https://doi.org/10.5281/zenodo.19430905

### Evidence 3
- paper: 2026 THE INTELLIGENT SILENCE ARCHITECTURE - TISA
- level: A_direct_chat_evidence
- doi: https://doi.org/10.5281/zenodo.19430906

### Evidence 4
- paper: 2026 Enabling Sensitive Conversations with Consent Boundaries: Moa, a Platform for Discussing PhD Advising Relationships
- level: B_transferable_conversation_evidence

### Evidence 5
- paper: 2026 The Effects of Chatbot Characteristics on Satisfaction and Continuance Intention: The Moderating Role of the Need for Human Interaction
- level: A_direct_chat_evidence
- doi: https://doi.org/10.3390/jtaer21040122

<!-- source: distilled/dimensions/rapport_trust_intimacy.md -->
# 融洽、信任与亲密 / `rapport_trust_intimacy`

- latest_status: 未覆盖
- audit_reason: `inbox_empty`
- evaluation_question: 两个人之间是否存在稳定的亲近和信任信号？

## 应补进报告的判断点

- `self_disclosure`
- `inside_jokes`
- `sensitive_topic_acceptance`
- `future_planning`
- `affection_terms`
- `trust_repair`

## 输出字段

- `rapport_score`
- `trust_markers`
- `intimacy_markers`
- `fragility_notes`

## 行为模式判断规则

- 把频率类指标、内容类指标和时间趋势拆开判断。
- 每个判断都需要聊天记录证据、论文证据和置信度说明。

## RAG 论文证据

### Evidence 1
- paper: 2026 The Effects of Chatbot Characteristics on Satisfaction and Continuance Intention: The Moderating Role of the Need for Human Interaction
- level: A_direct_chat_evidence
- doi: https://doi.org/10.3390/jtaer21040122

### Evidence 2
- paper: 2026 Effects of Framing and Identity Cues in Science Communication With and About AI
- level: A_direct_chat_evidence
- doi: https://doi.org/10.17645/mac.11350

### Evidence 3
- paper: 2026 A randomized factorial experiment to optimize the design of a culturally tailored breast cancer screening outreach chatbot intervention
- level: A_direct_chat_evidence
- doi: https://doi.org/10.3389/fdgth.2026.1720531

### Evidence 4
- paper: 2026 THE INTELLIGENT SILENCE ARCHITECTURE - TISA
- level: A_direct_chat_evidence
- doi: https://doi.org/10.5281/zenodo.19430905

### Evidence 5
- paper: 2026 THE INTELLIGENT SILENCE ARCHITECTURE - TISA
- level: A_direct_chat_evidence
- doi: https://doi.org/10.5281/zenodo.19430906

<!-- source: distilled/dimensions/reciprocity_balance.md -->
# 互惠与投入平衡 / `reciprocity_balance`

- latest_status: 未覆盖
- audit_reason: `inbox_empty`
- evaluation_question: 两个人的互动投入是否平衡？

## 应补进报告的判断点

- `message_share_by_speaker`
- `word_share_by_speaker`
- `initiation_share`
- `reply_share`
- `support_given_vs_received`

## 输出字段

- `balance_score`
- `dominant_speaker`
- `underresponsive_speaker`
- `asymmetry_notes`

## 行为模式判断规则

- 把频率类指标、内容类指标和时间趋势拆开判断。
- 每个判断都需要聊天记录证据、论文证据和置信度说明。

## RAG 论文证据

### Evidence 1
- paper: 2026 PuppetChat: Fostering Intimate Communication through Bidirectional Actions and Micronarratives
- level: A_direct_chat_evidence
- doi: https://doi.org/10.1145/3772318.3790685

### Evidence 2
- paper: 2026 PuppetChat: Fostering Intimate Communication through Bidirectional Actions and Micronarratives
- level: A_direct_chat_evidence
- doi: https://doi.org/10.1145/3772318.3790685

### Evidence 3
- paper: 2026 PuppetChat: Fostering Intimate Communication through Bidirectional Actions and Micronarratives
- level: A_direct_chat_evidence
- doi: https://doi.org/10.1145/3772318.3790685

### Evidence 4
- paper: 2026 PuppetChat: Fostering Intimate Communication through Bidirectional Actions and Micronarratives
- level: A_direct_chat_evidence
- doi: https://doi.org/10.1145/3772318.3790685

### Evidence 5
- paper: 2026 PuppetChat: Fostering Intimate Communication through Bidirectional Actions and Micronarratives
- level: A_direct_chat_evidence
- doi: https://doi.org/10.1145/3772318.3790685

<!-- source: distilled/dimensions/relationship_context.md -->
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

<!-- source: distilled/dimensions/response_dynamics.md -->
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

<!-- source: distilled/dimensions/safety_caveats.md -->
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

<!-- source: distilled/dimensions/social_support.md -->
# 支持、安慰与回应性 / `social_support`

- latest_status: 已覆盖
- audit_reason: `covered_with_evidence`
- evaluation_question: 一个人是否能在对方需要时提供支持？

## 应补进报告的判断点

- `validation_count`
- `reassurance_count`
- `advice_count`
- `practical_help_count`
- `support_timing`
- `support_received_response`

## 输出字段

- `support_score`
- `support_types`
- `support_balance`
- `missed_support_moments`

## 行为模式判断规则

- 把频率类指标、内容类指标和时间趋势拆开判断。
- 每个判断都需要聊天记录证据、论文证据和置信度说明。

## RAG 论文证据

### Evidence 1
- paper: 2026 PuppetChat: Fostering Intimate Communication through Bidirectional Actions and Micronarratives
- level: A_direct_chat_evidence
- doi: https://doi.org/10.1145/3772318.3790685

### Evidence 2
- paper: 2026 PuppetChat: Fostering Intimate Communication through Bidirectional Actions and Micronarratives
- level: A_direct_chat_evidence
- doi: https://doi.org/10.1145/3772318.3790685

### Evidence 3
- paper: 2026 PuppetChat: Fostering Intimate Communication through Bidirectional Actions and Micronarratives
- level: A_direct_chat_evidence
- doi: https://doi.org/10.1145/3772318.3790685

### Evidence 4
- paper: 2026 PuppetChat: Fostering Intimate Communication through Bidirectional Actions and Micronarratives
- level: A_direct_chat_evidence
- doi: https://doi.org/10.1145/3772318.3790685

### Evidence 5
- paper: 2010 The origins of 12-month attachment: A microanalysis of 4-month mother–infant interaction
- level: A_direct_chat_evidence
- doi: https://doi.org/10.1080/14616730903338985

<!-- source: distilled/dimensions/temporal_trajectory.md -->
# 时间趋势与关系阶段 / `temporal_trajectory`

- latest_status: 未覆盖
- audit_reason: `inbox_empty`
- evaluation_question: 这段关系随时间如何变化？

## 应补进报告的判断点

- `weekly_message_trend`
- `latency_trend`
- `support_trend`
- `conflict_trend`
- `alignment_trend`
- `change_points`

## 输出字段

- `stage_guess`
- `trend_summary`
- `change_points`
- `recent_direction`

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

<!-- source: distilled/dimensions/tie_strength.md -->
# 关系强度 / `tie_strength`

- latest_status: 未覆盖
- audit_reason: `inbox_empty`
- evaluation_question: 这段关系连接强度如何？

## 应补进报告的判断点

- `message_frequency`
- `initiation_frequency`
- `reciprocity`
- `conversation_density`
- `shared_topic_recurrence`

## 输出字段

- `tie_strength_score`
- `frequency_evidence`
- `reciprocity_evidence`
- `trajectory`

## 行为模式判断规则

- 把频率类指标、内容类指标和时间趋势拆开判断。
- 每个判断都需要聊天记录证据、论文证据和置信度说明。

## RAG 论文证据

### Evidence 1
- paper: 2026 PuppetChat: Fostering Intimate Communication through Bidirectional Actions and Micronarratives
- level: A_direct_chat_evidence
- doi: https://doi.org/10.1145/3772318.3790685

### Evidence 2
- paper: 2026 PuppetChat: Fostering Intimate Communication through Bidirectional Actions and Micronarratives
- level: A_direct_chat_evidence
- doi: https://doi.org/10.1145/3772318.3790685

### Evidence 3
- paper: 2026 PuppetChat: Fostering Intimate Communication through Bidirectional Actions and Micronarratives
- level: A_direct_chat_evidence
- doi: https://doi.org/10.1145/3772318.3790685

### Evidence 4
- paper: 2026 PuppetChat: Fostering Intimate Communication through Bidirectional Actions and Micronarratives
- level: A_direct_chat_evidence
- doi: https://doi.org/10.1145/3772318.3790685

### Evidence 5
- paper: 2026 How reciprocity, cohesion, and communication climate drive information sharing in WeChat-based e-commerce communities
- level: A_direct_chat_evidence
- doi: https://doi.org/10.1057/s41599-026-06947-0

<!-- source: distilled/dimensions/topic_continuity.md -->
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
