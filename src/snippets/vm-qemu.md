# Virtual Machines

## Install QEMU/KVM and virt-manager

Installing all the packages we need.
```sh
sudo pacman -S qemu virt-manager archlinux-keyring virt-viewer dnsmasq vde2 bridge-utils openbsd-netcat ebtables iptables libguestfs
```

Now lets start the KVM libvirt service

```sh
sudo systemctl enable --now libvirtd.service
```

Make sure libvirtd is running

```sh
sudo systemctl status libvirtd.service
```

Now lets give permissions for our standard user to manage KVM.

```sh
sudo vim /etc/libvirt/libvirtd.conf
```

Now uncomment `unix_sock_group = "libvirt"` and `unix_sock_rw_perms = "0770"`.
Now add your user to the libvirt group and restart the libvirt service.


```sh
sudo usermod -a -G libvirt $(whoami)
newgrp libvirt
sudo systemctl restart libvirtd.service
```

## Enabling Nested Virtualization

This allows you to run virtual machines inside virtual machines.

```sh
# Intel CPU
sudo modprobe -r kvm_intel
sudo modprobe kvm_intel nested=1
# AMD CPU
sudo modprobe -r kvm_amd
sudo modprobe kvm_amd nested=1
```

To make this configuration persistant: 
```sh 
echo "options kvm-intel nested=1" | sudo tee /etc/modprobe.d/kvm-intel.conf
```

```sh
# Intel CPU
systool -m kvm_intel -v | grep nested
cat /sys/module/kvm_intel/parameters/nested
# AMD CPU
systool -m kvm_amd -v | grep nested
cat /sys/module/kvm_amd/parameters/nested 
```

## Common Issues

If your network `default` is not enabled run `sudo virsh net-start default`

# Conclusion

Now you can install your virtual machines using virt-manager
