LdcplHkp0bB9Zp1YjTZDDXNyeYOJy1T7KrLFgMZlNMXJs0cNcSsNkqRavbiu


## Mount USB Drive
```
# find where drive is mounted
sudo fdisk -l 

# mount drive
sudo mount /dev/sdb1 /media/backup/

# see mount options
mount | grep sdb1

# copy resulted stuff to /etc/fstab
```

## Unmount USB Drive
```
umount /media/backup
umount /dev/sdb1
```

## Reformat To different fs
```
sudo umount /dev/sdc1
sudo mkfs.ntfs /dev/sdb1
sudo mkfs.fat32 /dev/sdb1
sudo mkfs.ext4 /dev/sdb1
```
