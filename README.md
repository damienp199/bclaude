# bclaude

A minimal TUI workspace launcher for [Claude Code](https://docs.anthropic.com/en/docs/claude-code).

Switch between projects instantly. No config files to edit — everything happens from the menu.

## Install

```sh
curl -fsSL https://raw.githubusercontent.com/damienp199/bclaude/main/install.sh | sh
```

Requires [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) installed.

## Usage

```sh
bclaude
```

| Key | Action |
|-----|--------|
| `↑` `↓` / `j` `k` | Navigate |
| `Enter` | Open workspace in Claude Code |
| `a` | Add a workspace |
| `s` | Remove a workspace |
| `d` | Set as default |
| `q` | Quit |

### Set default from CLI

```sh
bclaude --default /path/to/project
```

## How it works

- Workspaces are stored in `~/.config/bclaude/workspaces` (one path per line)
- Selecting a workspace `cd`s into it and launches `claude`
- No dependencies beyond `zsh` and `claude`

## Uninstall

```sh
rm ~/.local/bin/bclaude
rm -rf ~/.config/bclaude
```
