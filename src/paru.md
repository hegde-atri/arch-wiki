# AUR helper

AUR Helper, is simple a program that helps manage packages for us rather than pacman.
This is because
- `pacman` is not that intuitive.
- we cannot install AUR (Arch User Repository) packages using `pacman`.

```admonish warning
AUR is the Arch User Repository. These are packages made by people on the internet,
be careful not to install malware/malicious packages, as you will be installing it
at your own risk!!
```

## Paru

Paru is my AUR helper of choice. It is very fast and feature rich. To see some configuration options
visit the [paru page](./apps/paru.html).

### Installing paru

To install paru, we will need rust, the preferred way of installing rust would be
using `rustup`.

Lets make a ~/.source directory, cd into it and clone the paru repository.
Now we can build the paru package using `makepkg -si`.

```sh
### Installing rust ###
sudo pacman -S rustup
rustup default stable

### Cloning the repo ###
mkdir ~/.source
cd ~/.source
git clone https://aur.archlinux.org/paru.git --depth 1
cd paru
makepkg -sic
```

- `~/.source` - a directory for cloning repositories that we will build/install on 
the system.
- `makepkg -sic` - make the package, `-s` will sync the dependencies for the application
and the `-i` flag will install the package and `-c` will clean any remnant files.

### Paru configuration

Just like how we changed the default settings in pacman, we will do the same with paru to
get a better user experience.

Uncomment the following lines in the file `/etc/paru.conf`. (root permission required.)

```sh
BottomUp
SudoLoop
NewsOnUpgrade
```

### Paru usage

Just running the command `paru` will do a full system update.

You can search for packages by running `paru <package-name>`.

If you know the name of the package you want to install, you can install it using
`paru -S <package-name>`.

~~~admonish info
When you search for packages using `paru` you can see what repostiory they are coming from.
Such as community, extra, core, multilib, AUR.
~~~

## Validating AUR packages.

When using paru, if you try to install and AUR script, it will prompt you with the PKGBUILD file.
You can read through this file to make sure there is nothing that is obviously out of place.
Things like if it's trying to download something from a sketchy url.
