# Basic setup
## SSH
1. Create `id_rsa.pub`
```shell
ssh-keygen -t rsa -C "#email#"
```
- `-t` key type
- `-C` comment

(leave everything else empty should work fine)

2. Copy generated SSH key to [Github](https://github.com/settings/ssh/new)
```shell
cat ~/.ssh/id_rsa.pub
```