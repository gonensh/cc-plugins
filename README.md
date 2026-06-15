# safe-scripts

A Claude Code plugin that builds a personal library of pre-approved safe scripts to eliminate repetitive permission dialogs.

## How it works

When Claude runs a Bash command that needs approval, the plugin intercepts and offers to save a generalized, parameterized version as a "safe script." Once saved, that script is permanently pre-approved — no more dialogs for that class of command.

## Requirements

- Claude Code with plugin support
- `jq` ≥ 1.5 (`brew install jq` / `apt install jq`)
- bash ≥ 3.2

## Installation

```bash
claude plugin install <repo-url>
```

## Configuration

By default, scripts are saved to `~/.claude/safe-scripts/`.

To override per-project, create `.claude/safe-scripts-config.json`:

```json
{
  "safe_scripts_dir": "./.claude/safe-scripts"
}
```

A project-local directory can be committed to git for team-shared script libraries.

## Supported interpreters

bash, python3, node, perl, go (via bash wrapper), npx/ts-node (via bash wrapper), and inline heredoc scripts for any of the above.

## License

MIT
