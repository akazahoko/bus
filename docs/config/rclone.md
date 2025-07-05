# Rclone

## Setup  
```shell
rclone config
```

## Remote
- Check Remote
```shell
rclone lsd $(REMOTE_NAME): # List Top Directory
rclone ls $(REMOTE_NAME):  # List every files
```
- Copy to Remote
```shell
rclone copy $(LOCAL_DIR) $(REMOTE_NAME):
```
- Mount remote to local
```shell
rclone mount $(REMOTE_NAME): $(LOCAL_DIR) --vfs-cache-mode=full
```

## Auto-mount on startup 
Create a service 

## Reference
[Rclone: OneDrive](https://rclone.org/onedrive/)