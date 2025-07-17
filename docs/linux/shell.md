# Generals
## Aliases
create alias for typing less, example:
```shell
alias zshrc="vim ~./zshrc"
```
## Change default shell
```shell
chsh -s <shell>
```

# Zsh
## oh-my-zsh
Install [oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh)
```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
## Plugins
- [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)
```shell
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
(add `zsh-autosuggestions` to plugin list inside `~/.zshrc`)

- [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)
```shell
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
echo "source ${(q-)PWD}/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc
```
- [Other plugins](https://github.com/ohmyzsh/ohmyzsh/wiki/plugins)
