# `systemd`
## Reload daemon
```shell
sudo systemctl daemon-reload
```

# `fstab`
> PATH: `/etc/fstab`
1. Find drive UUID
```shell
sudo blkid
```

2. Create mount point
```shell
sudo mkdir /mnt/$(DRIVE_NAME)
``` 

3. Edit fstab
```shell
UUID=$(DRIVE_UUID) $(MOUNT_POINT) $(PARTITION_FS) defaults 0 0 
```

4. [Reload `systemd`](#reload-daemon)