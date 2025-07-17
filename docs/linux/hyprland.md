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