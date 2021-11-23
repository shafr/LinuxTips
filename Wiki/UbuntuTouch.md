## _apt user does not exist

```
sudo adduser _apt --force-badname
```
## cannot install apt applications - not enough space

```
umount /var/cache/apt/archives/
sudo mount -t tmpfs tmpfs /var/cache/apt/archives
```

## not able to get to bootlader (going back to android)
connect through usb-hub or usb2.0 port
