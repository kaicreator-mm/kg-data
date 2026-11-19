# Integrated automotive-books coverage report (round 1, 2026-11-20)

- Inventory snapshot: 765 PDFs (root 764 + archive 1), 765 unique fileIds — INVENTORY_COMPLETE_AT_SNAPSHOT, not KG complete.
- BookGraphs started this round: 6; all BOOK_IN_PROGRESS (chapter-scoped), review_status=GENERATED_REVIEW_PENDING.

## book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC
- claims=97 entities=64 edges=32 evidence=61 graph_sha256=b89a9a2d30868f8c…
- pages 11/300 processed; blocked/pending 289; assets 10/11; sections closed 1/1.

## book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y
- claims=93 entities=71 edges=69 evidence=14 graph_sha256=a1da6126451ef4ac…
- pages 8/206 processed; blocked/pending 198; assets 8/8; sections closed 1/1.

## book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8
- claims=32 entities=28 edges=10 evidence=14 graph_sha256=e3079bc7d503709a…
- pages 5/53 processed; blocked/pending 48; assets 5/10; sections closed 1/1.

## book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E
- claims=102 entities=39 edges=32 evidence=37 graph_sha256=3e11c8bd4590eded…
- pages 9/259 processed; blocked/pending 250; assets 5/5; sections closed 1/1.

## book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1
- claims=28 entities=24 edges=17 evidence=21 graph_sha256=3b510d7aaaa131a1…
- pages 10/109 processed; blocked/pending 99; assets 2/2; sections closed 1/1.

## book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_
- claims=73 entities=44 edges=17 evidence=26 graph_sha256=2749ba5fd4a93a5b…
- pages 10/299 processed; blocked/pending 289; assets 13/13; sections closed 1/1.

## Metrics (reference 05 §6)

- inventory_pdf_total=765; book_graphs_started=6; books_page_complete=0; books_scoped_accepted=0 (independent review NOT_RUN)
- claims_source_located=0 (all EXTRACTED_UNCHECKED until source-check); claims_self_checked=0; claims_independently_accepted=0
- cross_book_entities_aligned=0 verified / 7 candidates; conflicting_claim_sets=0 (scan pending); merge_queue_open=0
- model_calls logged in telemetry/cost-events.jsonl; provider token accounting unknown -> total_cost_usd=null

## Residual risks
- All graphs are chapter-scoped partials; silent-skip is impossible by construction (every page registered PENDING or processed) but completeness requires full-page processing.
- Independent Exact-SHA review NOT_RUN: review trigger words delivered on parts-system#62.
