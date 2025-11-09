# Org Structure Analysis

## Source Summaries

- `20250726T183423--cursor-keyboard-shortcuts__cursor_shortcut.org`
  - Metadata only; no body content beyond the Denote header.
  - Treat as placeholder pointing at richer Cursor shortcut data.
- `20250726T184111--keyboard-shortcut-keytops__shortcut.org`
  - Provides modifier legend and repeated nomenclature.
  - Contains a Markdown snippet describing how to seed new files.
- `20250726T184231--cursor-keyboard-shortcuts__shortcut.org`
  - Main content is a multi-section Org table combining Cursor-specific actions and general VS Code commands.
  - Table uses separator rows and blank spacer rows that do not map cleanly to Markdown tables.
- `20250726T184428--keyboard-shortcuts-many-applications__shortcut.org`
  - High-level outline with references to other notes.
  - Includes unresolved `file:` links into the deprecated org-roam store.
- `20250726T185310--zoom-keyboard-shortcuts__short_zoom.org`
  - Two-column Org table mixing Zoom actions and keystrokes.
  - Several typos (“Tobble”, “participante”) and inconsistent modifier spelling.

## Proposed Markdown Layout

1. H1 title: `<Tool> Keyboard Shortcuts`.
2. Optional metadata block (tool tags, source references) captured as a short unordered list.
3. Standard sections:
   - `Legend` (imported once from the shared keytop definitions).
   - `Shortcuts` (primary table).
   - Optional `See Also` section linking to related files.
4. Shared template snippet for new tools:

```markdown
# <Tool> Keyboard Shortcuts

- Source: `<original .org filename or external link>`
- Updated: `YYYY-MM-DD`
- Tags: `shortcut`, `<tool>`

## Legend

Refer to `keyboard_shortcut_keytops.md`.

## Shortcuts

| Shortcut | Shortcut (Text) | Action | Notes |
| -------- | ---------------- | ------ | ----- |
```

## Table Standards

- Column order: `Shortcut`, `Shortcut (Text)`, `Action`, `Notes`.
- Represent modifier sequences using macOS glyphs (`⌘`, `⌥`, `⌃`, `⇧`) followed by the key (e.g., `⌘C`, `⇧⌘P`).
- Provide a plain-text counterpart using Apple-style key names (e.g., `Command-C`, `Shift-Command-P`).
- Use ` OR ` between alternatives (e.g., `⌘\ OR ⌘|`) and parenthetical text for additional context when necessary.
- Keep one shortcut per row; split compound Org rows (such as “Next (Previous) 25 participante”) into individual records with explicit labels.
- Reserve the `Notes` column for mnemonics, platform qualifiers, or clarifications (“Zoom menu”, “macOS only”).
- When conversion drops content or formatting, add a blockquoted TODO note immediately after the affected element (and outside any table) using the pattern `> TODO: repair info lost in org->md translation - …` or `> TODO: repair formatting lost in org->md translation - …`.

## Outstanding Items

- Fix typos during translation (“Toggle”, “Participant”).
- Resolve or document any `file:` links that remain unreachable.

