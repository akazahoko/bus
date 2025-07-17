# Input Method

## Packages
- IME base
  - `fcitx5` -- base IME
  - `fcitx5-configtool` -- config gui
  - `fcitx5-gtk` -- gtk support
  - `fcitx5-qt` -- qt support
  - `kcm-fcitx5` (KDE config)
- Chinese support
  - `fcitx5-rime`
  - `fcitx5-table-extra` - Cangjie
- Japanese support 
  - `fcitx5-mozc` - Google IME 

## Hyprland
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

## Reference 
- [Arch Wiki: Fcitx5](https://wiki.archlinux.org/title/Fcitx5)
- [Fcitx5 Wiki: IME](https://fcitx-im.org/wiki/Input_method_engines)
- [Rime | 中州韻輸入法引擎](https://rime.im/)
