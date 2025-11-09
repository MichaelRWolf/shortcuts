# Shortcuts

A collection of useful shortcuts and productivity tools.

## Description

This repository contains various shortcuts, scripts, and productivity tools to help streamline common tasks and workflows.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Feel free to contribute by adding your own shortcuts and tools!

## Development Setup

### Install pre-commit

This repository relies on [pre-commit](https://pre-commit.com/) to format Markdown tables automatically before each commit.

1. Install the `pre-commit` package (choose one of the following):
   - `pip install pre-commit`
   - `brew install pre-commit`
   - `pipx install pre-commit`
2. Install project dependencies (once per clone):

   ```bash
   npm install
   ```

3. From the repository root, run:

   ```bash
   pre-commit install
   ```

After installation, the hooks will align GitHub-flavoured Markdown tables and run `markdownlint --fix` on every staged Markdown file. If a file cannot be reformatted or linted, the hook will fail loudly so you can address the issue before the commit completes.

### Running Hooks Manually

You can invoke the hooks without creating a commit:

- Run against staged files:

  ```bash
  pre-commit run
  ```

- Run against every tracked file:

  ```bash
  pre-commit run --all-files
  ```

Both commands apply the same formatting and linting rules as the commit-time hooks. To target just the Markdown linter, run:

```bash
pre-commit run markdownlint
```
