# Increase memory in virtual box

```bash
cd ~/VirtualBox VMs/YOUR_VM_NAME
```

```bash
VBoxManage modifyhd YOUR_HARD_DISK.vdi --resize 8096
```


- change disk size using special iso https://downloads.sourceforge.net/gparted/gparted-live-1.6.0-3-amd64.iso

in virtual machine ubuntu:
```bash
sudo pvresize /dev/sda3
```

```bash
sudo lvextend -l +100%FREE /dev/mapper/ubuntu--vg-ubuntu--lv
```

```bash 
sudo resize2fs /dev/mapper/ubuntu--vg-ubuntu--lv
```
