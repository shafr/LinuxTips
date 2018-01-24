# Bash trace script execution

###Using bash:
```bash
bash -x myscript.sh
```

### Enable
```bash
set -o xtrace
```

### Disable
```bash
set +o xtrace
```

## Grep
[Grep OR](http://www.thegeekstuff.com/2011/10/grep-or-and-not-operators/)
```bash
grep -E 'pattern1|pattern2' filename
```

## Remove files except some
```bash
ls | grep -v file.txt | xargs rm
```
