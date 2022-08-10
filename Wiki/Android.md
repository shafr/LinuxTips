# Disable Bloatware from Android:
```
adb shell pm list packages -d
adb shell pm disable-user --user 0 <package>
adb shell pm enable <package>
```


# Color logs in ADB:
```
 adb logcat | logcat-colorize 
 ```
 
 # Find app name after it had started:
 ```
  adb logcat | logcat-colorize | grep START
  ```
