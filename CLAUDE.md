# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

`claudeask` is a single-file Bash CLI tool that clones/updates GitHub repositories into `~/.claudeask/repos/` and opens them in Claude Code (`claude .`). The entire tool is the `claudeask` executable script at the repo root.

## Architecture

- **`claudeask`** — The sole source file. A Bash script that handles three modes:
  1. **No arguments**: lists repos in `~/.claudeask/repos/` via `fzf` for interactive selection
  2. **Full URL** (`https://` or `git@`): extracts repo name, clones or pulls, launches Claude Code
  3. **Shorthand** (`owner/repo`): constructs GitHub URL, clones or pulls, launches Claude Code
- Repos are stored flat in `~/.claudeask/repos/<repo-name>` (basename only, no owner nesting).

## Development

There is no build step, no tests, and no dependencies beyond `git`, `fzf`, and `claude`. To test changes, run the script directly:

```bash
./claudeask                          # interactive picker mode
./claudeask owner/repo               # clone/pull + launch
./claudeask https://github.com/o/r   # full URL mode
```

Install locally by symlinking:

```bash
chmod +x claudeask
sudo ln -s "$PWD/claudeask" /usr/local/bin/claudeask
```
