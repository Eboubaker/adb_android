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
## Settings
##### To add "LTE(4G) only" network mode in the phone settings: in the shell run:
```
settings put system hw_networkmode_preference 11
```
Then restart the device. if that did not work try again but put "9,3,2,1,11" in place of "11" and restart.   
##### To get the native network speed indicator without any app try this: in the adb shell
```
settings put system show_network_speed_enabled 1
```
## Tools
#### To toggle wifi hotspot
```
# wakeup
adb shell input keyevent 82
# swipe to prompt password
adb shell input swipe 500 1000 300 300
# input pin code mine is 15263, if you have password then you need to call enter command after but pin will auto unlock when correct
adb shell input text 15263
# open settings
adb shell am start -n com.android.settings/.TetherSettings
# choose first option
adb shell input keyevent 20
# click first option
adb shell input keyevent 66
```
> if hotspot not toggled add another `adb shell input keyevent 66`
