# Disable Bloatware from Android:
```
adb shell 
pm list packages -d
pm disable-user --user 0 <package>
pm enable <package>
```


# Color logs in ADB:
```
 adb logcat | logcat-colorize 
 ```
 
 # Find app name after it had started:
```
adb logcat | logcat-colorize | grep START
```

# Fix issues with Fastboot not working (insufficient permissions for device: udev requires plugdev group membership?)
https://lynxbee.com/solved-no-permissions-user-in-plugdev-group-are-your-udev-rules-wrong/

# Fix unreadable storage in Android TWRP
https://forum.xda-developers.com/t/how-to-fix-unable-to-mount-data-internal-storage-0mb-in-twrp-permanently.3830897/
