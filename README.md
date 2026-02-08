# claudeask

A simple CLI utility to quickly clone/update GitHub repositories and open them in a `claude` (Claude Code) instance for AI-powered exploration and questioning.

## Features

- **Quick Access**: Provide a repo name (`owner/repo`) or a full GitHub URL.
- **Smart Storage**: Repos are kept in `~/Sites/claudeask/repos/` to avoid redundant clones.
- **Auto-Update**: Automatically runs `git pull` if the repo is already present locally.
- **Immediate Action**: Opens the repository in `claude` (Claude Code) as soon as it's ready.

## Installation

1. **Clone the repository** (or create the directory and download the script):
   ```bash
   mkdir -p ~/Sites
   cd ~/Sites
   git clone https://github.com/markomitranic/claudeask.git
   cd claudeask
   ```

2. **Make the script executable**:
   ```bash
   chmod +x claudeask
   ```

3. **Symlink it to your path** for global access:
   ```bash
   sudo ln -s "$PWD/claudeask" /usr/local/bin/claudeask
   ```

   *Note: Using `$PWD` ensures the symlink points to the absolute path of your current directory.*

## Usage

```bash
# Using shorthand (owner/repo)
claudeask telenor/dk-s11002-telenor-website

# Using a full URL
claudeask https://github.com/facebook/react.git
```

## How it works

The script clones repositories into a structured directory at `~/Sites/claudeask/repos/`. For example, `claudeask owner/repo` will result in a local path of `~/Sites/claudeask/repos/owner/repo`. If the directory exists, it performs a `git pull` before launching the `claude` agent.

## License

FOSS (MIT or similar). Feel free to use and improve!
