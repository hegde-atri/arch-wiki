# Some packages that I use

These are some packages that I use day to day.

## Getting bluetooth working

TODO

## Wallpapers

Ignis wallpapers from the 'Get new wallpapers' store.

## Multimedia

### mpv + svp

Mpv is a free and opensource media player. SVP(Smooth video project) is a real time video frame rate converter(Converts any video into 60 fps). If you do not want SVP + mpv, you can install VLC media player.

You can use just mpv by disabling svp in its settings. 
The following instructions were taken from this [reddit post](https://www.reddit.com/r/linux/comments/c9jrzn/getting_svp_to_work_with_mpv_in_linux_manjaro/).
Firstly make sure that you your nvidia drivers:
`sudo pacman -S nvidia nvidia-utils nvidia-settings`
Now follow the follow the 
Run the below command for some of the packages we need. (In the order given)
- `sudo pacman -S vapoursynth mediainfo lsof`

- `sudo pacman ocl-icd opencl-headers opencl-nvidia`

- Now lets install mpv-full from the AUR. We can do this using yay: `yay mpv-full`

- Now we install SVP from the AUR using yay: `yay svp`

- Now while opening any file, open it with SVP which should open svp in the background and an mpv window with your videos
If you want mpv to use SVP by default then add the following to ~/.config/mpv/mpv.conf
```conf
profile=svp # Enable svp by default, here in the "top-level" of mpv.conf

# Keep within screen bounds; if window larger than W%xH% of screen, resize to W%xH%
autofit-larger=100%x100%

[svp]                               # SVP profile
# Everything below here only applies to this profile until another profile is declared!

input-ipc-server=/tmp/mpvsocket     # Receives input from SVP
hr-seek-framedrop=no                # Fixes audio desync
resume-playback=no                  # Not compatible with SVP

# These are are for hardware (GPU?) decoding.
# According to the Arch wiki,
# "hardware decoding is discouraged by mpv developers and is not likely to make 
# a significant difference in performance."
# Still: slightly better performance for 4K videos if enabled, apparently.
hwdec=auto-copy
hwdec-codecs=all

# Can fix stuttering in some cases, in other cases probably causes it. Try it if you experience stuttering.
#opengl-early-flush=yes
```

### VLC media player

Simple, easy to use media player. Install using `yay -S vlc`.

## Game-related

I use Steam, and lutris to play most my games.
`yay -S lutris steam`
