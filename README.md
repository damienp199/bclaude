# CLAUDE BOOT

A minimal TUI workspace launcher for [Claude Code](https://docs.anthropic.com/en/docs/claude-code).

Save your most-used project folders and launch Claude Code in one keystroke — no more `cd`-ing around every time. Recently used Claude projects are also shown automatically.

![screenshot](screenshot.png)

## Install

```sh
curl -fsSL https://raw.githubusercontent.com/damienp199/bclaude/main/install.sh | sh
```

Requires [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) installed.

Make sure `~/.local/bin` is in your PATH. Add this to your `~/.zshrc` (or `~/.bashrc`) if needed:

```sh
export PATH="$HOME/.local/bin:$PATH"
```

## Usage

```sh
bclaude
# or shorter:
bcl
```

| Key | Action |
|-----|--------|
| `↑` `↓` / `j` `k` | Navigate |
| `Enter` | Open workspace in Claude Code |
| `a` | Add a workspace (or pin a recent) |
| `s` | Remove a workspace |
| `d` | Set as default |
| `q` | Quit |

### Recents

The menu automatically shows up to 5 recently used Claude Code projects below your pinned workspaces. These are detected from `~/.claude/projects/` and sorted by last use. Directories that no longer exist or are already pinned are excluded.

Press `a` on a recent to pin it to your workspaces, or `d` to set it as default.

### Add a workspace

Press `a` in the menu, then type the full path to your project folder (e.g. `/Users/me/projects/my-app`). The folder must already exist.

You can also add workspaces manually by appending a path to `~/.config/bclaude/workspaces` (one path per line):

```sh
echo "/path/to/project" >> ~/.config/bclaude/workspaces
```

### Set default from CLI

```sh
bclaude --default /path/to/project
```

## How it works

- Workspaces are stored in `~/.config/bclaude/workspaces` (one path per line)
- Recent projects are read from `~/.claude/projects/` (created by Claude Code itself)
- Selecting a workspace or recent `cd`s into it and launches `claude`
- No dependencies beyond `zsh` and `claude`

## Uninstall

```sh
rm ~/.local/bin/bclaude ~/.local/bin/bcl
rm -rf ~/.config/bclaude
```
