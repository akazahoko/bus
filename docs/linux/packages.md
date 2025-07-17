# Package Managers

## Arch
Manager: 
- Official: `pacman`
- Arch User Repository (AUR): `yay`, `paru`

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

## Mac OS
Manager: 
- [Homebrew](https://brew.sh/)
- [Cask Upgrade](https://github.com/buo/homebrew-cask-upgrade)
```bash
# Install
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