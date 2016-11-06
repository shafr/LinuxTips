## CHANGE hostname:
[Instruction](https://www.vultr.com/docs/how-to-change-your-hostname-on-centos)

```bash
hostname <newhostname>
mcedit /etc/hosts (127.0.0.1 <hostname>)
mcedit /etc/hostname
mcedit /etc/sysconfig/network (set HOSTNAME=<hostname>)
```

## Find IP of machine
```bash
hostname -I
```