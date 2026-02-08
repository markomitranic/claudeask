# claudeask

A simple CLI utility to quickly clone/update GitHub repositories and open them in a `claude` (Claude Code) instance for AI-powered exploration and questioning.

## Features

- **Quick Access**: Provide a repo name (`owner/repo`) or a full GitHub URL.
- **Smart Storage**: Repos are kept in `~/.claudeask/repos/` to avoid redundant clones.
- **Auto-Update**: Automatically runs `git pull` if the repo is already present locally.
- **Immediate Action**: Opens the repository in `claude` (Claude Code) as soon as it's ready.

## Installation

1. **Clone the repository** (or create the directory and download the script):
2. **Make the script executable**:
   ```bash
   chmod +x claudeask
   ```

3. **Symlink it to your path** for global access:
   ```bash
   sudo ln -s "$PWD/claudeask" /usr/local/bin/claudeask
   ```

## Usage

```bash
# Using shorthand (owner/repo)
claudeask elixir-lang/elixir

# Using a full URL
claudeask https://github.com/facebook/react.git

# Or just place any folder into ~/.claudeask/repos/ (top-level only)
# Running with no arguments will ask you to choose from local folders
claudeask
```

## How it works

The script clones repositories into `~/.claudeask/repos/` using just the repository name as the folder. For example, `claudeask owner/repo` will result in `~/.claudeask/repos/repo`. Only top-level folders are recognized. If the directory already exists, it performs a `git pull` before launching the `claude` agent.

## License

FOSS (MIT or similar). Feel free to use and improve!
