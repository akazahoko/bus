# DNF
*sudo when install/remove/update*
- Install (from repo/path)
```shell
dnf install #package-to-install#
```
- Remove
```shell
dnf remove #package-to-remove#
```
- Search package from repos
```shell
dnf search #package-to-search#
```
- Update system
```shell
dnf update
```
## RPM Fusion
### Enable RPM Fusion with DNF:
```shell
sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```
### Install Nvidia Driver
**!Update system first!**

Install Driver 
```shell
sudo dnf install akmod-nvidia
```
Install CUDA/NVDEC/NVENC (Optional)
```shell
sudo dnf install xorg-x11-drv-nvidia-cuda
```

### Fix H.264 Codec
```shell
dnf swap ffmpeg ffmpeg-free --allowerasing
```
Install additional codec
```shell
sudo dnf update @multimedia --setopt="install_weak_deps=False" --exclude=PackageKit-gstreamer-plugin
```

# Flatpak
## Install
- enable flathub repo (fedora)
```shell
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```

# References
- [Flatpak Quick Setup](https://flatpak.org/setup/)
- [RPM Fusion](https://rpmfusion.org/)
- [Nvidia Driver](https://rpmfusion.org/Howto/NVIDIA)