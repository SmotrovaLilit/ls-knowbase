# DNS in virtual box Ubuntu 20.04
```bash
sudo systemctl enable systemd-resolved.service
```

```bash
sudo vim /etc/netplan/00-installer-config.yaml
```
Add Google DNS: 
```yml
network:
  ethernets:
    enp0s3:
      dhcp4: true
      nameservers:
        addresses: [8.8.8.8, 8.8.4.4]
  version: 2
```

```bash
sudo netplan apply
```