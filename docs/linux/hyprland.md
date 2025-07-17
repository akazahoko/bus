# Applications
> Refer: [We are Wayland Now](https://wearewaylandnow.com/)

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

# Fixes

## Screen sharing
*[Refer](https://gist.github.com/brunoanc/2dea6ddf6974ba4e5d26c3139ffb7580)*

Required packages:
- `pipewire`
- `wireplumber`
- `xdg-desktop-portal-hyprland` (Official and AUR git version are both OK)
- `grim`
- `slurp`

(Should be in dotfiles, if not) Add the following line in `hyprland.conf`: 
```
exec-once=dbus-update-activation-environment --systemd WAYLAND_DISPLAY XDG_CURRENT_DESKTOP
```