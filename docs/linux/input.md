# Fcitx
## Packages
- Base
  - fcitx5 -- base IME
  - fcitx5-configtool -- config gui
  - fcitx5-gtk -- gtk support
  - fcitx5-qt -- qt support
  - kcm-fcitx5 (KDE config)
- Chinese
  - fcitx5-table-extra - Cangjie
  - fcitx5-rime
- Japanese 
  - fcitx5-mozc - Google IME 
## Setup
Add environment variables:
```
GTK_IM_MODULE=fcitx
QT_IM_MODULE=fcitx
XMODIFIERS="@im=fcitx"
```
Execute on start
```
fcitx5 -r -d
```
## See 
- [Arch Wiki: Fcitx5](https://wiki.archlinux.org/title/Fcitx5)
- [Fcitx5 Wiki: IME](https://fcitx-im.org/wiki/Input_method_engines)
- [Rime | 中州韻輸入法引擎](https://rime.im/)