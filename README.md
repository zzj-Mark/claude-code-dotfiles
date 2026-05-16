# Claude Code Dotfiles

This repository contains my [Claude Code](https://claude.ai/claude-code) configuration files, managed by [Chezmoi](https://chezmoi.io/).

## What's Included

- `~/.claude/settings.json` - Claude Code global settings
- `~/.claude/settings.local.json` - Local environment settings (encrypted)
- `oh-my-claudecode` plugin configuration

## Setup on a New Machine

### 1. Install Chezmoi

```bash
# Using curl
sh -c "$(curl -fsSL https://chezmoi.io/get)" -- -b ~/.local/bin

# Or using brew
brew install chezmoi
```

### 2. Apply Dotfiles

```bash
# Initialize and apply
chezmoi init zzj-Mark/claude-code-dotfiles
chezmoi apply
```

### 3. Configure API Token

After applying, edit `~/.claude/settings.json` and add your actual API token:

```json
{
  "env": {
    "ANTHROPIC_AUTH_TOKEN": "your_actual_token_here"
  }
}
```

## Ignored Files

The following files are NOT synced (see `.chezmoiignore`):

- `sessions/` - Session history
- `history.jsonl` - Command history
- `file-history/` - File history
- `shell-snapshots/` - Shell snapshots

## Updating

To pull changes from this repo:

```bash
chezmoi update
```

To add new files:

```bash
chezmoi add ~/.claude/new_file.conf
chezmoi apply
cd ~/.local/share/chezmoi
git add . && git commit -m "Add new_file.conf" && git push
```

---

**Managed with [Chezmoi](https://chezmoi.io/)**
