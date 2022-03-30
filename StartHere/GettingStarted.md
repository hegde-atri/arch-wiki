# Getting Started

Some of the tools that you will want. I might have used these tools in the other pages.

## Using a package manager/AUR helper

is the AUR? It is the Arch User repository. Contaning packages made and maintained by the users. My personal preference of package manager is yay. Install [yay](https://github.com/Jguer/yay).

```sh
pacman -S --needed git base-devel
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si
```
I also use flatpak for some of my application which can be installed using:
```sh
sudo pacman -S flatpak
```
and then restart your system

## Changing your terminal and shell

My choice of terminal emulator would be kitty. I primarily have bash installed, but I recommend using fish for beginners
```sh
yay -S kitty fish
```

To change your default shell to fish
```
chsh -s `which fish`
```

