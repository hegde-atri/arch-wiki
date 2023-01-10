# Network Manager

This is a program that handles network connections!

You can use it using the `nmcli` command.

~~~admonish warning
By default, wifi passwords are saved in clear text. Therefore
anyone with root priviledges can access the password using the command
```
grep -r '^psk=' /etc/NetworkManager/system-connections/
```
Check [#Securing wifi passwords](./network-manager.md#securing-wifi-passwords) for more
~~~


## Connecting to WiFi

```sh
# turn wifi on
sudo nmcli radio wifi on
# list networks
sudo nmmli dev wifi list
# connect to a network using its ssid
sudo nmcli dev wifi connect <network-ssid> --ask
```

## Connecting to eduroam

If you are in an institute that uses eduraom, you can visit the
[eduroam website](https://cat.eduroam.com) to download an installer.

The installer is a `python3` script. However `python` is a symlink to `python3`
by default on arch linux, so we can simply run it after marking it as executable.

```sh
# making it executable
chmod +x <the file name>
# execute the file
./<file-name>
```

## Securing WiFi passwords

To secure passwords you will need a keyring running. (Check the
[apps page](./apps/index.html#keyring-service-gnome-keyring)).

Now run `nm-connection-editor` in your terminal, select a network connection and click
**Edit**. Now select the **Wifi Security** tab and click on the right icon of password
and check **Store the password only for this user**.
