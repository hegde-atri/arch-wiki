# Emacs

Think of something you would do on your computer... 🤔 ? You can do it in Emacs !

## Installing and Enabling Emacs

Firstly make sure you have the `emacs` package installed.
Then start its service by using the command `systemctl --user enable --now emacs`

```admonish tip
For the best performance install `emacs-nativecomp`. 
This enables native compilation. This does mean that when you install plugins
it will start compiling it in the background, which might mean occasionally you 
will notice emacs workers compiling things in the background.
```

Now you can launch Emacs using `emacsclient -nc`. Optionally include the filename as an argument.

## Doom Emacs

Configuring emacs, and keeping up to date with all the changes can be a daunting and
time consuming task. Hence I use an Emacs framework called
[Doom Emacs](https://github.com/doomemacs/doomemacs). Make sure to read the
[Getting started](https://github.com/doomemacs/doomemacs/blob/master/docs/getting_started.org).
I will not be going through how to use emacs, as it is another whole book on its own.

To install Doom Emacs run the following command (taken from Doom Emacs docs)

```sh
# dependencies
pacman -S git ripgrep fd
git clone --depth 1 https://github.com/doomemacs/doomemacs ~/.emacs.d
~/.emacs.d/bin/doom install
```
