# ADB

## Detect adb devices without root

## Install app, launch it and turn on the screen

```sh
./gradlew --info installDebug && adb shell am start -a android.intent.action.MAIN -c android.intent.category.LAUNCHER com.story8.android.gallery && adb shell input keyevent 82
```