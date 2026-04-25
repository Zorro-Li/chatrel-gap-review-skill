# RAG System For WeChat Relationship Analysis

This RAG layer turns the chat-record psychology knowledge base into an evidence-backed assessment system.

## Corpus

- Source DB: `../chat_record_knowledge_base/chat_records_psychology.sqlite`
- Papers: 61 chat-record-focused papers
- Retrieval chunks: 2336
- Evidence levels:
  - `A_direct_chat_evidence`: direct chat / messaging / CMC / WeChat / email evidence
  - `B_transferable_conversation_evidence`: transferable conversation or dialogue transcript evidence
  - `C_relationship_theory_background`: relationship theory background

## RAG Flow

1. Normalize WeChat records into a message table.
2. Compute observable chat features.
3. Retrieve evidence by assessment dimension.
4. Generate a probabilistic relationship report.
5. Cite evidence chunks for every major interpretation.

## Core Files

- `config/evaluation_dimensions.json`: 15 evaluation dimensions
- `config/rag_retrieval_plan.json`: retrieval policy and ranking logic
- `config/output_schema.json`: final report schema
- `prompts/system_prompt.md`: RAG system prompt
- `prompts/analysis_prompt.md`: analysis prompt template
- `scripts/rag_retrieve.py`: evidence retriever
- `evidence_bundle.json`: generated evidence bundle
- `evidence_bundle.md`: readable evidence bundle

## Generate Evidence Bundle

```bash
"Knowledge of 心理学/.venv/bin/python" "Knowledge of 心理学/rag_system/scripts/rag_retrieve.py" --context "微信聊天记录 两个人关系分析" --evidence A,B --top-k 5
```

Use `--evidence A,B,C` when the chat data is sparse or when the analysis needs relationship-theory background.

## Assessment Dimensions

The system evaluates:

1. data sufficiency
2. relationship context
3. tie strength
4. reciprocity and balance
5. response dynamics
6. topic continuity
7. lexical alignment
8. emotion and affect
9. social support
10. rapport, trust, intimacy
11. power and role asymmetry
12. conflict, rupture, repair
13. modality and media use
14. temporal trajectory
15. safety caveats

