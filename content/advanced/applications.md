+++
title = "Managing your applications"
weight = 5
+++

# Managing your applications

There are numberous ways of installing the same application in linux. I'll be going over
the pros and cons of most of them.

## Different types of applications

I will be covering how and when to use AppImages, AUR apps and flatpaks. I will not be going over snap packages as I do not use it since it is too slow.

### AppImages

AppImage files are usually available at a project's GitHub or website, it is an executable
you download. For example, if I downloaded `Application.AppImage`.
```sh
chmod a+x Application.AppImage # gives executable permissions to the file
./Application.AppImage # executes the file
```
If you use AppImages, using AppImage Launcher can be really handy, every time you
launch an AppImage, it automatically asks you if you want to create a desktop entry for
it which makes launching it easier. You can install it from the AUR using the command
`paru -S appimagelauncher`. You can see their [GitHub](https://github.com/TheAssassin/AppImageLauncher) for more information.

AppImages can allow you to store multiple versions of the same programs if required.


### AUR apps

The AUR apps are dead simple to use, and there usually is an AUR package for everything!
They are updated automatically when you run paru. Just make sure to read through the
PKGBLD file when prompted in paru. Since it is made by user, we need to make sure that
there is no malicious intent.

One of the downsides is that it might be a few hours to days apart from an offical update.

### Flatpaks

One of the best features of flatpak is that it is usually officially supported. This
means that it also receives updates at the same time as other platforms. To get flatpak
setup you will need to install the flatpak package and then restart your computer
```sh
sudo pacman -S flatpak
sudo reboot now
```

The best place to get flatpaks are at [flathub](https://flathub.org/home).
You can update your flatpak apps from the terminal.
```sh
flatpak list # lists installed apps
flatpak update # updates everything
flatpak update <flatpak-app> # updates specified flatpak
```

## Running windows apps

I personally do not like running windows apps in linux, and usually use a virtual machine
when necessary. However for some people it may be easier to have it "integrated" to your
workflow. For this you have 2 options depending on what application it is.

### Microsoft and Adobe apps

You can do this using [winapps](https://github.com/Fmstrat/winapps). You can read their
README file for installation instructions. It basically runs a virtual machine in the
background, but the windows spawn in your Linux environment, and are available as 
launch-able applications from your menu (start menu/dmenu).

### Running standalone 'exe' files

If you have like small exe files, such as calculator emulators, you can use them from a 
flatpak called bottles that is available on [flathub](https://flathub.org/apps/details/com.usebottles.bottles). You can find a detailed guide on how to use bottles in the [docs](https://docs.usebottles.com/) section of their [website](https://usebottles.com/)
