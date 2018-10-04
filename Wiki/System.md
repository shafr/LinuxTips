## Show systemctl as tree
```
systemd-cgls
```

## PS with groups:
```
alias psc='ps xawf -eo pid,user,cgroup,args'
psc
```


## How to schedule some task
### Create task file inside `/etc/systemd/system/task.service`
```bash
[Unit]
Description=Run some task

[Service]
Type=simple
User=saikek
WorkingDirectory=/home/saikek/
ExecStart=/home/saikek/task.sh
ExecStop=/bin/kill -15
```

### Create execute timer inside `/etc/systemd/system/task.timer`
```bash
[Unit]
Description=Execute some task daily at 09:00

[Timer]
OnCalendar=*-*-* 09:00:00

[Install]
WantedBy=multi-user.target
```

Note that `[Timer]` section can have different useful units:
```bash
OnBootSec=15min # start timer only 15 minutes after boot
OnUnitActiveSec=1min # Execute every minute
```