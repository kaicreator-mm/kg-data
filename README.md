# kg-data

Automotive and other open-domain knowledge graph **candidate data**. This repository stores machine-readable, independently generated knowledge artifacts and their provenance, not book PDFs or copied textbook pages.

## Source and provenance

- Source document inventory and PDFs remain in private Google Drive Books.
- Task coordinator: https://github.com/kaicreator-mm/parts-system/issues/60
- Generated candidates must be tagged `MODEL_GENERATED_UNVERIFIED` until independently reviewed against genuine evidence.
- A table of contents establishes topic coverage only; it is **not** primary evidence of technical claims.
- No source PDFs, lengthy book text, tables, or copyrighted figures should be committed.

## Layout

- `schemas/`: LinkML models and controlled vocabularies.
- `books/<drive-file-id>/`: immutable-by-version, book-specific knowledge candidates and source metadata.
- `registry/lanes/`: independent scheduled worker cursors, one file per lane.
- `integrated/`: future cross-book alignments, conflicts and provenance preserving graphs.

Canonical book content: YAML + LinkML schema. Render Markdown, JSON-LD and CSV as derived formats from the canonical graph. Keep original model knowledge clearly separate from verified source claims. Every scheduled worker belongs to one deterministic shard (`fileId -> FNV-1a -> mod 5`) and writes only to its own book/cursor paths.

## Status
`INITIALIZED` — text-write connectivity probe only; no book extraction or independent verification is implied.
