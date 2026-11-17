# Five-lane autonomous book knowledge scheduling

Coordinator: https://github.com/kaicreator-mm/parts-system/issues/60

## Work allocation
All five independent hourly automations may inspect the current Drive Books root and archived-PDF folder, but only one is allowed to **write** a given book.

Every book is assigned by the exact stable Google Drive fileId, never by mutable filename, folder path or list index.

`lane = FNV1a32(ASCII/UTF-8(fileId)) % 5`, where FNV-1a starts at unsigned 32-bit offset basis 2166136261, for each byte XORs the byte and then unsigned-multiplies by prime 16777619 modulo 2^32. Lanes are 0, 1, 2, 3, 4. The book `1-XMC-sjwyrpWuWn1BJPpirxDEo8LZJvv` is lane **2** (hash 3184636382).

**R12 long-batch goal (2026-11-17):** Each Lane aims for **5 genuinely generation-complete books per invocation**, and may touch at most **15 distinct books** if capacity permits. Books are processed **sequentially within a Lane**, in order of readiness: work deeply through all available chapters and complete self-QA and canonical/derived text commits and fetch-file readback, then proceed to the next book. Other Lanes may run concurrently. This is a **target, not a guaranteed throughput or adjustable task runtime**; the platform may interrupt an invocation before a single whole book is complete, in which case persist validated chapter-level checkpoints and resume next run. Do not stop early after a token sample, and do not count merely touched books as completed. Qualification still requires independent review.

## Data and ledger layout
- `books/<drive-fileId>/M##/knowledge-candidates.rN.yaml`: primary original hypotheses.
- `books/<drive-fileId>/M##/knowledge.rN.md`: full professional explanations and counterexamples.
- `books/<drive-fileId>/M##/knowledge-candidates.rN.jsonld`: derived semantic graph.
- `books/<drive-fileId>/M##/nodes.rN.csv`, `edges.rN.csv`: derived projections.
- `books/<drive-fileId>/M##/schema.linkml.rN.yaml`: schema as necessary.
- `registry/lanes/lane-N.yaml`: per-lane cursor, version, inventory and receipts, if used.
- `integrated/`: cross-book fusion candidates with conflicts, never destructive rewriting of source-book graphs.

Direct GitHub connector text writes only. Do not upload a local file path through Google Drive; no Google Docs bridge needed for GitHub text outputs. No raw PDFs, extensive original TOCs, copyrighted figures/tables or textbook body passages belong in this **public** repository. Google Drive remains the original-book input/source and private retained historical archive.

GitHub contents API writes must check existence and exact blob SHA before replacing an existing path. Workers write only within their own book files / individual cursor; avoid shared mutable registry across lanes. A repository conflict or rate limit should become a retryable checkpoint, not a false success. Confirm GitHub readback after committing and report exact file URLs plus commit SHA in #60.

## Qualification
`MODEL_GENERATED_UNVERIFIED` until independent review and evidence. `TOC_DIRECT` proves headings, not technical assertions. Zero formal N3/Gate/SAP/Review qualification without real separate evidence. Only count real meaningful records with stable IDs, applicability, assumptions, mechanism, counterexamples, QA and state. A successful file transport does not qualify the facts.


## Full-book completion and metrics
- `books_touched`: a book with genuine work performed; not identical to `books_completed`.
- `books_completed`: all readable TOC topics have been examined for useful, nonduplicate original knowledge or explicitly documented `EMPTY_WITH_REASON`, a full scoped self-QA pass has been recorded, all required native UTF-8 artifacts exist in GitHub and are fetch-verified, and the book is marked `GENERATION_COMPLETE_REVIEW_PENDING`. Merely generating YAML/JSON-LD/CSV, 4–5 provisional facts, or one chapter is **not** completion.
- If TOC cannot be read, use `OCR_TOC_NEEDED`/`BLOCKED`, not `BOOK_COMPLETE`; title-only provisional knowledge must not inflate completed count.
- Persist per-book and per-chapter coverage + exact resume cursors with genuine commit SHAs. Any source-body claim remains unverified absent rights and primary evidence. No formal qualification without independent review.
- Process up to 15 distinct books per Lane per invocation, but reserve enough execution budget to checkpoint verified data. Hard runtime/task deadlines are outside prompt control.
