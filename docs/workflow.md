# Org-to-Markdown Workflow

## Preparation

1. Confirm source inventory in `docs/source-index.md`.
2. Ensure original files exist under `original/` with read-only copies.

## Conversion Loop (per file)

1. **Normalize name**
   - Identify tool from original filename.
   - Target Markdown filename: `<tool>_shortcuts.md` (e.g., `zoom_shortcuts.md`).
2. **Run conversion**
   - Prefer `pandoc -f org -t gfm --wrap=none original/<file>.org -o tmp.md`.
   - Capture command and options in the progress tracker.
3. **Post-process**
   - Apply shortcut glyph normalization (`⇧⌥⌃⌘` order).
   - Split combined rows into individual entries (`Shortcut`/`Shortcut (Text)`/`Action`/`Notes`).
   - Drop Org-only spacer rows.
   - Whenever information or formatting is lost, append a Markdown note on the next line outside any table:  
     `> TODO: repair info lost in org->md translation - <description>` or  
     `> TODO: repair formatting lost in org->md translation - <description>`.
4. **Structure to template**
   - Wrap content using the layout defined in `docs/structure-analysis.md`.
   - Insert `Legend`, `See Also`, and metadata bullet list.
   - Replace `/` separators with ` OR ` when multiple shortcuts map to the same action.
5. **Fidelity check**
   - Compare sections, row counts, and links using criteria in `docs/fidelity-metrics.md`.
   - Record status (`Accurate`, `Close`, `Missing`). Rectify issues before proceeding.
6. **Finalize file**
   - Populate both glyph and Apple-style textual columns for each shortcut.
   - Save Markdown under `notes/<tool>_shortcuts.md` (create `notes/` if desired).
   - Add cross-links to related Markdown files.

## Batch Steps

1. Update progress tracker after each file (copy command, status, open issues).
2. Aggregate gap analysis notes to refine conversion commands.
3. When all notes reach “Accurate” or acceptable “Close,” remove timestamp suffixes by renaming final Markdown files to `<tool>_shortcuts.md`.
4. Announce the selected conversion tool in chat and wait for user confirmation before running any conversion commands.

## Post-Conversion

- Maintain a summary table of fidelity outcomes for future comparisons.
- Keep original Org files untouched inside `original/` for auditing.

