![License GPLv3](https://img.shields.io/github/license/bmartin5692/bumper.svg?color=brightgreen)

# Bumper 

Bumper is a standalone and self-hosted implementation of the central server used by Ecovacs vacuum robots.  Bumper allows you to have full control of your Ecovacs robots, without the robots or app talking to the Ecovacs servers and transmitting data outside of your home.

![Bumper Diagram](./docs/images/BumperDiagram.png "Bumper Diagram")

**Note:** The current master branch is unstable, and in active development.

## Build Status

| Master Branch | Status                                                                 |
| ------------------- | ---------------------------------------------------------------------- |
| AppVeyor (Win32)    | [![AppVeyor branch](https://img.shields.io/appveyor/ci/bmartin5692/bumper/master?logo=appveyor)](https://ci.appveyor.com/project/bmartin5692/bumper/branch/master) |
| TravisCI (Linux)    | [![Travis (.org) branch](https://img.shields.io/travis/bmartin5692/bumper/master?logo=travis)](https://travis-ci.com/bmartin5692/bumper/branch/master) |
| Docker Hub	      | [![Docker Build](https://img.shields.io/docker/cloud/build/bmartin5692/bumper?logo=docker)](https://hub.docker.com/r/bmartin5692/bumper/branch/master) |
| CodeCov Coverage    | [![Codecov branch](https://img.shields.io/codecov/c/github/bmartin5692/bumper/master?logo=codecov)](https://codecov.io/gh/bmartin5692/bumper/branch/master) |


**Community**:
A Gitter community has been created for Bumper so users can chat and dig into issues outside of Github, join us here:
[![Gitter chat](https://badges.gitter.im/gitterHQ/gitter.png)](https://gitter.im/ecovacs-bumper/community)


***Testing needed***
Bumper needs users to assist with testing in order to ensure compatability as bumper moves forward!  If you've tested Bumper with your bot, please open an issue with details on success or issues.

***Please note**: this software is experimental and not ready for production use. Use at your own risk.* 

## Why?

For fun, mostly :)

But seriously, there are a several reasons for eliminating the central server:

1. Convenience: It works without an internet connection or if Ecovacs servers are down
2. Performance: No need for messages to travel to Ecovacs server and back.
3. Security: We can completely isolate the robot from the public Internet.
 
## Compatibility

As work to reverse the protocols and provide a self-hosted central server is still in progress, Bumper has had limited testing.  There are a number of EcoVacs models that it hasn't been tested against.  Bumper should be compatible with most wifi-enabled robots that use either the Ecovacs Android/iOS app or the Ecovacs Home Android/iOS app, but has only been reported to work on the below:

| Model           | Protocol Used | Bumper Version Tested | EcoVacs App Tested   |
| --------------- | ------------- | --------------------- | -------------------- |
| Deebot 900/901  | MQTT          | master                | Ecovacs/Ecovacs Home |
| Deebot 600      | MQTT          | master                | Ecovacs Home         |
| Deebot Ozmo 950 | MQTT          | master                | Ecovacs Home         |
| Deebot Ozmo 601 | XMPP          | master                | Ecovacs              |
| Deebot Ozmo 930 | XMPP          | master                | Ecovacs              |
| Deebot M81 Pro  | XMPP          | v0.1.0                | Ecovacs              |

## Documentation and Getting Started

See the documentation on [Read the Docs](https://bumper.readthedocs.io)

## Start with example file
1. Setup a linux system and install docker
2. clone repo into linux 
3. Navigate to example folder 
4. `docker docker-compose.yaml up`

## Howto convert CA Certificate into Android 12 readable file
1. open console
2. Navigate to folder with file ca.crt
3. `openssl x509 -in ca.crt -noout -text >> ca.crt`

## This is How You Can Easily Unlock Developer Options Running Android 12 (https://wccftech.com/how-to/how-to-unlock-developer-options-in-android-12-and-access-powerful-hidden-features/)
1. The first thing that you have to do is launch the Settings app.
2. Scroll down and tap on About Phone.
3. Now, scroll down to the end and tap on the Build Number seven times.
Unlock Developer Options in Android 12 Phones and Unlock Hidden tools and features
4. You will see the prompt telling you that "You are now a developer!"
5. You might be asked to enter your passcode to unlock developer options in Android 12.
This is all that you have to do to enable developer options. However, it is another method to access the unlocked developer options. Follow the instructions below to access developer options on Android 12.
1. Launch Settings.
2. Tap on System.
Unlock Developer Options in Android 12 on Google Pixel Phones and Unlock Hidden tools and features
3. Tap on Developer Options.
Unlock Developer Options in Android 12 on Google Pixel Phones and Unlock Hidden tools and features


## Howto install CA Certificate under Android 12 (https://www.youtube.com/watch?v=GERlhgCcoBc)
1. Download and extract SDK Platform Tools.
https://developer.android.com/studio/...
2. Create a folder named "Android" in "C:\" drive.
3. Copy and paste the "platform-tools" folder in "C:\Android".
4. Search for "This PC". Right click it and click "Properties". Scroll at the bottom and click "Advanced system settings". On the new window click "Environment Variables...".
5. Double click the "Path" variable in System variables. Click "New" and paste "C:\Android\platform-tools" as value. Now you have implemented ADB with Windows Terminal.
6. Turn on USB Debugging on your Android phone and connect it to your PC.
7. Open your terminal of choice, type "adb devices" and push ENTER.
8. Tap "Allow" on your phone.
9. Congrats. Now you can use the ADB commands you want!
---
### Thanks
A big thanks to the original project creator @torbjornaxelsson, without his work this project would have taken much longer to build. 

Bumper wouldn't exist without [Sucks](https://github.com/wpietri/sucks), an open source client for Ecovacs robots. Thanks to @wpietri and contributors!
