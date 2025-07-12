# System
## Disable xdg autostart
*(Can just copy from dotfiles, if not) [Refer](https://wiki.archlinux.org/title/XDG_Autostart)*

1. Create `~/.config/autostart/`
2. Copy `/etc/xdg/autostart/{entry}` -> `~/.config/autostart/`
3. Add `Hidden=true` -> `~/.config/autostart/{entry}`

## Disable XHCI Wakeup
[Refer: tmpfiles.d](https://wiki.archlinux.org/title/Systemd#systemd-tmpfiles_-_temporary_files)

1. Create `disable-xhci-wake.conf` -> `/etc/tmpfiles.d/`
2. Add the following to `disable-xhci-wake.conf`:
```
/etc/tmpfiles.d/disable-xhci-wake.conf
------------------------------------------------------
#    Path                  Mode UID  GID  Age Argument
w    /proc/acpi/wakeup     -    -    -    -   XHCI
```

## SDDM Autologin (with hyprland uwsm)
[Refer: sddm](https://wiki.archlinux.org/title/SDDM)

1. Create `autologin.conf` -> `/etc/sddm.conf.d/`
2. Add the following to `autologin.conf`
```
/etc/sddm.conf.d/autologin.conf
-------------------------------
[Autologin]
User=lain
Session=hyprland-uwsm.desktop
```

## Pacman
https://wiki.archlinux.org/title/Pacman/Tips_and_tricks#Removing_unused_packages_(orphans)

# Dolphin (KDE File Manager)
## Could not find the "keditfiletype" executable in PATH
  - Install `kde-cli-tools`
- 

# Hyprland
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

## Fcitx5
*[Refer](https://linux.do/t/topic/537066)*

Required packages:
- `fcitx5-im` (whole group)

OR

- `fcitx5`
- `fcitx5-gtk`
- `fcitx5-qt`
- `fcitx5-configtool`

Add the following environment variables in `/etc/environment`:
```
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS="@im=fcitx"
```
(Should be in dotfiles, if not) Add the following line in `hyprland.conf`:
```
exec-once = fcitx5 --replace -d
```
> - `-d` - run fcitx5 in daemon mode
> - `--replace` - only run one instance of fcitx5

## Right-click menu visual bug


# Misc
## Reset GSettings
**SHOULD use front end for managing GTK themes, [REFER]()** 

Reset Key:
```
gsettings reset SCHEMA [:PATH] KEY
```
Reset All:
```
gsettings list-schemas | xargs -n 1 gsettings reset-recursively
```