# Set as default
```shell
chsh -s #shell#
```

# Customizing zsh
## oh-my-zsh
### Install oh-my-zsh
```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
### Plugins
- Auto Suggestions
```shell
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
(add `zsh-autosuggestions` to plugin list inside `~/.zshrc`)

- Syntax Highlighting
```shell
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
echo "source ${(q-)PWD}/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc
```
- [Other plugins](https://github.com/ohmyzsh/ohmyzsh/wiki/plugins)

## Aliases
create alias for typing less, example:
```shell
alias zshrc="vim ~./zshrc"
```

# For More
- [Guide for installing ZSH](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH)
- [Guide for installing zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md)
- [Guide for installing zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md)

# Reference
- [ohmyzsh](https://github.com/ohmyzsh/ohmyzsh)
- [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)
- [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)