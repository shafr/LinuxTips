## change system locale
```
localectl set-locale LANG=en_US.utf8
```

## Set Date & Time
Sometimes you don't have access to NTP server (like corporate network) so you have to sync manually. 
You can get values from local linux machine:
```bash
date +%Y%m%d%T
date +%T 

```
## Update time/system clock
```bash
DATE:
date +%Y%m%d%T -s "20151214"

TIME:
date +%T -s "10:13:13"

After time is set (sync up with internal HW time)
hwclock -w
```
## Change timezone
```
sudo dpkg-reconfigure tzdata
```

## Update using NTP
```
sudo apt-get install ntpdate
sudo ntpdate 1.ro.pool.ntp.org
```
