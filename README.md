# nvim_config_1

My Neovim config for Python development, built on [LazyVim](https://github.com/LazyVim/LazyVim).
This is set up to work with my local, up to date Linux systems while still remaining compatible with my university's systems.

## What's different from stock LazyVim

- **Live file reloading.** `lua/custom/directory-watcher.lua` watches the working directory with
  libuv's `fs_event` API, and `lua/custom/hotreload.lua` reloads visible buffers when a file changes
  on disk (unless the buffer has unsaved edits). This replaces the default focus/`checktime`-based
  reloading, so changes made by other tools show up right away. Taken from Richard Gill's post
  [Tips for configuring Neovim for Claude Code](https://xata.io/blog/configuring-neovim-coding-agents).
- **pylsp instead of pyright**, since it's easier to get running on servers.
- **OSC 52 clipboard**, so yanks reach my local clipboard over SSH.
- **Notebooks:** [jupytext.nvim](https://github.com/GCBallesteros/jupytext.nvim) (hydrogen-style
  `# %%` cells) and [molten-nvim](https://github.com/benlubas/molten-nvim) for running them.
- **Git:** [Neogit](https://github.com/NeogitOrg/neogit) with diffview, on `<leader>gn`.
- **LazyVim extras:** DAP, aerial, refactoring, testing, and language support for Python, Docker,
  JSON, Markdown, and TOML (see `lazyvim.json`).

## tmux

`tmux.conf` turns on mouse support, a 50k-line history, passthrough, and clipboard forwarding so
OSC 52 works through tmux too. Link or copy it to `~/.tmux.conf`.

## Install

```sh
mv ~/.config/nvim ~/.config/nvim.bak   # if you have an existing config
git clone git@github.com:taylorsm9/nvim_config_1.git ~/.config/nvim
nvim
```

lazy.nvim installs itself and the plugins on first launch.
