# Setup
## Change default shell
```shell
chsh -s <shell>
```
# Zsh
## Configs
Directory tree:
```
$HOME
├── .zshenv
└── .config/zsh/
	├── .zshenv
	├── .zprofile
	├── .zshrc
	├── .zlogin
	└── .zlogout
```
loading order: `zshenv` -> `zprofile` -> `zshrc` -> `zlogin` -> `zlogout`
## Customization: oh-my-zsh
[Github: oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh)
```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
### Plugins
- [Github: zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)
```shell
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
(add `zsh-autosuggestions` to plugin list inside `~/.zshrc`)

- [Github: zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)
```shell
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
echo "source ${(q-)PWD}/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc
```
- [Other plugins](https://github.com/ohmyzsh/ohmyzsh/wiki/plugins)
### Theme
- [Github: Powerlevel10k](https://github.com/romkatv/powerlevel10k)
```shell
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git "${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k"
```
