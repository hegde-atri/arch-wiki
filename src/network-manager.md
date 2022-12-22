# Network Manager

## Connecting to WiFi

```sh
# turn wifi on
sudo nmcli radio wifi on
# list networks
sudo nmmli dev wifi list
# connect to a network using its ssid
sudo nmcli dev wifi connect <network-ssid> --ask
```
