# @jrussellsmyth/fit-cli

A CLI tool for autonomous agent and CI pipeline management of an [Obsidian](https://obsidian.md) vault, built on top of [fit](https://github.com/joshuakto/fit).

> **Note:** This is a fork of [joshuakto/fit](https://github.com/joshuakto/fit) extended with a CLI interface. A [pull request](https://github.com/joshuakto/fit/pull/217) has been submitted to the upstream project. Once the upstream maintainer publishes the CLI officially, consider migrating to their package.

## Installation

```bash
npm install -g @jrussellsmyth/fit-cli
```

## Usage

```bash
fit-cli --help
```

## What is fit?

FIT (File gIT) syncs your Obsidian vault across mobile and desktop devices using GitHub as a backend. The CLI exposes this functionality outside of the Obsidian app environment, enabling:

- Automation scripts
- CI/CD pipelines
- Autonomous agent workflows (e.g. AI agents reading/writing vault notes)

## Configuration

The CLI reads the same GitHub token and repository settings used by the Obsidian plugin. Set the following environment variables or pass them as arguments:

| Variable | Description |
|---|---|
| `GITHUB_TOKEN` | A GitHub personal access token with `repo` scope |
| `GITHUB_REPO` | The target repository in `owner/repo` format |

## Links

- Fork source: https://github.com/jrussellsmyth/fit/tree/add-cli
- Upstream project: https://github.com/joshuakto/fit
- Issues: https://github.com/jrussellsmyth/fit/issues
