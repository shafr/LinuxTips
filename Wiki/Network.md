## Bash get external IP address:
curl -s http://whatismijnip.nl |cut -d " " -f 5

## Open Port
```
firewall-cmd --list-all

firewall-cmd --permanent --add-port=80/tcp
firewall-cmd --permanent --remove-port=8080/tcp
firewall-cmd --permanent --remove-port=8443/tcp

firewall-cmd --reload

firewall-cmd --add-port=6011/tcp
```

## Port forwarding
[Source](https://www.linode.com/docs/security/firewalls/introduction-to-firewalld-on-centos)
```bash
sudo firewall-cmd --zone=public --permanent --add-forward-port=port=80:proto=tcp:toport=8080
sudo firewall-cmd --zone=public --permanent --add-forward-port=port=443:proto=tcp:toport=8443
sudo firewall-cmd --list-all
sudo firewall-cmd --reload

sudo firewall-cmd --remove-forward-port=port=8080:proto=tcp:toport=80:toaddr=127.0.0.1
```

## Monitor port
```
nc -l -p 80
```

## Minimal HTTP server
```
python -m SimpleHTTPServer <port>
```

## Traceroute
```
yum install traceroute
```

## See what ports are used by specific ports (works in Docker as well)
ss -l -p -n | grep <PID>
  
## netstat: command not found
```bash
apt-get install net-tools
```

## Connect OpenVPN in background:
```bash
(sudo ./openvpn --config vpnConfig.ovpn) &
```