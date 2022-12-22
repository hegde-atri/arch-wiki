# Post Installation

Just logged in after installing? Let's make sure you have a working internet connection.
Try running `ping gnu.org`. If you start receiving packets, then you are connected!. Stop this
command by pressing `Ctrl-C`. 

If you do not get any packets, you might want to connect to the
internet either using ethernet or wifi. If you are using NetworkManager, also make sure the service
is running by using the command `sudo systemctl status NetworkManager`. If it is not running, start it and enable it using the command `sudo systemctl enable --now NetworkManager`.

To connect to a wifi network using NetworkManager have a look at the 
[Network Manager page](./network-manager.html)

## Making sure you have the packages you want

Sometimes you might've missed a package that gives you core functionaly you require. So 
here is a list of packages I always install.

TODO: complete list
