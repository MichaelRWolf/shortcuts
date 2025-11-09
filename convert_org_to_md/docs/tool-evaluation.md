# Org → Markdown Conversion Tools

| Tool                                | Approach                                                            | Strengths                                                                     | Known Gaps                                                                                              | Notes                                                              |
|-------------------------------------|---------------------------------------------------------------------|-------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------|
| `pandoc`                            | CLI converter supporting Org as input and multiple Markdown flavors | Mature, scriptable, table handling generally solid, preserves metadata blocks | Requires tuning for custom tables, may flatten nested headings, needs `--wrap=none` to avoid hard wraps | Default choice; test with each note to measure fidelity.           |
| `python-orgparse` + custom renderer | Parse Org AST in Python and emit Markdown                           | Full control over rendering decisions, can build custom table/legend handling | Requires implementation effort, limited community support for Markdown output                           | Good fallback when `pandoc` output diverges from desired template. |
| `go-org` CLI (`go-org convert`)     | Go-based Org parser with Markdown output                            | Fast, standalone binary, good heading support                                 | Limited styling control, mixed reports on table fidelity                                                | Consider only if `pandoc` fails and Python approach is too heavy.  |

## Recommendations

1. Start with `pandoc` (`pandoc -f org -t gfm --wrap=none source.org -o output.md`) and measure results against fidelity criteria.
2. If specific sections require custom shaping (e.g., multi-table merges), supplement with a Python post-processor rather than abandoning `pandoc`.
3. Keep notes on command-line flags per file in the progress tracker to ensure reproducibility.
