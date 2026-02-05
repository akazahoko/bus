- [[#Audio|Audio]]
	- [[#Audio#Configure sample rate|Configure sample rate]]
- [[#Network|Network]]
	- [[#Network#DNS|DNS]]
		- [[#DNS#DNS over HTTPS|DNS over HTTPS]]
		- [[#DNS#Cloudflare Warp|Cloudflare Warp]]
- [[#Peripherals|Peripherals]]
	- [[#Peripherals#Fans|Fans]]
	- [[#Peripherals#Printers|Printers]]
- [[#Service|Service]]
	- [[#Service#Disable xdg autostart|Disable xdg autostart]]
	- [[#Service#Disable XHCI Wakeup|Disable XHCI Wakeup]]
	- [[#Service#SDDM Autologin (with hyprland uwsm)|SDDM Autologin (with hyprland uwsm)]]
	- [[#Service#Auto mount drives|Auto mount drives]]
- [[#Time & Date|Time & Date]]
	- [[#Time & Date#NTP|NTP]]
- [[#Locale|Locale]]
# Audio
> SEE: [PipeWire](https://wiki.archlinux.org/title/PipeWire), [WirePlumber](https://wiki.archlinux.org/title/WirePlumber)
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
> SEE: [NetworkManager](https://wiki.archlinux.org/title/NetworkManager), [Firewalld](https://wiki.archlinux.org/title/Firewalld)
- Backend: 
  - `networkmanager`
  - `firewalld`
- Frontend: 
  - `network-manager-applet` -> GUI frontend (`nm-applet`)
  - `firewall-applet` (BUILT-IN) -> GUI Frontend

## DNS
### DNS over HTTPS
> SEE: [Arch Wiki: DNS-over-HTTPS](https://wiki.archlinux.org/title/DNS-over-HTTPS)

Require package: 
- `dns-over-https`

Setup:
1. Disable all services bound to port 53, check by the following cmd
```shell
ss -lp 'sport = :domain'`
```
2. Edit `resolv.conf`
```shell title="/etc/resolv.conf"
namespace 127.0.0.1
```
3. Enable service `doh-client.service`

### Cloudflare Warp
> SEE: [Cloudflare: Linux](https://developers.cloudflare.com/warp-client/get-started/linux/)
 
Tool: `warp-cli`
1. Install Cloudflare Warp ([Package list](/docs/linux/packages.md#warp))
2. Enable service `warp-svc.service`
3. Registrate `warp-cli registration new`
4. Connect `warp-cli connect`
5. Check via [cloudflare](https://1.1.1.1/help)

# Peripherals
## Fans
Prerequisites:
  - lm_sensors
  - coolercontrol<sup>aur</sup>
 
1. Setup sensors
```shell
sudo sensors-detect
```
2. Configure via coolerControl
## Printers
> SEE: [Arch Wiki: CUPS](https://wiki.archlinux.org/title/CUPS)

Prerequisities:
- cups
- system-config-printer

Setup:
1. Enable service `cups`
2. Configure via system-config-printer (GUI)
## Fingerprint reader
> SEE: [Arch Wiki: fprint](https://wiki.archlinux.org/title/Fprint)

Prerequisites:
- fprintd

Setup:
1. Enroll new fingerprint
```shell
sudo fprintd-enroll [OPTION] [username]
```
2. Add `pam_fprintd.so` as an auth method
```shell title="/etc/pam.d/foo"
auth    sufficient    pam_fprintd.so
```
*Copy `polkit-1` from `/usr/lib/pam.d/polkit-1` to `/etc/pam.d/` for polkit*
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
```shell title="/etc/tmpfiles.d/disable-xhci-wake.conf"
#    Path                  Mode UID  GID  Age Argument
w    /proc/acpi/wakeup     -    -    -    -   XHCI
```

## Auto login
> SEE [Arch Wiki: greetd](https://wiki.archlinux.org/title/Greetd#Enabling_autologin)

```shell title="/etc/greetd/config.toml"
[initial_session]
command = "start-hyprland"
user = "foo"
```
## Auto mount drives 
> Reference: [Arch Wiki: fstab](https://wiki.archlinux.org/title/Fstab#Automount_with_systemd)
1. Find drive UUID
```bash
sudo blkid
```

2. Create mount point
```shell
sudo mkdir /mnt/$(DRIVE_NAME)
``` 

3. Edit config
```shell title:/etc/fstab
UUID=[DRIVE_UUID] [MOUNT_POINT] [PARTITION_FS] defaults 0 0 
```

# Time & Date
## NTP
> SEE: [Arch Wiki: systemd-timesyncd](https://wiki.archlinux.org/title/Systemd-timesyncd)

1. Edit config
```shell title:/etc/systemd/timesyncd.conf
NTP=stdtime.gov.hk
```
2. Enable NTP
```shell
timedatectl set-ntp true
```

# Locale
> SEE: [Arch Wiki: Locale](https://wiki.archlinux.org/title/Locale)

config: `/etc/locale.conf`