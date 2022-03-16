# Changing your DNS

You can change dns multiple ways.

One way to test if your changes have taken place if you have systemd-resolve: `systemd-resolve --status`. It will list the DNS servers associated to each connection.

## Systemd-resolve

Check if you have systemd-resolve installed by running `systemd-resolve --version`. If you do not have it install it using your package manager `yay -S systemd-resolvconf`

- You can change your DNS using `sudo systemd-resolve --interface <interface_name> --set-dns <dns>`.
- Changes not persistant. You may need to run it everytime you restart your computer.

An example of it: `sudo systemd-resolve --interface wl01 --set-dns 9.9.9.9`.

## KDE-plasma system settings

- In system settings, go to the connections page.
- Click on your connection, head over to the IPv4 tab.
- Set method to `Automatic (Only addresses)`.
- In the DNS servers, box enter your dns. E.g. `9.9.9.9`.
