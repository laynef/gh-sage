# gh-sage

> Sage AI for GitHub CLI — generate PRs, review code, write commit messages, and run agentic tasks, all from the terminal.

## Install

```bash
gh extension install sageworksai/gh-sage
```

Requires: [sage CLI](https://sageworksai.com) — `pip install sage-ai-cli && sage login`

## Commands

| Command | Description |
|---|---|
| `gh sage pr [base]` | Generate a PR description (default base: `main`) |
| `gh sage review [pr-num]` | AI code review of a pull request |
| `gh sage commit` | Generate a commit message from staged diff |
| `gh sage explain <file\|pr>` | Explain a file or PR diff |
| `gh sage issue <description>` | Draft a GitHub issue |
| `gh sage run <task>` | Run full agentic task in current repo |
| `gh sage models` | List available AI models |

## Examples

```bash
# Generate PR description for current branch vs main
gh sage pr

# Review PR #42
gh sage review 42

# Auto-generate commit message (runs sage on staged diff)
git add .
gh sage commit

# Explain what a file does
gh sage explain src/auth.py

# Explain what a PR changed
gh sage explain 123

# Run a coding task in the repo
gh sage run "add error handling to all API endpoints"

# Override model for this command
SAGE_MODEL=cloud:mistral-small gh sage commit
```

## Configuration

Set a default model via the `SAGE_MODEL` environment variable or by configuring your sage default:

```bash
sage config set default_model cloud:qwen3-coder
```

## License

MIT — [sageworksai.com](https://sageworksai.com)
