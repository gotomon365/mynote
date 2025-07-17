# about install arch linux
0. Download your iso 1
1. Boot from the .iso (either in VirtualBox or by making a bootable USB) 
	1. timedatectl set-ntp trun
2. Partition your disks 
	1. lsbllk -> check the blk
	2. cfdisk /etc/sda
3. Format your disks (ext4 for boot and root) 
	1. mkfs.ext4 /dev/sda1
	2. mkfs.ext4 /dev/sda2
4. Mount your disks 
	1. mount /dev/sda2 /mnt
	2. mkdir /mnt/boot
	3. mount /dev/sda1 /mnt/boot
5. pacstrap /mnt base base-devel linux linux-firmware vim 
6. Generate your fstab file genfstab -U /mnt export to /mnt/etc/fstab 
	1. genfstab -U /mnt >> /mnt/etc/fstab
7. Chroot into Arch arch-chroot /mnt 
	1. arch-chroot /mnt /bin/bash
8. Install grub and network manager pacman -S networkmanager grub 
9. Make network manager run at startup
	1. systemctl enable NetworkManager 
10. Configure Grub 
	1. grub-install /dev/sda  
	2. grub-mkconfig -o /boot/grub/grub.cfg 
11. set password for root user 
12. Configure local and timezone 
	1. vim /etc/locale.gen -> set zh_TW ...
	2. locale-gen
	3. vim /etc/locale.conf
	4. vim /etc/hostname -> 
	5. ln -sf /usr/share/zoneinfo/Asia/Taipei /etc/localtime
13. exit chroot, unmount, and reboot into your arch environment
	1. umount -R /mnt
---
# after install arch linux
1. vim /etc/pacman.conf
		1. ILoveCandy 
		2. Color 