

# Version Cheat Sheet

| Name                     | Version     | Information                  |
| :---                     |    :----:   |          ---:                |
| iOS Platform             | 6.2.0       | -                            |
| Android Platform         | 10.1.1      | -                            |
| Cordova CLI              | 11.0.0      | cordova plugin ionic webview |
| cordova-ios              | 6.2.0       | -                            |
| cordova-android          | 10.1.1      | -                            |
| text                |       | -              |
| text                |       | -              |
| text                |       | -              |


# Useful Commands

`npm ls <package name>`

`ionic info`
`ionic cordova emulate --list`


`$ sudo apt-get install gradle`


// Display the JDK version
`javac -version`
// Display the JRE version
java -version


# Important Resources

## Downloads
1. 
2. [Java 8 Download](https://www.oracle.com/java/technologies/downloads/#java8-mac)

## Documentation 
1. [Ionic Docs](https://ionicframework.com/docs/)
2. [Cordova Docs](https://cordova.apache.org/docs/en/11.x/guide/overview/index.html)
3. [Gradle Docs](https://docs.gradle.org/current/userguide/userguide.html)
4. [Xamarin.Android](https://docs.microsoft.com/en-us/xamarin/android/)
5. [Android Studio](https://developer.android.com/studio/intro)
6. [A full history of macOS (OS X) release dates and rates](https://robservatory.com/a-full-history-of-macos-os-x-release-dates-and-rates/)
7. [Ionic Web View](https://github.com/ionic-team/cordova-plugin-ionic-webview)

# GOTCHAS

## config.xml
1. [resource-file](https://cordova.apache.org/docs/en/latest/config_ref/#resource-file) - This tag is currently only supported on cordova-ios@4.4.0 or greater and cordova-android@6.2.1 or greater. Run `cordova platforms ls` and check against version sheet above. 


## Cordova
1. Running `ionic cordova emulate --list` you'll see this error in the Android section. [ERR_UNSUPPORTED_API_LEVEL](https://github.com/ionic-team/native-run/wiki/Android-Errors#err_unsupported_api_level) `native-run` supports SDK version 31





<br><br><br><br>








1. android cordova 
## Android

npm install -g native-run
npm install -g cordova
npm install -g ios-sim

[install the Android SDK](https://stackoverflow.com/questions/29391511/where-is-android-sdk-root-and-how-do-i-set-it/30900424#30900424) - I'm on 17.0.2


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

While running an emulation of a phone and running this command
ionic cordova run android --livereload

I was able to get the app to stick to the emulation device. This is a good sign, now how do I do that with the emulate command?

ionic cordova emulate ios - command still works perfect. Had to run a couple of commands to update the config.xml file though
* cordova plugin save
* cordova platform rm ios
* cordova platform add ios
then I ran the emulation command, problem solved. 

Ran command with ionic cordova emulate android --livereload --no-native-run

This worked?

tried to run ionic cordova emulate ios --livereload --no-native-run 

ERROR: Failed to load webpage with error: Could not connect to the server

SOLUTION: [ionic cordova build ios](https://stackoverflow.com/questions/26314005/ionic-failed-to-load-webpage-with-error-could-not-connect-to-the-server)

ran ionic cordova emulate ios --livereload --no-native-run

ERROR: the app won't live reload and so I think I need to run through the installation steps for ios just to make sure I have everything. 

## iOS

2. Install iOS cordova
<-- CURRENT HEAD -->

https://ionicframework.com/docs/developing/ios

$ npm install -g ios-sim
$ brew install ios-deploy
$ ionic cordova prepare ios

ionic cordova prepare ios - want to get it ready for emulation

ionic cordova run ios -l --external

ERROR: Failed to load webpage with error: Could not connect to the server

[SOLUTION 1:](https://stackoverflow.com/questions/26314005/ionic-failed-to-load-webpage-with-error-could-not-connect-to-the-server)

ionic cordova build ios

ionic cordova run ios -l --external

ERROR: CONNECTION REFUSED 
when I ran this command with `ionic cordova emulate android --livereload --no-native-run`
then opened Android Studio I got the error
Pressed the run button on pixel 4
And then got the error above

ERR_NO_TARGET: No target devices/emulators available.

SOLUTION: You remove the API level that it doesn't support and also add in a phone that would support the level API. So I also created a new phone with the appropriate configurations.


# FINAL

Run these commands:
* $ ionic cordova run android -l
* $ ionic cordova run ios -l













2. Install Intercom

## [Installation Guide](https://developers.intercom.com/installing-intercom/docs/react-native-installation)

3. Test Intercom

## [Message Rules](https://www.intercom.com/help/en/articles/5296455-message-rules-when-how-and-to-whom-should-a-message-be-sent)


4. Build More features

## [API](https://developers.intercom.com/intercom-api-reference/reference/create-contact)





