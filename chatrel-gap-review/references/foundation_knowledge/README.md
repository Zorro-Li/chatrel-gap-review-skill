# Foundation Knowledge

This package is the public foundation layer behind the chat-relationship workflow.

It provides:

- `dyadic_taxonomy.json`: relationship domains and model dimensions.
- `dyadic_papers_manifest.json`: a sanitized paper registry for the broader dyadic psychology library.

The manifest keeps metadata that is useful for open reuse:

- title
- year
- DOI
- relationship domains
- signal families
- evidence and source metadata

The manifest leaves local-only fields outside the public package:

- local PDF paths
- local note paths
- local retrieval indexes
- full-text retrieval chunks
- machine-specific run traces

This layer is useful when you want the broad theory base behind the chat-specific retrieval system.
