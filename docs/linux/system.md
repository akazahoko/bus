# System

## General
### Reload daemon
```shell
sudo systemctl daemon-reload
```

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

# `fstab`
> PATH: `/etc/fstab`
1. Find drive UUID
```shell
sudo blkid
```

2. Create mount point
```shell
sudo mkdir /mnt/$(DRIVE_NAME)
``` 

3. Edit fstab
```shell
UUID=$(DRIVE_UUID) $(MOUNT_POINT) $(PARTITION_FS) defaults 0 0 
```

4. [Reload `systemd`](#reload-daemon)

## Network
### DNS