# Wayland

```admonish info
Wayland is the new display server protocol being developed as an alternative (and hoping to
replace) X11/Xorg.
```

## Recommended packages

Here are the packages I'd install to use Hyprland.

To make things easier I'm going to be using [paru](./paru.md)

```sh
paru -S noto-fonts noto-fonts-emoji noto-fonts-cjk ttf-jetbrains-mono ttf-font-awesome \
        sxiv feh mpv zathura zathura-pdf-mupdf ffmpeg fzf man-db zip unzip unrar \
        papirus-icon-theme dosfstools ntfs-3g git pipewire pipewire-pulse vim neovim \
        arc-gtk-theme rsync firefox neofetch helix libnotify jq aria2 mako ranger \
        waybar xdg-user-dirs libconfig polkit kitty networkmanager emacs-nativecomp \
        dhcpcd wpa_supplicant pamixer mpd ncmpcpp swaylock wofi wlogout wl-clipboard \
        hyprland waybar-hyprland-git
```

## Hyprland

This is my WM (Window Manager) of choice on wayland.

To read more on configuring Hyprland, visit the [Hyprland page](./config/hyprland.html)

Here are some packages that you will need if you are using a wayland/wlroots based compositor.

- `swaylock`: a simple screen lock.
- `wlogout`: a simple logout menu.
- `wofi`: wayland version of rofi, an applications launcher.
- `wl-clipboard`: clipboard functionality like xclip.
- `mako`: notification daemon.

