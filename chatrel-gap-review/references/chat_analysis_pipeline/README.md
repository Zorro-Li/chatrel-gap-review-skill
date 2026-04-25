# Chat Analysis Pipeline

This package contains the public method knowledge for turning chat records into relationship reports.

It covers three parts:

- `chat_record_analysis_blueprint.md`: feature-engineering blueprint from message rows to dyadic signals.
- `chat_record_knowledge_base_overview.md` and `chat_record_papers_manifest.json`: the chat-specific retrieval layer.
- `rag_system/`: evaluation dimensions, output schema, retrieval policy, and prompt templates for relationship assessment.

It also includes `video_scripts/`, which explains the same analysis logic in creator-friendly script form.

This package focuses on public method knowledge:

- what to observe
- how to structure evidence
- how to retrieve support
- how to format a report

This package leaves private and heavier artifacts outside the repository:

- raw chat exports
- local media inventory
- SQLite databases
- chunk stores
- evidence bundles
- local parsing and run traces
