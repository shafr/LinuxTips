## PS1 update
[BashGenerator site](http://bashrcgenerator.com)
```bash
export PS1="\[\033[38;5;70m\]\A\[$(tput sgr0)\]\[\033[38;5;15m\] \[$(tput sgr0)\]\[\033[38;5;68m\]\u\[$(tput sgr0)\]\[\033[38;5;15m\] \[$(tput sgr0)\]\[\033[38;5;179m\]\w \[$(tput sgr0)\]"
with hostname:
export PS1="\[\033[38;5;22m\]\A\[$(tput sgr0)\]\[\033[38;5;15m\] \[$(tput sgr0)\]\[\033[38;5;1m\]\h\[$(tput sgr0)\]\[\033[38;5;15m\] \[$(tput sgr0)\]\[\033[38;5;178m\]\u\[$(tput sgr0)\]\[\033[38;5;15m\] \[$(tput sgr0)\]\[\033[38;5;62m\]\w\[$(tput sgr0)\]\[\033[38;5;15m\] \[$(tput sgr0)\]"
```

## set terminal FONT:
```
setfont CyrKoi-Terminus12x6
```

## Use zsh
```bash
sudo apt-get install zsh
git clone https://github.com/powerline/fonts.git ; ./install.sh

https://github.com/kagamilove0707/moonline.zsh

git clone https://github.com/kagamilove0707/moonline.zsh.git ~/.moonline
echo "test -f ~/.moonline/moonline.zsh && source ~/.moonline/moonline.zsh && moonline initialize" >> ~/.zshrc
source ~/.zshrc
```

## Add variable to PATH for ZRC:
```bash
Update `.zshrc` file, and add there:

JAVA_HOME="/opt/jdk1.8.0_101"
GRADLE_HOME="/opt/gradle-3.1"

PATH="$HOME/bin:$HOME/.local/bin:$PATH"
OAOAPATH=$JAVA_HOME/bin:$PATH
PATH=$GRADLE_HOME/bin:$PATH
```


## Dynmotd page example
```bash
/usr/local/bin/dynmotd
DYNMOTD:
#!/bin/bash

HOSTNAME=`uname -n`
HOME=`df -Ph | grep centos | awk '{print $4}' | tr -d '\n'`
MEMORY1=`free -t -m | grep "Mem" | awk '{print $3" MB";}'`
MEMORY2=`free -t -m | grep "Mem" | awk '{print $2" MB";}'`
PSA=`ps -Afl | wc -l`
WEATHER=`curl --silent "http://weather.yahooapis.com/forecastrss?u=c&w=796597" | grep condition | sed -r 's/.*temp=\"([-0-9]+).*/\1/'`

TOMCAT=`systemctl status tomcat | grep Active: | cut -b 12-`

#System uptime
uptime=`cat /proc/uptime | cut -f1 -d.`
upDays=$((uptime/60/60/24))
upHours=$((uptime/60/60%24))
upMins=$((uptime/60%60))
upSecs=$((uptime%60))

#System load
LOAD1=`cat /proc/loadavg | awk {'print $1'}`
LOAD5=`cat /proc/loadavg | awk {'print $2'}`
LOAD15=`cat /proc/loadavg | awk {'print $3'}`

FORTUNE=` fortune -s | cowsay`

echo \"
__        _______ _     ____ ___  __  __ _____    _   _  ___  __  __ _____ _
\ \      / / ____| |   / ___/ _ \|  \/  | ____|  | | | |/ _ \|  \/  | ____| |
 \ \ /\ / /|  _| | |  | |  | | | | |\/| |  _|    | |_| | | | | |\/| |  _| | |
  \ V  V / | |___| |__| |__| |_| | |  | | |___   |  _  | |_| | |  | | |___|_|
   \_/\_/  |_____|_____\____\___/|_|  |_|_____|  |_| |_|\___/|_|  |_|_____(_)

===========================================================================
 - Users...............: Currently `users | wc -w` user(s) logged on
 - System uptime.......: $upDays days $upHours hours $upMins minutes $upSecs seconds

 - CPU usage...........: $LOAD1, $LOAD5, $LOAD15 (1, 5, 15 min)
 - Memory used.........: $MEMORY1 / $MEMORY2
 - Processes...........: $PSA running
 - Disk space HOME.....: $HOME remaining
 - Tomcat..............: $TOMCAT
 - Weather.............: $WEATHER °C
===========================================================================
 $FORTUNE
==========================================================================
```