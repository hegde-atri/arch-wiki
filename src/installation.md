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

These are two ways of interacting with your computer and have different target audiences.

### DE - Desktop Environments

Desktop Environments (DE) often come with everything you need and expect from Operating Systems such as
Microsoft windows and MacOS. This includes things like: file browsers, web browsers, printing services,
settings menu to change things like locale, keyboard layouts etc...
This is what beginners should use if they have no clue how to set these up manually.

### TWM - Tiling Window Manager

Tiling Window Managers, are programs that do only one thing: that is to manage windows. This means it only
handles the opening, closing and management of windows. There are a wide variety of TWM's from ones with 
built in application launchers to ones that don't even register you keystrokes(handled to open applications
or alteast the program to open applications.)

Introduces a whole world of ergonomics, being able to manage all your windows without a mouse.

After getting used to a TWM, you will find DE's to be "bloated". (if you know what you are doing and do not need
GUI elements to configure your computer.)

## X11 vs Wayland

Use wayland, cause why not :)

### X11

Using the X-server server-client model. A very popular, stable choice but development has been almost non-existant.
Most distributions are moving to wayland. However has the most support for hardware and is suitable for most people.

### Wayland

The replacement for X11 window system. It is still seeing lots of active development, and I recommend switching over to
wayland, although it is missing quite a few features, and might need temporary workarounds that may or may not suite your needs.
- Screensharing with audio. (only tested in discord)
- Hybrid graphics with nvidia cards on laptop. (as of now!)

Although people have reported difficulty in getting wayland working with nvidia, it is a bit of hassle but is easily doable, with
the help of patience and a good guide!

