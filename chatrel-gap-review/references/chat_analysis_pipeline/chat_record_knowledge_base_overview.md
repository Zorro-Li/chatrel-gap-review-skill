# Chat Record Psychology Knowledge Base

This is the chat-record-focused retrieval layer for WeChat-style dyadic analysis.

## Counts
- source metadata files scanned: 269
- selected papers: 61
- retrieval chunks: 2336
- This public package omits local chat-record counts and media inventory.

## Evidence Levels
- A_direct_chat_evidence: 37
- B_transferable_conversation_evidence: 24

## Feature Tags
- emotion_affect: 33
- social_support: 28
- rapport_trust: 25
- power_role: 23
- tie_strength: 9
- response_dynamics: 6
- conflict_repair: 3
- lexical_alignment: 3

## Default Query

```bash
"$HUMANOS_ROOT/Knowledge of 心理学/.venv/bin/python" "$HUMANOS_ROOT/Knowledge of 心理学/chat_record_knowledge_base/search_chat_kb.py" "亲子同步"
"$HUMANOS_ROOT/Knowledge of 心理学/.venv/bin/python" "$HUMANOS_ROOT/Knowledge of 心理学/chat_record_knowledge_base/search_chat_kb.py" "微信 关系强度" --feature tie_strength
"$HUMANOS_ROOT/Knowledge of 心理学/.venv/bin/python" "$HUMANOS_ROOT/Knowledge of 心理学/chat_record_knowledge_base/search_chat_kb.py" "治疗联盟" --evidence A,B,C
```

## WeChat Schema Observed

A WeChat-style JSONL export can expose the fields needed for relationship analysis:

- `sender`
- `timestamp`
- `type`
- `content`
- `platformMessageId`

The public package focuses on schema and retrieval logic. Local conversation inventories and media counts stay private.

## Precision Controls

- `--evidence A,B` is the default and keeps direct chat evidence plus transferable conversation evidence.
- `--evidence A` keeps only papers directly about chat, messaging, text, WeChat, email, or CMC.
- `--feature tie_strength`, `--feature lexical_alignment`, `--feature social_support`, `--feature rapport_trust`, `--feature power_role`, `--feature conflict_repair`, `--feature response_dynamics`, `--feature emotion_affect` narrows retrieval to one modeling dimension.
