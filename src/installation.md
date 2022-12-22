# Installation

Usually referring to the Arch installation guide should work, for times when it doesn't work, or
if you are a seasoned user wanting to automate the installation, have a look at my
[arch-install script](https://github.com/hegde-atri/arch-install)

## Dual booting

If you are dual booting with Windows, then make sure to
- Not wipe the Windows Boot Manager partition.
- Run `powercfg /h off` in Powershell as admin. This will disable hibernation completely. This
gets rid of hybrid boot, which can cause any shared hard drives to be read-only.

## DE vs TWM

### DE - Desktop Environments

### TWM - Tiling Window Manager 
