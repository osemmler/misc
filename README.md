# Oprava GRUB

Pripojit pres live cd

```
sudo mount /dev/nvme0n1p5 /mnt
for i in /sys /proc /run /dev; do sudo mount --rbind "$i" "/mnt$i"; done
sudo mount /dev/nvme0n1p1 /mnt/boot/efi
sudo chroot /mnt
grub-install /dev/nvme0n1
update-grub
exit
sudo reboot
```

Based on https://askubuntu.com/questions/88384/how-can-i-repair-grub-how-to-get-ubuntu-back-after-installing-windows

# Smerovani VPN

```
sudo ip route add default via 192.168.1.1
sudo ip route add <vpn-network>/8 via 0.0.0.0 dev tun0
sudo ip route add <vpn-network>/8 via 0.0.0.0 dev tun0
...
```
