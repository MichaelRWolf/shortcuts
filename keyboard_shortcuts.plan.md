# Plan Mode Instructions

1. Read this plan file.
2. Execute the tasks and considerations listed below.

# Shortcut Note Consolidation Plan

## Tasks

1. Inventory Org Sources

- Locate `/Users/michael/repos/notes/*shortcut*` files, record path, size, modified timestamp.
- Capture list inside repo (e.g., `docs/source-index.md`) for tracking.

2. Stage Source Copies

- Create `original/` (or similar) in `shortcuts` repo.
- Copy each identified `.org` file and recursively include any referenced assets or linked files, without deleting originals.

3. Analyze Structures

- Review sampled `.org` files to document current section/table patterns.
- Draft recommended Markdown note layout and standard table column order (e.g., `shortcut` then `description`).
- Analyze existing table usage to standardize column order (e.g., `key`/`description`) and outline organizational template.

4. Evaluate Conversion Approach

- Survey practical conversion tools (excluding Emacs/org/roam) such as `pandoc` or custom scripts.
- Note pros/cons and likely fidelity gaps.

5. Translation Fidelity Criteria

- Define metrics for “accurate / close / missing” categories using structural checks (section counts, table rows, metadata).

6. Develop Translation Workflow

- Outline step-by-step process for `.org` → `.md` conversion, including manual review for flagged cases.
- Recommend naming convention `<tool>_shortcuts.md`.
- Include plan for removing org-mode timestamps from filenames post-conversion.

7. Progress Tracking Setup

- Build checklist (Markdown table) capturing each file’s status across phases: copied, analyzed, converted, verified, renamed.

## Next Considerations

1. Confirm target directory names (`original/`, `docs/`, etc.); ad lib additional directories if needed.
2. Plan to analyze all shortcut `.org` files (<10) before standardizing structure.
3. Defer defining “close” fidelity threshold until after gap analysis.
4. Identify any automation tooling requirements (language/runtime) for custom scripts.
5. Plan final verification and summary report of translation fidelity categories.

