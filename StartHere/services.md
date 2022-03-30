# Services
A service is a program that runs in the background

## Some commands
- `sudo systemctl start <service_name>`: to start a service
- `sudo systemctl enable --now <service_name>`: starts the service but also makes sure it is running when you turn your computer on / log in. If you don't need the service to run/start right now, you can omit the `--now` flag.
- `sudo systemctl stop <service_name>`: to stop a running service.
- `sudo systemctl disable <service_name>:` Stop a service from running on startup.

Some commands that are useful for debegging:
- `sudo systemctl | grep running` : see all the services that are running.
- `sudo systemctl list-unit-files | grep enabled`: see the enabled services