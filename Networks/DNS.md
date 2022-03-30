# Changing your DNS

You can change dns multiple ways.

Testing if your changes have taken place:

- `resolvectl status`
- if you have systemd-resolve: `systemd-resolve --status`. It will list the DNS servers associated to each connection.

Make sure that you do not use more than one way 

## Systemd-resolve

Check if you have systemd-resolve installed by running `systemd-resolve --version`. If you do not have it install it using your package manager `yay -S systemd-resolvconf`

- You can change your DNS using `sudo systemd-resolve --interface <interface_name> --set-dns <dns>`.
- Changes not persistant. You may need to run it everytime you restart your computer.

An example of it: `sudo systemd-resolve --interface wl01 --set-dns 9.9.9.9`.

You can also create a bash script that does this and set it to autorun on startup in your KDE system settings page. Here's what my startup.sh would look like:

```sh
#!bin/bash

sudo systemd-resolve --interface wlo1 --set-dns 192.168.1.3
```

## KDE-plasma system settings

- In system settings, go to the connections page.
- Click on your connection, head over to the IPv4 tab.
- Set method to `Automatic (Only addresses)`.
- In the DNS servers, box enter your dns. E.g. `9.9.9.9`.

## Editing resolv.conf

- Open a terminal
- `sudo micro /etc/resolv.conf` and add your dns server/s like this: `nameserver 9.9.9.9`

