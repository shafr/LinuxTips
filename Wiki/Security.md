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
```
ssh-keygen -t rsa
ssh-copy-id user@123.45.56.78
```

[How To Set Up SSH Keys](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys--2)
[Ubuntu 16.04 ssh - agent refused](http://askubuntu.com/questions/762541/ubuntu-16-04-ssh-sign-and-send-pubkey-signing-failed-agent-refused-operation)
