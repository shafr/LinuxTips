# Disable Bloatware from Android:
```
adb shell pm list packages -d
adb shell pm disable-user --user 0 <package>
adb shell pm enable <package>
```
