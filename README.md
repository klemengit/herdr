# herdr config

Personal [herdr](https://herdr.dev) configuration, living in `~/.config/herdr`.
It starts from the Omarchy seed in `/usr/share/omarchy/config/herdr/config.toml`
and keeps that file's aim: reproduce the tmux setup it replaced, so the muscle
memory carries over.

The tmux vocabulary maps onto herdr like this:

| tmux    | herdr     |
| ------- | --------- |
| session | workspace |
| window  | tab       |
| pane    | pane      |

Only `config.toml` is tracked. The rest of the directory is runtime state —
logs, sockets, `session.json` — and is ignored.

## Shortcuts

Prefix is `Ctrl+Space`. `prefix+h` below means press the prefix, release, then
the key.

### Panes

| Keys                       | Action                     |
| -------------------------- | -------------------------- |
| `prefix+h` / `Alt+Enter`   | Split horizontally         |
| `prefix+v` / `Alt+Shift+Enter` | Split vertically       |
| `prefix+x` / `Alt+Esc`     | Close pane                 |
| `prefix+z`                 | Zoom pane                  |
| `prefix+;`                 | Last pane                  |
| `Alt+h/j/k/l`              | Focus left/down/up/right   |
| `Ctrl+Alt+←↓↑→`            | Focus left/down/up/right   |
| `Ctrl+Alt+Shift+←↓↑→`      | Resize pane                |
| `prefix+Ctrl+←↓↑→`         | Enter resize mode          |
| `prefix+Shift+o`           | Rename pane                |

### Tabs (tmux windows)

| Keys                          | Action        |
| ----------------------------- | ------------- |
| `prefix+c`                    | New tab       |
| `prefix+r`                    | Rename tab    |
| `prefix+k`                    | Close tab     |
| `prefix+1..9` / `Alt+1..9`    | Switch to tab |
| `prefix+p` / `Alt+←`          | Previous tab  |
| `prefix+n` / `Alt+→`          | Next tab      |
| `Alt+Shift+←` / `Alt+Shift+→` | Move tab      |

### Workspaces (tmux sessions)

| Keys                          | Action             |
| ----------------------------- | ------------------ |
| `prefix+Shift+c`              | New workspace      |
| `prefix+Shift+r`              | Rename workspace   |
| `prefix+Shift+k`              | Close workspace    |
| `prefix+Shift+p` / `Alt+↑`    | Previous workspace |
| `prefix+Shift+n` / `Alt+↓`    | Next workspace     |

### Session

| Keys        | Action        |
| ----------- | ------------- |
| `prefix+?`  | Help          |
| `prefix+q`  | Reload config |
| `prefix+d`  | Detach        |
| `prefix+[`  | Copy mode     |

## Deviations from the Omarchy seed

- `Alt+h/j/k/l` added alongside `Ctrl+Alt+arrows` for pane focus.
- `pane_gaps = true` — tmux used heavy border lines for the active pane; herdr
  has no line-weight setting, so a gap is the closest equivalent.
- `rename_pane` moved to `prefix+Shift+o`, because herdr's default
  `prefix+Shift+p` is previous-workspace here.
- Onboarding off, symbol status indicators, agent labels on pane borders, and
  toasts delivered as system notifications.

## Install

```sh
git clone git@github.com:klemengit/herdr.git ~/.config/herdr
```

If a config is already there, move it aside first — herdr's own runtime files in
that directory are ignored, so they can stay.
