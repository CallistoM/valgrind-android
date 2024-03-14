# valgrind-android

This repo provides the valgrind binary package for **Android ARMv7**.

Versions used to compile valgrind.

- NDK version 20
    - https://dl.google.com/android/repository/android-ndk-r20b-linux-x86_64.zip
- Valgrind version 3.22

# Download

## Android

arm-v7 build with ndk r20b

# Usage

* Pull git project
```
git clone https://github.com/CallistoM/valgrind-android.git
```

* Extract archive and push files to android device
```
adb push inst /tmp
adb shell
```

* Run valgrind normally inside ADB shell
```
cd /tmp
export VALGRIND_LIB=/tmp/inst/libexec/valgrind
inst/bin/valgrind --leak-check=full --log=valgrind-out.txt ./executable_name
```

* Pull valgrind output to check memory leaks or use cat
```
adb pull /tmp/valgrind-out.txt 
```
* Cat version
```
adb shell
cat /tmp/valgrind-out.txt
```