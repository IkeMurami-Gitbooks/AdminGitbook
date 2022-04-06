# Работа с флешками и другими монтированными устройствами

&#x20; lsblk - что примонтировано

запись iso на usb через dd:&#x20;

```
sudo dd bs=4M if=Downloads/ubuntu-19.04-desktop-amd64.iso of=/dev/sdb conv=fdatasync status=progress
```
