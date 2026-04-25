# Chat Record Analysis Blueprint

This blueprint maps WeChat-style exported records to evidence-backed relationship analysis features.

## Observed WeChat Input

Message rows expose:

- `sender`: speaker identity
- `timestamp`: message time
- `type`: message modality or platform message type
- `content`: text or media reference
- `platformMessageId`: stable message id

A reliable production setup benefits from richer text coverage, voice transcription, and optional image OCR or captioning.

## Analysis Pipeline

1. Normalize JSONL into message rows:
   - conversation_id
   - sender_id
   - timestamp
   - message_type
   - text
   - media_path
   - platform_message_id

2. Segment interactions:
   - same-day sessions
   - silence gaps such as 30 minutes, 6 hours, 24 hours
   - topic windows
   - conflict / repair windows

3. Compute speaker-level features:
   - message count share
   - word / character count share
   - initiation count
   - reply count
   - average response latency
   - median response latency
   - late reply rate
   - question rate
   - directive rate
   - self-disclosure rate
   - support / validation rate
   - conflict / repair marker rate

4. Compute dyadic features:
   - reciprocity of message volume
   - reciprocity of response speed
   - lexical alignment
   - emotional convergence / divergence
   - topic continuity
   - turn-taking balance
   - intimacy and self-disclosure trajectory
   - trust / rapport markers
   - power asymmetry markers
   - conflict rupture-repair trajectory
   - media modality balance

5. Retrieve evidence from the KB:
   - direct chat evidence: `A_direct_chat_evidence`
   - transferable conversation evidence: `B_transferable_conversation_evidence`
   - background relationship theory: `C_relationship_theory_background`

## Feature-To-Evidence Map

| Chat Feature | KB Feature Tag | Evidence Query |
| --- | --- | --- |
| response time, reply gaps, turn balance | `response_dynamics` | `回复速度 轮次` / `response latency turn-taking` |
| language style similarity | `lexical_alignment` | `语言风格匹配` / `language style matching` |
| sentiment and emotion shift | `emotion_affect` | `情绪 共情` / `emotion empathy` |
| reassurance, advice, validation | `social_support` | `支持 安慰` / `social support validation` |
| trust, closeness, rapport | `rapport_trust` | `信任 融洽` / `rapport trust` |
| directives, deference, dominance | `power_role` | `权力 角色` / `power role dominance` |
| criticism, avoidance, repair | `conflict_repair` | `冲突 修复` / `conflict repair` |
| reciprocity and frequency | `tie_strength` | `关系强度 互惠` / `tie strength reciprocity` |

## Recommended Default Retrieval

Use direct chat and transferable conversation evidence first:

```bash
"$HUMANOS_ROOT/Knowledge of 心理学/.venv/bin/python" "$HUMANOS_ROOT/Knowledge of 心理学/chat_record_knowledge_base/search_chat_kb.py" "微信 关系强度" --feature tie_strength
```

Use relationship theory when the chat-specific evidence is sparse:

```bash
"$HUMANOS_ROOT/Knowledge of 心理学/.venv/bin/python" "$HUMANOS_ROOT/Knowledge of 心理学/chat_record_knowledge_base/search_chat_kb.py" "亲子同步" --evidence A,B,C
```

## Practical Scoring Output

Each pair should produce:

- relationship_type_guess
- confidence
- evidence_used
- observed_features
- speaker_asymmetry
- rapport_score
- trust_score
- support_score
- conflict_score
- tie_strength_score
- communication_style_match_score
- trajectory_by_time
- caveats

## Safety And Product Rule

Chat analysis should produce probabilistic relationship signals with cited evidence. It should avoid deterministic claims about private motives, mental illness, deception, or intent from sparse records.
