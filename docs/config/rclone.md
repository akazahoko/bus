# Rclone
> *Reference: [Rclone: OneDrive](https://rclone.org/onedrive/)*
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
rclone mount $(REMOTE_NAME): $(LOCAL_DIR) --vfs-cache-mode=full --file-perms=0777
```

## Auto-mount on startup 
Create a service 

```sh
[Unit]
Description=Rclone Mount Service
After=network-online.target
Wants=network-online.target

[Service]
Type=notify
User=user
Group=user
ExecStart=/usr/bin/rclone mount \
    #mount flags
ExecStop=/bin/fusermount -uz /mnt/rclone
Restart=on-failure
RestartSec=5

[Install]
WantedBy=multi-user.target
```