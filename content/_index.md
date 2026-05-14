+++
title = "QTerminator"
template = "index.html"
+++

A **Qt port of [Terminator](https://github.com/gnome-terminator/terminator)**,
the popular tabbed/split terminal emulator — built from the ground up in
PyQt6 over QTermWidget.

## What it does

- **Tabs and splits** — horizontal and vertical splits with recursive nesting; tab bar with close, rename, reorder
- **Per-terminal titlebar** — title, group indicator, read-only badge, activity status
- **Terminal grouping** — assign terminals to named groups; broadcast input to a group or all terminals
- **Read-only mode** — lock a terminal to prevent stray keystrokes
- **Profile system** — named profiles with per-terminal switching and cycling
- **Plugin system** — `URLHandler`, `MenuProvider`, `OutputWatcher` base classes; user + built-in plugin dirs
- **Preferences dialog** — font, 13 built-in color schemes, cursor shape, scrollback, tab position
- **Layout save/restore** — splits and tabs restored automatically on next launch
- **CLI arguments** — working directory, title, execute command, geometry, no-restore
- **50+ keyboard shortcuts** for every common operation

## Install

```bash
git clone https://codeberg.org/qterminator/qterminator
cd qterminator
# Requires Python 3.10+, PyQt6 6.5+, QTermWidget 6 + Python bindings
just run
```

Source: [codeberg.org/qterminator/qterminator](https://codeberg.org/qterminator/qterminator)
