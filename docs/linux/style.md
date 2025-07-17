# Styling

## Fonts
### Noto Sans
- `noto-fonts`
- `noto-fonts-cjk` (CJK Support)
- `noto-fonts-emoji` (Emoji Support)
- `ttf-noto-nerd` (Nerd Fonts)

### Font Awesome (icon font)
`otf-font-awesome` ([cheat-sheet](https://fontawesome.com/search))

## Themes
### [Catppuccin](https://catppuccin.com/) (GTK/Qt)
(Available from AUR)
- GTK: `catpuuccin-gtk-theme-{flavor}`
- Qt: `catpuuccin-plasma-colorscheme-{flavor}`

Avaliable flavors:
- `latte` (White)
- `frappe` (Dark)
- `macchiato` (Darker)
- `mocha` (Darkest)

*Extra: [Catppuccin Color Palette](https://catppuccin.com/palette/)*, [Style guide](https://github.com/catppuccin/catppuccin/blob/main/docs/style-guide.md)

## Tool
- GTK2/3/4: `nwg-look`
- Qt5: `qt5ct-kde` (AUR)
- Qt6: `qt6ct-kde` (AUR)

## Fixes
### Reset GSettings
---
**SHOULD use front end for managing GTK themes** 

Reset Key:
```
gsettings reset SCHEMA [:PATH] KEY
```
Reset All:
```
gsettings list-schemas | xargs -n 1 gsettings reset-recursively
```