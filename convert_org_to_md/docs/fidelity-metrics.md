# Translation Fidelity Criteria

## Categories

- **Accurate**: Markdown output matches Org source semantically and structurally. Section counts, table rows, and key metadata align 1:1. Legend glyphs and shortcut columns retain ordering and spelling.
- **Close**: Minor manual follow-up required (e.g., fix italic vs. bold, adjust table alignment) but no data loss. Differences are cosmetic or formatting-only.
- **Missing**: Data dropped, mis-ordered, or meaningfully altered (e.g., truncated table rows, lost references, incorrect shortcut glyphs).

## Checks

1. **Section Structure**
   - Compare heading hierarchy (number of `##` sections, order of subsections).
   - Flag when Markdown omits a section present in Org.
2. **Table Integrity**
   - Ensure column counts stay consistent (`Shortcut`, `Shortcut (Text)`, `Action`, `Notes`).
   - Verify row counts match source tables after splitting combined rows and duplicating values into both shortcut representations.
3. **Shortcut Normalization**
   - Confirm modifiers use glyphs (`⌘`, `⌥`, `⌃`, `⇧`) and sequence order `⇧` → `⌥` → `⌃` → `⌘`.
   - Detect plain-text sequences (`Command + Shift + A`) that still need normalization into Apple-style text (`Shift-Command-A`).
4. **Link Preservation**
   - Check that `See also` links and references survive conversion.
   - Record unresolved `file:` links for documentation.
5. **Metadata Capture**
   - Validate that titles, tags, and dates are either retained or deliberately mapped to new front matter.
6. **Loss Annotations**
   - Ensure every known loss of content or formatting is followed by a blockquoted TODO note using the prescribed phrasing.

## Automation Hooks

- Simple Python script to diff section headers and row counts between `.org` and converted `.md`.
- Unit tests (e.g., pytest) verifying normalized shortcut glyphs using regex patterns.
- JSON summary per file capturing counts (`{"sections":3,"rows":25,"links":4}`) to track drift over iterations.
