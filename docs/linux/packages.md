# Package Managers

- [Package Managers](#package-managers)
  - [Arch](#arch)
    - [Arch User Repository (AUR)](#arch-user-repository-aur)
  - [Fedora](#fedora)
    - [RPM Fusion](#rpm-fusion)
  - [Mac OS](#mac-os)


## Arch
Manager: `pacman`

Sync:
```shell
pacman -S               # sync local database with repos
pacman -Ss <package>    # search package on repos
pacman -Si <package>    # show package info on repos
pacman -Su <package>    # sync packages with repos ONLY (NOT RECOMMENDED)
pacman -Syu <package>   # sync database & packages with repos
pacman -Syyu            # force resync (SLOW)
```
Query:
```shell
pacman -Q <package>     # query local packages
pacman -Qi <package>    # 
```
### Arch User Repository (AUR)
Manager: `yay`, `paru`

Install:

## Fedora
Manager: `dnf`, `yum`
 
Usage: 
```shell
dnf search <package>    # search package

dnf update              # update local database
dnf install <package>   # install package
dnf remove <package>    # remove package

dnf upgrade             # upgrade all packages
dnf upgrade <package>   # upgrade package
```

### RPM Fusion
Enable RPM Fusion Repo
```shell
sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```
Install Nvidia driver
```shell
sudo dnf install akmod-nvidia
sudo dnf install xorg-x11-drv-nvidia-cuda # (Optional) CUDA/NVDEC/NVENC
```
Fix H.264
```shell
dnf swap ffmpeg ffmpeg-free --allowerasing
sudo dnf update @multimedia --setopt="install_weak_deps=False" --exclude=PackageKit-gstreamer-plugin # Install additional codec
```

## Mac OS
Manager: 
- [Homebrew](https://brew.sh/)
- [Cask Upgrade](https://github.com/buo/homebrew-cask-upgrade)

Install:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
Usage: 
```shell
brew search <package>   # search package on repo
brew info <package>     # show package info on repo

brew list               # list current installed packages
brew tap                # list 3rd party repos

brew update             # update local database with repos
brew install <package>  # install package
brew remove <package>   # remove package

brew upgrade            # upgrade all packages (formulae)
brew upgrade <package>  # update specific package
brew cu                 # upgrade all casks

```