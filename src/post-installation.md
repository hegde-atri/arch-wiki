# Post Installation

Just logged in after installing? Let's make sure you have a working internet connection.
Try running `ping gnu.org`. If you start receiving packets, then you are connected!. Stop this
command by pressing `Ctrl-C`. 

If you do not get any packets, you might want to connect to the
internet either using ethernet or wifi. If you are using NetworkManager, also make sure the service
is running by using the command `sudo systemctl status NetworkManager`. If it is not running, start it and enable it using the command `sudo systemctl enable --now NetworkManager`.

To connect to a wifi network using NetworkManager have a look at the 
[Network Manager page](./network-manager.html)

```admonish info
We will be modifying configuration files from the command line using the tool VIM.
You can learn the basics by VIM by reading the [VIM page](./vim.md).
```

## PC Speaker

To provide auditory cues, your motherboard usually comes with a simple speaker capable
of producing beeps. This can be very loud and annoying when using the terminal, as it
might beep quite often. To test if you have this problem, just press `<TAB>` multiple
after logging in, if you hear a beep and want to remove perform the following actions.

### Non-Persistant solution

We can disable it by unloading the `pcspkr` and `snd_pcsp` kernel modules.

```sh
rmmod pcspkr
rmmod snd_pcsp
```

### Persistant solution

There are two easy ways of persisting this change.

#### Blacklisting modules

You can blacklist the modules to prevent them from being loaded at boot.
Either by adding `module_blacklist=pcspkr,snd_pcsp` in our bootloaders kernel line.
(This is <i>"advanced"</i> and will require regenerating your grub config if you are using grub)

or by creating the file `/etc/modprobe.d/nobeep.conf` (with root permissions) with the 
following content.

```conf
blacklist pcspkr
blacklist snd_pcsp
```

#### Console

You can uncomment `set bell-style none` in `/etc/inputrc`. (require root permission)

## `.bashrc`

When we are using the terminal we are usually interacting with a shell inside of a terminal emulator.
When we open the shell, it loads its "configuration" from the file `~/.bashrc`. In here we can set
command shortcuts to improve our work flow.

```admonish example
Updating our computer using pacman usually is done using `pacman -Syu`
We can simplify it to update, by adding `alias update='pacman -Syu'` in our `~/.bashrc` file.
```


## Configuring Pacman

Now lets configure pacman so it is more perfomant and readable.

### Enabling Parallel Downloads

This will usually significantly improve download times when using pacman.
Lets open the file `/etc/pacman.conf` with root priviledges.
```sh
sudo vim /etc/pacman.conf
```

Now find this line. (using [vim](./vim.md))
```
#ParallelDownloads...
```

and replace it with
```
ParallelDownloads = 15
```

### Enabling multilib repository

This repository contains 32-bit applications. Includes applications such as steam.
To enable this, uncomment the following lines in `/etc/pacman.conf` (root permission required)
```
[multilib]
Include = /etc/pacman.d/mirrorlist
```

Now you will need to update pacman's database by running
```
sudo pacman -Sy
```

### Enabling color output

This will enable colour ouput which will be helpful for our [AUR Helper](./paru.md) paru.
To enable this, we will need to uncomment `Color` from `/etc/pacman.conf`. (root permission required)

