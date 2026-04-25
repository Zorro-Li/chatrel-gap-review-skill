# Chatrel Report Gap Audit

- run_dir: `redacted_public_snapshot`
- report_count: 2
- covered: 15
- weak: 0
- missing: 0
- rag_targets: conflict_repair, power_role, emotion_affect, relationship_context, social_support

## Reports

- Report file names redacted for public release.

## Dimension Coverage

### 数据充分性 / `data_sufficiency`

- status: 已覆盖
- reason: `covered_with_evidence`
- keyword_score: 31
- evidence_score: 3
- top_hits: 置信度(12), 消息量(7), 图片(5), 数据充分性(4), 数据充分(4), 时间跨度(4), conversation(2), jsonl(2)
- next_action: 保留当前结构，后续只补最新证据。

### 关系类型与场景 / `relationship_context`

- status: 已覆盖
- reason: `covered_with_evidence`
- keyword_score: 17
- evidence_score: 3
- top_hits: 关系类型(5), 朋友(5), 场景(3), conversation(2), context(2), type(2)
- next_action: 保留当前结构，后续只补最新证据。

### 关系强度 / `tie_strength`

- status: 已覆盖
- reason: `covered_with_evidence`
- keyword_score: 29
- evidence_score: 5
- top_hits: 发起(13), 连接(9), 关系强度(7), 微信(6), communication(4), conversation(2), reciprocity(2), WeChat(2)
- next_action: 保留当前结构，后续只补最新证据。

### 互惠与投入平衡 / `reciprocity_balance`

- status: 已覆盖
- reason: `covered_with_evidence`
- keyword_score: 29
- evidence_score: 4
- top_hits: 互惠(9), 微信(6), communication(4), 互惠与投入平衡(4), 投入平衡(4), 不平衡(4), 消息占比(3), reciprocity(2)
- next_action: 保留当前结构，后续只补最新证据。

### 回复节奏与可获得性 / `response_dynamics`

- status: 已覆盖
- reason: `covered_with_evidence`
- keyword_score: 34
- evidence_score: 5
- top_hits: 回复(24), 沉默(8), 可获得性(7), 回复节奏与可获得性(4), 回复速度(4), 轮次(4), NaturalTurn(3), 延迟(3)
- next_action: 保留当前结构，后续只补最新证据。

### 话题承接与对话连续性 / `topic_continuity`

- status: 已覆盖
- reason: `covered_with_evidence`
- keyword_score: 31
- evidence_score: 4
- top_hits: 话题(12), 承接(8), backchannel(5), 接住(5), 连续性(3), 追问(3), conversation(2), alignment(2)
- next_action: 保留当前结构，后续只补最新证据。

### 语言风格匹配 / `lexical_alignment`

- status: 已覆盖
- reason: `covered_with_evidence`
- keyword_score: 28
- evidence_score: 3
- top_hits: 表情(24), 语言风格(9), 语言风格匹配(7), 风格匹配(7), 语气(4), ConversationAlign(2), alignment(2), lexical(2)
- next_action: 保留当前结构，后续只补最新证据。

### 情绪状态与情绪同步 / `emotion_affect`

- status: 已覆盖
- reason: `covered_with_evidence`
- keyword_score: 13
- evidence_score: 3
- top_hits: 情绪(14), 负面(6), conversation(2), 情绪同步(2), 正面(1)
- next_action: 保留当前结构，后续只补最新证据。

### 支持、安慰与回应性 / `social_support`

- status: 已覆盖
- reason: `covered_with_evidence`
- keyword_score: 22
- evidence_score: 3
- top_hits: 支持(18), 安慰(8), 陪伴(5), communication(4), social(2), 回应性(2), 建议(2)
- next_action: 保留当前结构，后续只补最新证据。

### 融洽、信任与亲密 / `rapport_trust_intimacy`

- status: 已覆盖
- reason: `covered_with_evidence`
- keyword_score: 22
- evidence_score: 3
- top_hits: 亲密(34), communication(4), 自我披露(4), 信任(4), 融洽、信任与亲密(2), 玩笑(2), 融洽(2)
- next_action: 保留当前结构，后续只补最新证据。

### 权力、角色与主导结构 / `power_role`

- status: 已覆盖
- reason: `covered_with_evidence`
- keyword_score: 20
- evidence_score: 2
- top_hits: 解释(16), 权力(6), 角色(6), 道歉(5), 权力、角色与主导结构(2), 主导(2)
- next_action: 保留当前结构，后续只补最新证据。

### 冲突、破裂与修复 / `conflict_repair`

- status: 已覆盖
- reason: `covered_with_evidence`
- keyword_score: 19
- evidence_score: 2
- top_hits: 修复(16), 冲突(14), 破裂(6), 道歉(5), 冲突、破裂与修复(2), 恢复(1)
- next_action: 保留当前结构，后续只补最新证据。

### 媒介使用模式 / `modality_media`

- status: 已覆盖
- reason: `covered_with_evidence`
- keyword_score: 26
- evidence_score: 3
- top_hits: 语音(23), 媒介(9), 表情包(7), 文字(7), 图片(5), communication(4), for(2)
- next_action: 保留当前结构，后续只补最新证据。

### 时间趋势与关系阶段 / `temporal_trajectory`

- status: 已覆盖
- reason: `covered_with_evidence`
- keyword_score: 28
- evidence_score: 3
- top_hits: 趋势(7), 后期(6), 阶段(6), communication(4), 最近(4), 升温(3), alignment(2), 冷却(1)
- next_action: 保留当前结构，后续只补最新证据。

### 安全边界与不确定性 / `safety_caveats`

- status: 已覆盖
- reason: `covered_with_evidence`
- keyword_score: 20
- evidence_score: 4
- top_hits: 风险(8), 边界(6), conversation(2), transcripts(2), context(2), 低置信度(2), to(2), 安全(2)
- next_action: 保留当前结构，后续只补最新证据。
