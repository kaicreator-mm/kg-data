# Five-lane autonomous book knowledge scheduling

Coordinator: https://github.com/kaicreator-mm/parts-system/issues/60

## Work allocation
All five independent hourly automations may inspect the current Drive Books root and archived-PDF folder, but only one is allowed to **write** a given book.

Every book is assigned by the exact stable Google Drive fileId, never by mutable filename, folder path or list index.

`lane = FNV1a32(ASCII/UTF-8(fileId)) % 5`, where FNV-1a starts at unsigned 32-bit offset basis 2166136261, for each byte XORs the byte and then unsigned-multiplies by prime 16777619 modulo 2^32. Lanes are 0, 1, 2, 3, 4. The book `1-XMC-sjwyrpWuWn1BJPpirxDEo8LZJvv` is lane **2** (hash 3184636382).

Each worker advances **up to eight eligible distinct books per invocation** if resources permit, prioritizing an actual nonempty knowledge chunk for a partially processed book over adding thin TOC-only skeletons to eight books. Eight is a ceiling, not a completion expectation or service-level guarantee.

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
