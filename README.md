##### Download adb tools: https://developer.android.com/tools/releases/platform-tools  
##### To connect (after enabling usb debugging and enable debugging on charge-only-mode)
```shell
adb kill-server
adb devices
```
##### To enter the shell:
```
adb shell
```
##### To add "LTE only" network mode in the phone settings: in the shell run:
```
settings put system hw_networkmode_preference 11
```
Then restart the device. if that did not work try again but put "9,3,2,1,11" in place of "11" and restart.   
##### To get the native network speed indicator without any app try this: in the adb shell
```
settings put system show_network_speed_enabled 1
```
