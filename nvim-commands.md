# NeoVim Commands Basics

## What's Neovim

Neovim is a highly extensible command-line-based text editor built on Vim. It's
extremely lightweight and efficient, and allows extensive customization for your
development environment with powerful plugin support and integrations options.
It also supports Lua for scripting and plugin integrations, which lets you
create highly tailored workflows that optimize your development process.

## Neovim Basic Navigation

- Move Cursor:
  - Arrow keys `h`,`j`,`k`,`l` for left, down, up, right respectively
- Go to the start/end of line:
  - `0` (start) / `$` (end)
- Go to specific line:
  - `:<line-number>`
- To copy and paste:
  - Copy (yank) a line:
    - Place the cursor on the line you want to copy, then type:
    ```
    > yy
    ```
  - Copy multiple lines:
    - Use a number before `yy` to yank multiple lines. For example, to copy 3
      lines, type:
    ```
    > 3yy
    ```
  - Copy a block of text (visual mode)
    - Press `v` to enter visual mode, then use arrow keys (`hjkl`) to select the
      text you want to copy.
    - Once the text is highlight, press `y` to yank it.

### Editing

- Enter Insert Mode:
  - `i` inserts before cursor
  - `a` inserts after cursor
- Save Changes:
  - `:w`
- Quit
  - `:q` (or `:wq` to save and quit)

### Code Navigation

- Go to Definition (requires LSP):
  - `gd`

# Tmux (terminal multiplexer)

`tmux` is a powerful tool for managing multiple terminal sessions from a single
window. You can create, manage, and navigate between different terminal windows
and panes within the same session. This can be incredibly useful during
development, especially for workflows that involve multiple processes
concurrently. You can use tmux to also detach for a session or reattach to it
later (idk how to do this yet lol) which basically means that you can keep
processes from one terminal running even if you disconnect from it.

## Basic Tmux Commands

### Session management

- `tmux ls` lists sessions

### Window Management

- Create a new window:
  - Press `Ctrl + [space]` then `c`
- Switch Windows:
  - Press `Ctrl + [space]` then window number (0,1,etc)
- Rename Window:
  - Press `Ctrl + [space]` then `,` then enter the new name

### Window Navigation

- Go to Previous Window:
  - Press `Ctrl [space]` then `p`
- Go to Next Window:
  - Press `Ctrl [space]` then `n`
- Resize existing Panels on Window:
  - Press `Ctrl [Shift]` then `[Shift]`
- Full Screen/ Zoom out of Window
  - Press `Ctrl [space]` then `z`

### Pane Management

- Split Pane Vertically
  - Press `Ctrl + [space]` then `%`
- Split Pane Horizontally
  - Press `Ctrl + [space]` then `"`
- Navigate Between Panes
  - Press `Ctrl + [space]` then arrow keys `hjkl`
- Resize Pane:
  - Press `Ctrl + [space]` then `:resize-pane -[L/R/U/D]`
- Kill Pane:
  - Press `Ctrl [space]` then `:`
  - Then type `kill-pane`

### Pane Navigation

- Go Up a Pane
  - Press `Cmd k`
- Go Down a Pane
  - Press `Cmd j`
- Do Left a Pane
  - Press `Cmd h`
- Go Right a Pane
  - Press `Cmd l`
- Close buffer
  - Press `:q`
