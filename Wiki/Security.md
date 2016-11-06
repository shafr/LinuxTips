## Check login logs
tail -f /var/log/secure

## Disable ssh root login
```bash
mcedit /etc/ssh/sshd_config
PermitRootLogin no
/etc/init.d/sshd restart
```

## FAIL2Ban for SSH
http://blog.iopsl.com/fail2ban-on-centos-7-to-protect-ssh-part-i/

## MOVE SSH TO different port
sudo firewall-cmd --zone=public --permanent --add-forward-port=port=16162:proto=tcp:toport=22

### Connect SSH to different port:
ssh user@server -p port

## ssh login via KEY
TODO