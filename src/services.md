# Services

A service is a program that runs in the background.

We can add to remove services for a better experience. For example
we want our `NetworkManager` service to automatically start on boot, so when we login,
we are connected to a network.

There are two scopes of services
- user scope: by adding the flag `--user` to any of the commands, we will be running
the service as a user. If it is `enabled` it will start only once the user logs in.
- system scope: The service will start when the system boots up. (managed by the init
system, systemd).

## Managing services

```admonish info
If you are trying to do this in user scope, then omit the `sudo` and add the `--user`
flag.
```

### Commands

- `sudo systemctl start <service_name>`: to start a service
- `sudo systemctl enable --now <service_name>`: starts the service but also makes sure it is running when you turn your computer on / log in. If you don't need the service to run/start right now, you can omit the `--now` flag.
- `sudo systemctl stop <service_name>`: to stop a running service.
- `sudo systemctl disable <service_name>:` Stop a service from running on startup.

### Some commands that are useful for debegging:
- `sudo systemctl | grep running` : see all the services that are running.
- `sudo systemctl list-unit-files | grep enabled`: see the enabled services
