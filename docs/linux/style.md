# Styling
## Qt
Packages: 
- qt5ct-kde<sup>aur</sup>
- qt6ct-kde<sup>aur</sup>
- kvantum (for qt6)
- kvantum-qt5 (for qt5)

Settings:
- In qt5-ct/qt6-ct, set the style to `kvantum`/`kvantum-dark`
- Set `QT_QPA_PLATFORMTHEME` as `qt6ct`
- In Kvantum, apply theme

## GTK
Packages:
- nwg-look

Just apply theme in nwg-look

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

Packages:
- catppuccin-gtk-theme-latte<sup>aur</sup>
- catppuccin-gtk-theme-frappe<sup>aur</sup>
- catppuccin-gtk-theme-macchiato<sup>aur</sup>
- catppuccin-gtk-theme-mocha<sup>aur</sup>
- kvantum-theme-catppucin-git<sup>aur</sup>

*Extra: [Catppuccin Color Palette](https://catppuccin.com/palette/), [Style guide](https://github.com/catppuccin/catppuccin/blob/main/docs/style-guide.md)*