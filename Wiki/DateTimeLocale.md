## change system locale
```
localectl set-locale LANG=en_US.utf8
```

## SET DATE
```
date -s '2015-12-21 23:26:00'
```
## Update time/system clock
```bash
TIME:
date +%T -s "10:13:13"
DATE:
date +%Y%m%d -s "20151214"
after time is set
hwclock -w
```
## Change timezone