# Vim

Vim - Vi iMproved is a text editor that uses keystrokes to control everything! You do not need your
mouse whatsoever. This keystrokes are often called `vim motions`. Vim motions are so effecient, that
most text-editors or IDE's have a Vim extension of some sort.

To learn how to use vim:
- Install `vim` package.
- Type `:VimTutor`

As much as I do love the intention behind vim, I cannot learn vim script, so I use Neovim instead.

## Basic commands

- `gg` Goes to start of the file.
- `G` Goes to end of file.
- `h`, `j`, `k`, `l` For navigation right, down, up, left respectively.
- `:wq` To write and quit a file.
- `:q!` Quit file without saving changes.
- `i` To enter insert mode and `esc` to exit insert mode.

You will not be able to type any changes into a file without going into insert mode.
Once you are done modifying the text, exit out of insert mode (puts you in command mode)
after while you will be able to use `:wq` to write to a file and quit vim.

# Neovim

[Neovim](https://neovim.io) is an opensource application that is basically vim, but extensible using the Lua programming
language. (Neovim is an amazing project and a lot of work has been done to refector it!)

To try neovim, install the `neovim` package.

```admonish tip
Add `alias vim='nvim'` to your `~/.bashrc` file so you always open neovim!
```

I will not go into further detail on configuring neovim as I primarily use [Emacs](./emacs.md) as my
editor.

You try my nvim configuration [here](https://github.com/hegde-atri/.nvim).

~~~admonish info title="You try my nvim configuration [here](https://github.com/hegde-atri/.nvim)."

To use it copy and paste the commands below
```sh
sudo pacman -S ripgrep
mv ~/.config/nvim ~/.config/nvim.bak
git clone https://github.com/hegde-atri/.nvim ~/.config/nvim
```
~~~

Now open nvim and let Packer install its plugins. press `q` once its over and now start using neovim!
