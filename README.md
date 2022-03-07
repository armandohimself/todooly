

# Version Cheat Sheet

| Name                     | Version     | Information    |
| :---                     |    :----:   |          ---:  |
| iOS Platform             | 6.2.0       | -              |
| Android Platform         | 10.1.1      | -              |
| text                |       | -              |
| text                |       | -              |
| text                |       | -              |
| text                |       | -              |
| text                |       | -              |



# Important Resources

## Downloads
1. 
2. [Java 8 Download](https://www.oracle.com/java/technologies/downloads/#java8-mac)

## Documentation 
1. [Ionic Docs](https://ionicframework.com/docs/)
2. [Cordova Docs](https://cordova.apache.org/docs/en/11.x/guide/overview/index.html)
3. [Gradle Docs](https://docs.gradle.org/current/userguide/userguide.html)
4. [Android Studio](https://developer.android.com/studio/intro)
5. 

# GOTCHAS

## config.xml
1. [resource-file](https://cordova.apache.org/docs/en/latest/config_ref/#resource-file) - This tag is currently only supported on cordova-ios@4.4.0 or greater and cordova-android@6.2.1 or greater. Run `cordova platforms ls` and check against version sheet above. 





<br><br><br><br>


1. Get Cordova Running on: 


## iOS


## Android

npm install -g native-run
npm install -g cordova
npm install -g ios-sim

[install the Android SDK](https://stackoverflow.com/questions/29391511/where-is-android-sdk-root-and-how-do-i-set-it/30900424#30900424) - I'm on 17.0.2

<-- CURRENT HEAD -->

Terminal Error: Could not find an installed version of Gradle either in Android Studio,
or on your system to install the gradle wrapper. Please include gradle 
in your path, or install Android Studio

Android Studio Error: No usable Android build tools found. Highest 30.x installed version is 30.0.2; minimum version required is 30.0.3.

https://stackoverflow.com/questions/70002327/ionic-cordova-android-no-usable-android-build-tools-found-highest-30-x-install

Need to remove all mention of the java jdk on your machine. So run the following commands. 

sudo rm -rf /Library/Java/JavaVirtualMachines/

sudo rm -rf /Library/PreferencePanes/JavaControlPanel.prefPane
sudo rm -rf /Library/Internet\ Plug-Ins/JavaAppletPlugin.plugin
sudo rm -rf ~/Library/Application\ Support/Oracle/Java

### We are restarting the installation process

Add these paths to your `/etc/paths` 
/usr/local/share/npm/bin 

# Exports added for Android Studio
export ANDROID_SDK_ROOT=$HOME/Library/Android/sdk

# avdmanager, sdkmanager
export PATH=$PATH:$ANDROID_SDK_ROOT/tools/bin
# adb, logcat
export PATH=$PATH:$ANDROID_SDK_ROOT/platform-tools
# emulator
export PATH=$PATH:$ANDROID_SDK_ROOT/emulator

# Gradle
export PATH=$PATH:/opt/gradle/gradle-7.4/bin

brew install gradle

ionic cordova prepare android

open the config.xml file and modify the id attribute of the root element, <widget>
com.todoolie.book identify
version 1.0.0 for initial setup

Updated name in config file to it's formal name displayed on home screen and within app store

$ ionic cordova run android -l

ERROR: No usable Android build tools found. Highest 30.x installed version is 30.0.2; minimum version required is 30.0.3.

[SOLUTION](https://stackoverflow.com/questions/70002327/ionic-cordova-android-no-usable-android-build-tools-found-highest-30-x-install)

LESSON: READ THINGS MORE CAREFULLY AND FOLLOW YOUR GUT

ERROR: Could not find tools.jar. Please check that /Library/Internet Plug-Ins/JavaAppletPlugin.plugin/Contents/Home contains a valid JDK installation.

[SOLUTION](https://stackoverflow.com/questions/64856188/ionic-cordova-android-build-error-could-not-find-tools-jar)
* /usr/libexec/java_home -V
* sudo rm -rf "/Library/Internet Plug-Ins/JavaAppletPlugin.plugin/"

Running both commands fails: 
* ionic cordova run android -l
* ionic cordova emulate android

ERROR: No hardware devices found, attempting emulator...

POSSIBLE SOLUTIONS
1. [read avd doc](https://developer.android.com/studio/run/managing-avds#create-manage-avds)
2. [continue reading what else emulation needs](https://developer.android.com/training/basics/firstapp/running-app)

Was able to press the play button on Android Studio but the build doesn't work. 


2. Install Intercom

## [Installation Guide](https://developers.intercom.com/installing-intercom/docs/react-native-installation)

3. Test Intercom

## [Message Rules](https://www.intercom.com/help/en/articles/5296455-message-rules-when-how-and-to-whom-should-a-message-be-sent)


4. Build More features

## [API](https://developers.intercom.com/intercom-api-reference/reference/create-contact)





