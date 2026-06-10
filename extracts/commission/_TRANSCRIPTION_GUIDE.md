# Transcription guide for Commission base-text extracts

Internal standard for every file in `extracts/commission/`. The goal: a faithful, diffable
transcription of the **operative text of the Commission proposal COM(2026) 504 final** (CELEX
52026PC0504), structured to line up with the Council extracts in `../council/` so that
`git diff --no-index ../commission/COM-2026-504_<slice>.md ../council/ST-<nnnn>-<yyyy>_<slice>.md`
shows exactly what a compromise text changes.

## Source of truth
The committed proposal under `../../sources/commission/COM-2026-504_proposal_2026-06-03.pdf` (the
authoritative text) is what you transcribe from — it matches the EUR-Lex version
(CELEX **52026PC0504**). The annexes (Annexes I–VII, incl. **Annex VII**, the correlation table to
Regulation (EU) 2023/1781) are `../../sources/commission/COM-2026-504_annexes-1-7_2026-06-03.pdf`.
Transcribe from the committed source on disk; never from memory or a web summary.

## What "transcribe" means for the base text
The Commission proposal is the **original**: there is nothing to "consolidate". Chips Act 2.0
replaces Regulation (EU) 2023/1781 wholesale (repeal in Art 58, transitional provisions in Art 59,
correlation table in Annex VII) — the proposal is enacted as standalone text, so there are no
amending instructions: transcribe the articles **verbatim as enacted text**. Where an article
interfaces with existing law (the repealed 2023 Chips Act, the Chips Joint Undertaking / Horizon
Europe / Digital Europe basic acts, the public-procurement directives), flag it with a `▸` note
linking the relevant `../../docs/instruments/related-instruments.md` row, and — once Council
versions exist — what the Council did to that point, linking the matching `../council/` anchor.

## Faithfulness rules
- Preserve the proposal's own article/paragraph numbering and Chapter/Section structure.
- Preserve bracketed placeholders exactly — e.g. `[OP: insert date for four years after date of
  entry into force]` — that is *not* `[illegible]`; it is undecided in the source.
- Typos in the source are reproduced and flagged `[sic]`.
- Never silently normalise: cross-references, defined terms and capitalisation stay as printed.

## Structure & anchors
- One file per slice in [`../../tracker.yaml`](../../tracker.yaml) `extract_slices`, named
  `COM-2026-504_<slice>.md`. The slices follow the proposal's own Chapter/Section groupings
  (Ch I Arts 1–2; Ch II Arts 3–12; Ch III s1 Arts 13–20, s2 Arts 21–25, s3 Arts 26–29,
  s4 Arts 30–32; Ch IV Arts 33–43; Ch V Arts 44–49; Ch VI Arts 50–54; Ch VII+VIII Arts 55–60;
  recitals). Confirm the groupings against the text while transcribing and adjust
  `extract_slices` if the proposal's own structure differs.
- Anchor every article heading with `<a id="article-N"></a>` (exactly `article-N` — no topic suffix;
  recitals use `recital-N`), so future Council versions can reuse the anchors and cross-version
  diffs line up.
- Recitals file: curated subset (the contested/structural ones). State that it is a curated subset,
  not the full preamble.

## Header block
Open with a blockquote: source = **COM(2026) 504 final**, 3 June 2026, interinstitutional file
**2026/0139 (COD)**, "working transcription, not an official text", "verify against the authoritative
document (EUR-Lex CELEX 52026PC0504)", and "See `../../NOTICE`."

## Links
Relative links only. Link the sibling extracts, the matching `../council/` anchors (once they exist),
and the relevant `../../docs/provisions/*` / `../../docs/instruments/*` pages. Verify every internal
link/anchor resolves (`python3 ../../.claude/skills/transcribe-council-extract/linkcheck.py ../..`)
before finishing.
