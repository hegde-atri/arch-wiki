+++
title = "Installation"
weight = 5
+++

## Prerequisites

### Dual Booting

- Make sure that the if you are dual booting, you do not wipe out Windows Boot Manager Partition.
- `powercfg /h off` - Run this command (in windows) to disable hibernation completely. This gets rid of hybrid boot, which can cause your hard drive to be read-only.


## Installing Arch Linux

You can follow the installation guide over at the [official arch wiki](https://wiki.archlinux.org/title/Installation_guide), or you can try out my [arch installation script](https://github.com/hegde-atri/arch-install) if you are not a complete beginner.

### Desktop Environments and Window Managers

When installing Arch Linux, you can install a desktop environment such as KDE Plasma, or you can opt for a much less bloated albeit harder to get used to, Window Manager.

The difference between these is that with a desktop environment, you get everything pre-configured
and a bunch of services installed for you if you need it. It usually also has a
graphical settings menu for you to change/personalize your desktop. You will usually not have to worry about having a missing package.

In a Window manager however, you need to configure everything by yourself. I am 
currently using a WM known as BSPWM, where you need also configure your own hotkey 
daemon.

If you have no idea what I was talking about, then use a Desktop Environment. You can always have multiple DE's or WM's installed at the same time, so you can try out whatever you want. However I suggest completely reinstalling linux when you settle on a particular DE, since there usually is conflict between default services used and maybe other programs, if you haven't completely uninstalled the DE.

### Networking

If you decide to use Network manager to manage your network make sure to start the service using 
```sh
sudo systemctl enable --now NetworkManager.service
```
