# System

- [System](#system)
- [Audio](#audio)
  - [Configure sample rate](#configure-sample-rate)
- [Network](#network)
  - [DNS](#dns)
    - [DNS over HTTPS](#dns-over-https)
    - [Cloudflare Warp](#cloudflare-warp)
- [Peripherals](#peripherals)
  - [Fans](#fans)
  - [Printers](#printers)
- [Service](#service)
  - [Disable xdg autostart](#disable-xdg-autostart)
  - [Disable XHCI Wakeup](#disable-xhci-wakeup)
  - [SDDM Autologin (with hyprland uwsm)](#sddm-autologin-with-hyprland-uwsm)
  - [Auto mount drives](#auto-mount-drives)
- [Time \& Date](#time--date)
  - [NTP](#ntp)

# Audio
> Reference: [PipeWire](https://wiki.archlinux.org/title/PipeWire), [WirePlumber](https://wiki.archlinux.org/title/WirePlumber)

- Backend: 
  - `pipewire`
  - `wireplumber` 
- Extensions: 
  - `pipewire-alsa` -- ALSA Interface
  - `pipewire-audio` -- Audio Processor (Required)
  - `pipewire-jack` -- JACK2 support
  - `pipewire-pulse` -- PulseAudio Support
  - `pipewire-session-manager` -- Session Manager (Required)
- Frontend: 
  - `pactl` (BUILT-IN)
  - `pavucontrol` -- GUI for PipeWire / PulseAudio
  - `pw-top` -- monitor
  - `wpctl` (BUILT-IN)

## Configure sample rate
1. Edit the default sample rate in `pipewire.conf` (`default.clock.rate`)
2. Edit the available sample rates (`default.clock.allow-rates`)
3. Restart services: `pipewire.service`, `wireplumber.service`

# Network
> Reference: [NetworkManager](https://wiki.archlinux.org/title/NetworkManager), [Firewalld](https://wiki.archlinux.org/title/Firewalld)
- Backend: 
  - `networkmanager`
  - `firewalld`
- Frontend: 
  - `network-manager-applet` -> GUI frontend (`nm-applet`)
  - `firewall-applet` (BUILT-IN) -> GUI Frontend

## DNS
### DNS over HTTPS
> Reference: [Arch Wiki: DNS-over-HTTPS](https://wiki.archlinux.org/title/DNS-over-HTTPS)

Require package: `dns-over-https`

1. Disable all services bound to port 53, check by the following cmd
```shell
ss -lp 'sport = :domain'`
```
2. Add following line to `/etc/resolv.conf`
```shell
namespace 127.0.0.1
```
3. Enable service `doh-client.service`

### Cloudflare Warp
> Reference: [Cloudflare: Linux](https://developers.cloudflare.com/warp-client/get-started/linux/)
 
Tool: `warp-cli`
1. Install Cloudflare Warp ([Package list](/docs/linux/packages.md#warp))
2. Enable service `warp-svc.service`
3. Registrate `warp-cli registration new`
4. Connect `warp-cli connect`
5. Check via [cloudflare](https://1.1.1.1/help)

# Peripherals
## Fans
Required Packages:
  - `lm_sensors`
  - [coolerControl](https://docs.coolercontrol.org/)
 
1. Setup sensors
```shell
sudo sensors-detect
```
2. Configure via coolerControl
## Printers
> Reference: [Arch Wiki: CUPS](https://wiki.archlinux.org/title/CUPS)

Prerequisities:
  - `cups`
  - `system-config-printer`

1. Enable service `cups`
2. Configure via system-config-printer (GUI)

# Service
## Disable xdg autostart
> Reference: [Arch Wiki: XDG Autostart](https://wiki.archlinux.org/title/XDG_Autostart)

*Note: copy from dotfiles*

1. Create `~/.config/autostart/`
2. Copy `/etc/xdg/autostart/{entry}` -> `~/.config/autostart/`
3. Add `Hidden=true` -> `~/.config/autostart/{entry}`

## Disable XHCI Wakeup
> Reference: [Arch Wiki: tmpfiles.d](https://wiki.archlinux.org/title/Systemd#systemd-tmpfiles_-_temporary_files)

1. Create `disable-xhci-wake.conf` -> `/etc/tmpfiles.d/`
2. Add the following to `disable-xhci-wake.conf`:
```
/etc/tmpfiles.d/disable-xhci-wake.conf
------------------------------------------------------
#    Path                  Mode UID  GID  Age Argument
w    /proc/acpi/wakeup     -    -    -    -   XHCI
```

## SDDM Autologin (with hyprland uwsm)
> Reference: [Arch Wiki: SDDM](https://wiki.archlinux.org/title/SDDM)

1. Create `autologin.conf` -> `/etc/sddm.conf.d/`
2. Add the following to `autologin.conf`
```
/etc/sddm.conf.d/autologin.conf
-------------------------------
[Autologin]
User=lain
Session=hyprland-uwsm.desktop
```

## Auto mount drives 
> Reference: [Arch Wiki: fstab](https://wiki.archlinux.org/title/Fstab#Automount_with_systemd)
1. Find drive UUID
```shell
sudo blkid
```

2. Create mount point
```shell
sudo mkdir /mnt/$(DRIVE_NAME)
``` 

3. Edit `/etc/fstab`
```shell
UUID=$(DRIVE_UUID) $(MOUNT_POINT) $(PARTITION_FS) defaults 0 0 
```

# Time & Date
## NTP
> Reference: [Arch Wiki: systemd-timesyncd](https://wiki.archlinux.org/title/Systemd-timesyncd)

1. Edit `/etc/systemd/timesyncd.conf`
```
/etc/systemd/timesyncd.conf
---------------------------
NTP=stdtime.gov.hk
```
2. Enable NTP
```shell
timedatectl set-ntp true
```