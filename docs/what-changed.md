# What changed — full provision-by-provision diff

> **Not yet active.** This page becomes the authority on what moved — tracing every tracked provision
> **Commission proposal → latest Council text → EP position** — once a co-legislator produces a text.
> As of 10 June 2026 only the Commission proposal (COM(2026) 504) exists, so there is nothing to diff.

When the first Council compromise text (a new ST number) or EP draft report lands:

1. Transcribe it into [`extracts/`](../extracts/) (the `transcribe-council-extract` skill), one file
   per slice in [`tracker.yaml`](../tracker.yaml) `extract_slices`.
2. Add one row per tracked provision here and in [`data/positions.csv`](../data/positions.csv), with
   deep links into the operative extracts (`extracts/...md#anchor`). Because this file **repeals
   Regulation (EU) 2023/1781**, rows should state the 2023-Act baseline AND the proposal separately
   (never fold a carried-over 2023 feature into the "proposal" cell) — the correlation table in
   Annex VII of COM(2026) 504 is the mapping aid.
3. Promote a headline subset to `STATUS.md`'s "What changed in the latest text vs earlier reporting"
   section (format: [`reporting-standard.md`](reporting-standard.md)).

Until then, the baseline is the transcribed Commission operative text in
[`extracts/commission/`](../extracts/commission/) (anchors `article-N`), with analysis in
[`provisions/`](provisions/).
