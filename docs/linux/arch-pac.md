*Unless stated, packages are from official arch repository*

# System
## Network
> Refer: [NetworkManager](https://wiki.archlinux.org/title/NetworkManager), [Firewalld](https://wiki.archlinux.org/title/Firewalld)
- Backend: `networkmanager`
- Frontend: `network-manager-applet` -> GUI frontend (`nm-applet`)
---
- Backend: `firewalld`
- Frontend: `firewall-applet` (BUILT-IN) -> GUI Frontend

## Audio
> Refer: [PipeWire](https://wiki.archlinux.org/title/PipeWire), [WirePlumber](https://wiki.archlinux.org/title/WirePlumber)

- Backend: `pipewire`
- Frontend: 
  - `pactl` (BUILT-IN)
  - `wireplumber` -- CLI (`wpctl`)
  - `pavucontrol` -- GUI for PipeWire / PulseAudio
- Extensions: 
  - `pipewire-alsa` -- ALSA Interface
  - `pipewire-audio` -- Audio Processor (Required)
  - `pipewire-jack` -- JACK2 support
  - `pipewire-pulse` -- PulseAudio Support
  - `pipewire-session-manager` -- Session Manager (Required)

## GPU


# General
> Refer: [We are Wayland Now](https://wearewaylandnow.com/)

# Desktop Environment
- `hyprland` ([config-wiki](https://wiki.hypr.land/))

## Wallpaper
- Backend:
  - `hyprpaper`
  - `swww`
- Frontend:
  - `waypaper` 

## Application Launcher
- `rofi`
- `wofi`
- `tofi` (AUR)
- `fuzzel ([config-wiki](https://man.archlinux.org/man/fuzzel.ini.5.en))

## Status bar
- `waybar` ([config-wiki](https://github.com/Alexays/Waybar/wiki))

## logout menu
- `wlogout`

# Application
## Image
- `qimgv`
- `eog` -- Gnome Image Viewer 
- `feh` -- CLI  

## Screenshot
- Backend:
  - `grim`
  - `slurp`
- Frontend:
  - `hyprshot`

## Clipboard
- Backend:
  - `wl-clipboard`
  - `wl-clip-persist`
- Frontend:
  - `cliphist`

## File Manager
https://wiki.archlinux.org/title/Category:File_managers