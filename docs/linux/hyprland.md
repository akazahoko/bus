# Configs
Directory tree:
```
hypr/
├── hypridle.conf
├── hyprland/
│   ├── appearance.conf
│   ├── binds.conf
│   ├── initialize.conf
│   └── rules.conf
├── hyprland.conf
├── hyprlock.conf
└── themes/
```
Modules:
- [hyprland](https://hypr.land/)
- [hypridle](https://github.com/hyprwm/hypridle)
- [hyprlock](https://github.com/hyprwm/hyprlock)

# Fixes

## Screen sharing
*[Refer](https://gist.github.com/brunoanc/2dea6ddf6974ba4e5d26c3139ffb7580)*

Required packages:
- `pipewire`
- `wireplumber`
- `xdg-desktop-portal-hyprland` (Official and AUR git version are both OK)
- `grim`
- `slurp`

Add the following line in `hyprland.conf`: 
```shell title="~/.config/hypr/hyprland/init.conf"
exec-once=dbus-update-activation-environment --systemd WAYLAND_DISPLAY XDG_CURRENT_DESKTOP
```
