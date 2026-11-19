# Integrated automotive-books coverage report (round 1, 2026-11-20)

- Inventory snapshot: 765 PDFs (root 764 + archive 1), 765 unique fileIds — INVENTORY_COMPLETE_AT_SNAPSHOT, not KG complete.
- BookGraphs started this round: 13; all BOOK_IN_PROGRESS (chapter-scoped), review_status=GENERATED_REVIEW_PENDING.

## book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC
- claims=257 entities=116 edges=60 evidence=134 graph_sha256=d3c0945817eb91a2…
- pages 22/300 processed; blocked/pending 278; assets 26/28; sections closed 2/2.

## book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y
- claims=93 entities=71 edges=69 evidence=14 graph_sha256=a1da6126451ef4ac…
- pages 8/206 processed; blocked/pending 198; assets 8/8; sections closed 1/1.

## book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8
- claims=32 entities=28 edges=10 evidence=14 graph_sha256=e3079bc7d503709a…
- pages 5/53 processed; blocked/pending 48; assets 5/10; sections closed 1/1.

## book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E
- claims=102 entities=39 edges=32 evidence=37 graph_sha256=3e11c8bd4590eded…
- pages 9/259 processed; blocked/pending 250; assets 5/5; sections closed 1/1.

## book:1-XMC-sjwyrpWuWn1BJPpirxDEo8LZJvv
- claims=136 entities=36 edges=61 evidence=69 graph_sha256=8b3a1b4a5d802125…
- pages 16/404 processed; blocked/pending 388; assets 13/13; sections closed 1/1.

## book:1A0TcG3A9Z2Uq8wPTTJz6v1pqaQufcf_B
- claims=37 entities=20 edges=9 evidence=22 graph_sha256=f947ab44329cd1e7…
- pages 14/278 processed; blocked/pending 264; assets 19/19; sections closed 1/1.

## book:1E6xA3XFUnSpJjULUyabJ-dFF57buxZ-v
- claims=83 entities=48 edges=40 evidence=32 graph_sha256=bf08a2a36db10671…
- pages 10/303 processed; blocked/pending 293; assets 13/13; sections closed 1/1.

## book:1Ds7ED02SAYic6aZm5nRpIb0KZX8C8EIz
- claims=140 entities=52 edges=33 evidence=71 graph_sha256=925a6dab85847ef4…
- pages 16/277 processed; blocked/pending 261; assets 12/12; sections closed 1/1.

## book:1wtxnL2CnwTklePxerazLQICo9-lrxzj3
- claims=36 entities=26 edges=17 evidence=11 graph_sha256=f77785651b441127…
- pages 7/306 processed; blocked/pending 299; assets 6/7; sections closed 1/1.

## book:1yarCr2eoTyjTUYIXzN3z2zZpGCxMnlTY
- claims=168 entities=48 edges=85 evidence=60 graph_sha256=83047473c7714f5a…
- pages 11/404 processed; blocked/pending 393; assets 4/4; sections closed 1/1.

## book:197fgux-sQ8YPhRkInFu0ojbah88W_plL
- claims=156 entities=94 edges=106 evidence=44 graph_sha256=57b4975d7e399769…
- pages 7/329 processed; blocked/pending 322; assets 8/9; sections closed 1/1.

## book:1ZiUmJc4H0A4-NTido4rikoOmWnZV1Czd
- claims=62 entities=28 edges=15 evidence=30 graph_sha256=73136120d683c740…
- pages 12/425 processed; blocked/pending 413; assets 14/14; sections closed 1/1.

## book:1QyGCHW6NxdfqsNl-Z9E3H6JyNxiLlKfe
- claims=116 entities=62 edges=89 evidence=21 graph_sha256=9a402c5974b41c73…
- pages 9/130 processed; blocked/pending 121; assets 16/16; sections closed 1/1.

## Metrics (reference 05 §6)

- inventory_pdf_total=765; book_graphs_started=13; books_page_complete=0; books_scoped_accepted=0 (independent review NOT_RUN)
- claims_source_located=0 (all EXTRACTED_UNCHECKED until source-check); claims_self_checked=0; claims_independently_accepted=0
- cross_book_entities_aligned=0 verified / 27 candidates; conflicting_claim_sets=0 (scan pending); merge_queue_open=0
- model_calls logged in telemetry/cost-events.jsonl; provider token accounting unknown -> total_cost_usd=null

## Residual risks
- All graphs are chapter-scoped partials; silent-skip is impossible by construction (every page registered PENDING or processed) but completeness requires full-page processing.
- Independent Exact-SHA review NOT_RUN: review trigger words delivered on parts-system#62.
