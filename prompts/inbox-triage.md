# Inbox Triage Prompt

Process all unprocessed material in `inbox/`.

For each item:

1. Identify type: screenshot, chart, handwritten note, PDF, PPT, CSV, text, or other.
2. Preserve the original file.
3. Extract objective content first.
4. Clearly separate transcription from interpretation.
5. Identify relevant instrument, date, timeframe, strategy, market regime, and source when visible.
6. Search existing `knowledge/` and `strategies/` before creating a new file.
7. Update an existing topic when it is the same knowledge unit.
8. Create a new lowercase-hyphenated topic only when needed.
9. Preserve page/slide/image references.
10. Mark uncertain OCR/visual interpretation explicitly instead of guessing.
11. List contradictions with existing knowledge.
12. Suggest, but do not automatically promote, candidates for `LEARNINGS.md` or `decisions.md`.

Return a processing report containing:

- source file
- extracted facts
- interpretation
- destination file(s)
- contradictions
- unresolved questions
- promotion candidates
