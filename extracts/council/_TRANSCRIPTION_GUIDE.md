# Transcription guide for Council compromise-text extracts

Internal standard for every file in `extracts/council/`. The goal: each version's extract is a
faithful, diffable transcription of that version's operative text, structured identically across
versions so `git diff` between them is meaningful. (No compromise text exists yet on this file —
this guide is ready for the first one.)

## Source of truth
The committed PDF under `sources/council/` for that document. Transcribe from the PDF on disk.
Never transcribe from memory, a web summary, or another version's text.

## Consolidated reading
Each compromise text shows changes *against the Commission proposal* (additions bold/bold-underline,
deletions strikethrough). Transcribe the **consolidated** result — i.e. apply the changes and write
the resulting operative text. Do NOT reproduce the strikethrough/bold markup itself; render the
resulting text.

## Faithfulness rules (hard)
- Transcribe operative wording verbatim from the PDF. This is primary legal text, not prose to
  paraphrase. Do not summarise an article and call it a transcription.
- If a passage is illegible/uncertain in the PDF, mark it `[illegible in source]` — never guess.
- Use the document's OWN article and recital numbering — numbering can shift between versions. Do not
  copy a later version's numbering onto an earlier text.
- Where the version deletes a whole provision, mark it `[DELETED in ST <nnnn>/26]` with a one-line note.
- Flag the salient change for each article with a `▸` change-note (what moved vs the Commission
  proposal and, where known, vs the previous compromise text).

## Structure & anchors
- One file per slice in [`../../tracker.yaml`](../../tracker.yaml) `extract_slices`, named
  `ST-<nnnn>-<yyyy>_<slice>.md`, mirroring the `../commission/COM-2026-504_*` baseline set. Reuse the
  baseline's heading text and `<a id="...">` anchors wherever an article corresponds, so cross-links
  and diffs line up — BUT only for articles that exist in this version. New articles get their own
  heading + anchor following the same pattern (exactly `article-N`; recitals `recital-N`).
- If a version genuinely lacks a slice, still create the file and state that the section is
  absent/unchanged in that version, with a one-line explanation.
- Recitals file: curated subset (the contested/structural ones). State that it is a curated subset,
  not the full preamble.

## Header block (every file)
Open with a blockquote: source doc number + LIMITE status + date + the working-party meeting it
served + interinstitutional file 2026/0139 (COD) + "working transcription, not an official text" +
"verify against the authoritative document. See `../../NOTICE`."

## Cross-links
Relative links only. Link sibling extracts and the relevant `docs/provisions/*` /
`docs/instruments/*` pages. Verify every internal link/anchor resolves before finishing.
