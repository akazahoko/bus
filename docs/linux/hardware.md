# Fans
1. Setup sensors
```shell
sudo dnf install lm_sensors
sudo sensors-detect
```
2. Install [coolerControl](https://docs.coolercontrol.org/)
```shell
sudo dnf install dnf-plugins-core
sudo dnf copr enable codifryed/CoolerControl
sudo dnf install coolercontrol
sudo systemctl enable --now coolercontrold
```

# RGB

# Steering Wheel

# VR

# Speakers
