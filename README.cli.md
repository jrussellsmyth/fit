# @jrussellsmyth/fit-cli

A CLI tool for autonomous agent and CI pipeline management of an [Obsidian](https://obsidian.md) vault, built on top of [fit](https://github.com/joshuakto/fit).

> **Note:** This is a fork of [joshuakto/fit](https://github.com/joshuakto/fit) extended with a CLI interface. A [pull request](https://github.com/joshuakto/fit/pull/217) has been submitted to the upstream project. Once the upstream maintainer publishes the CLI officially, consider migrating to their package.

## What is FIT?

[FIT (File gIT)](https://obsidian.md/plugins?id=fit) syncs your Obsidian vault across mobile and desktop devices using GitHub as a backend. The CLI exposes this functionality outside of the Obsidian app environment, enabling:

- Automation scripts
- CI/CD pipelines
- Autonomous agent workflows (e.g. AI agents reading/writing vault notes)

## Installation

```bash
npm install -g @jrussellsmyth/fit-cli
```

### Usage

```bash
# Show help
fit-cli help

# Check pending changes (dry-run, machine-readable)
fit-cli status --json

# Sync vault with remote
fit-li sync
```

### Configuration

Options can be supplied as flags, environment variables, or a JSON config file (all three can be combined; flags take highest priority).

| Flag | Environment variable | Description |
|---|---|---|
| `--vault <path>` | `FIT_VAULT` | Path to the Obsidian vault directory |
| `--pat <token>` | `FIT_PAT` | GitHub personal access token |
| `--owner <owner>` | `FIT_OWNER` | GitHub repository owner |
| `--repo <repo>` | `FIT_REPO` | GitHub repository name |
| `--branch <branch>` | `FIT_BRANCH` | Branch to sync (default: `main`) |
| `--device <name>` | `FIT_DEVICE` | Device name used in commit messages |
| `--config <path>` | `FIT_CONFIG` | Path to a JSON config file |
| `--state <path>` | _(none)_ | Path to state file (default: `<vault>/.fit-state.json`) |
| `--json` | _(none)_ | Output results as JSON |
| `--verbose` | _(none)_ | Enable verbose logging to stderr |

**Config file** (`~/.fit-cli.json` by default):

```json
{
  "vaultPath": "/path/to/vault",
  "pat": "ghp_...",
  "owner": "username",
  "repo": "vault-repo",
  "branch": "main",
  "deviceName": "my-agent"
}
```

### Sync behaviour

`fit-cli` uses the same sync engine as the Obsidian plugin — conflict detection, `_fit/` staging, and protected path rules all behave identically. State (SHA caches) is persisted to `<vault>/.fit-state.json` by default so that incremental syncs are efficient.


## Links

- Fork source: https://github.com/jrussellsmyth/fit/tree/add-cli
- Upstream project: https://github.com/joshuakto/fit
- Issues: https://github.com/jrussellsmyth/fit/issues
