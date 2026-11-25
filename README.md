# dotfiles

Personal tmux and zsh configuration with plugin setup notes

## What it is

Two config files for a terminal setup: a tmux config with vi keys, pane bindings, mouse support and TPM plugins, and an oh-my-zsh config with a plugin list and a few aliases.

| File | Purpose |
| --- | --- |
| `.tmux.conf` | tmux settings and TPM plugins (sensible, resurrect, continuum, yank, prefix-highlight, open, dracula) |
| `.zshrc` | oh-my-zsh setup, plugin list and aliases |

The clipboard bindings in `.tmux.conf` use `xclip`, so they work on Linux only.

## Stack

- tmux with TPM
- zsh with oh-my-zsh
- Neovim (kickstart.nvim, installed separately; no nvim config is kept in this repo)

## Run it

Link the config files into your home directory:

```bash
ln -s "$PWD/.tmux.conf" ~/.tmux.conf
ln -s "$PWD/.zshrc" ~/.zshrc
```

Source the tmux config:

```bash
tmux source-file ~/.tmux.conf
```

Install the tmux plugin manager:

```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

See the [TPM docs](https://github.com/tmux-plugins/tpm/blob/master/docs/managing_plugins_via_cmd_line.md) for installing plugins from the command line.

Install the zsh plugins listed in `.zshrc`:

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
git clone --depth 1 -- https://github.com/marlonrichert/zsh-autocomplete.git $ZSH_CUSTOM/plugins/zsh-autocomplete
git clone https://github.com/zdharma-continuum/fast-syntax-highlighting.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/fast-syntax-highlighting
git clone https://github.com/MichaelAquilina/zsh-you-should-use.git $ZSH_CUSTOM/plugins/you-should-use
```

Install kickstart.nvim (optional):

```bash
git clone https://github.com/nvim-lua/kickstart.nvim.git "${XDG_CONFIG_HOME:-$HOME/.config}"/nvim
```

## License

MIT. See [LICENSE](LICENSE).
