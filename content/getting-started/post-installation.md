+++
title = "Post installation"
weight = 10
+++

## Network Manager

If you are using ethernet you can skim through the wifi commands and directly update your system using `sudo pacman -Syu`
If you are using an ethernet connection, you should just be connected to the internet. If not refer to the arch wiki.

For connecting to a wifi networking using Network Manager.

```sh
sudo nmcli radio wifi on #turns wifi on.
sudo nmcli dev wifi list #list networks.
sudo nmcli dev wifi connect <network-ssid> --ask
```

You can check if your internet connection works by using ping - `ping gnu.org` and viewing active connections by using
`nmcli con show`.

Now lets do a `sudo pacman -Syu` to update the system.

## Text editor

We will be editing quite a few files from the terminal. I will be using vim in
all my code snippets, however if you do not know how to use vim, I suggest you 
use micro, which is much better than nano.
 ```sh
 sudo pacman -S vim micro
 ```

## Configuring pacman and AUR

### Pacman

Lets enable multilib repositories first, this allows us to install 32-bit applications such as steam.
To do this, we need to edit the pacman.conf file with "admin"/sudo privileges
```sh
sudo vim /etc/pacman.conf
```
Here we want to
- Uncomment `Color`
- Uncomment
```conf
[multilib]
Include = /etc/pacman.d/mirrorlist
```
- Uncomment `ParallelDownloads = 5` and make it `ParallelDownloads = 15`
Now we will need to update pacman's database since we added the multilib repositories.
```sh
sudo pacman -Sy
```

### Paru

One of features of Arch Linux is the AUR(Arch User Repositories), which means we can 
install quite a lot of applications. Although make sure to reach the PKGBUILDs before
using them.

One of the tools we can use to make using the AUR easier is by using an AUR helper.
My choice would be [paru](https://github.com/morganamilo/paru), an actively developed AUR helper written in rust.

When building applications from source I recommend cloning the source to a `.source` directory.

```sh
mkdir ~/.source
cd ~/.source
sudo pacman -S --needed base-devel
git clone https://aur.archlinux.org/paru.git
cd paru
makepkg -si
```
If you get cargo errors, it might be a DNS issue. Change your dns to cloudflares `1.1.1.1` temporarily by `sudo vim /etc/resolv.conf` and change your nameserver.

Before we use paru I recommend changing the way it lists results by editing `paru.conf`
```sh
sudo vim /etc/paru.conf
```
and uncommenting `BottomUp`.

Now we can run `paru`. This will do a system upgrade while also checking for and AUR package updates. To install anything, you can first search for it and select it by doing `paru <search-term>` or if you know the package name, you can skip the searching by running `paru -S <package>`

## Auto-mounting drives

If you have a secondary drive that you want to to automatically mount upon system start,
we will need to configure it in a config file. Make sure that your config file is valid
as if it is invalid, your system will fail to boot.
If you are mounting an NTFS drive, make sure you have the `ntfs-3g` package.

First lets open the terminal and type `lsblk -f`. This will list all the disks & partitions connected along with their UUID.
Select your disk of choice and copy the UUID from the terminal by using `LCtrl + LShift + c`. Also make note of the partition
and open `sudo vim /etc/fstab`.

```sh
... # <-- These are already present drives. If the file is empty, you have not installed arch properly!
# /dev/sdb1 -> replace sdb1 with your partition name
UUID=<paste your UUID here>     /mnt/hdd ntfs-3g defaults 0 2
#    ^ paste using Ctrl+Shift+v  ^this must be an empty directory
# replace ntfs-3g with your drive's format. and leave the rest the same
```
In this code block, I am mounting my HDD to `/mnt/hdd`. Make sure there is an empty directory `/mnt/hdd`, or else mounting will fail.

Check whether your fstab file is valid by using `sudo mount --fake -a` and then `sudo mount -a` if there are no errors. If there are errors, then just remove whatever you've added and start again.

## Changing keyboard layout and mouse acceleration

You'll need to create this section in `00-keyboard.conf`. Replace `gb` with your layout.

`sudo vim /etc/X11/xorg.conf.d/00-keyboard.conf`
```conf
Section "InputClass"
        Identifier "system-keyboard"
        Option "XkbLayout" "gb"
        Option "XkbModel" "pc104"
EndSection
```

Mouse acceleration can be disabled by the following config.

`sudo vim /etc/X11/xorg.conf.d/50-mouse-acceleration.conf`

```conf
Section "InputClass"
	Identifier "My Mouse"
	Driver "libinput"
	MatchIsPointer "yes"
	Option "AccelProfile" "flat"
	Option "AccelSpeed" "0"
EndSection
```

## WM fix (for java applications)

If you are using a Window Manager, then Java applications will not launch (example - JetBrains IDE's). For this 
make sure to install the `wmname` package and then run this everytime you want use
a java application, or add it to your autostart file.

```sh
export _JAVA_AWT_WM_NONREPARENTING=1
export AWT_TOOLKIT=MToolkit
wmname LG3D
```
