# Getting Started

- [Getting Started](#getting-started)
  - [What you need](#what-you-need)
    - [Getting the apk](#getting-the-apk)
- [Start modding](#start-modding)
  - [Setup](#setup)
  - [Modding `water.db`](#modding-waterdb)


## What you need

* Where's My Water apk
* [APK Editor Studio](https://github.com/kefir500/apk-editor-studio)
* [apktool](https://ibotpeaches.github.io/Apktool/install/)
* [apksigner](https://developer.android.com/studio) (unfortunately, you need to install android studio to get it).
* [adb](https://developer.android.com/studio/releases/platform-tools)
* [Java](https://www.java.com/)
* [DB Browser](https://sqlitebrowser.org/dl/)

### Getting the apk

1. Install the apk

    You need to first install it on an android device (could be an emulator). You can get it on [google play](https://play.google.com/store/apps/details?id=com.disney.WMW) for $1.99.
    
    You can also find it online if you can't buy it. This doesn't need to be installed, but it is a good idea to install it to make sure it works. BE CAREFUL WHEN DOWNLOADING APPS ONLINE!!

2. if you downloaded the apk online, then you can skip this step. This is only for getting an installed apk.

    You need to get an android file manager to get the apk. A file manager I recommend is [File Manager +](https://play.google.com/store/apps/details?id=com.alphainventor.filemanager). If you know how to do this another way, go ahead.

    Open the file manager and head over to the apps section

    <img width="30%" src="images/file%20manager%20plus.png">

    Once you're there, find "Water?", then tap and hold it to select the app

    <img width="30%" src="images/file%20manager%20apps.png">

    Once you've done that, all you need to do then is tap share, File Manager +, then select a detination folder.

    The filename will most likely be called `base.apk`, so you can go ahead and rename to make it easier to know what it is.

3. Copy it onto your computer

    To copy it to your computer, there are many different ways, but here's the way I recommend.

    Plug your device into your computer, then go into the new drive, and find your apk. You might have to enable USB Debugging (you can find that in developer settings). Once you've found the apk, you can copy it directly to your computer.

    You can do this though a cloud service, but I recommend doing it over USB as you'd be copying the apk to your device whenever you want to test the mod, which you do quite a lot.

    If you're on an emulator, then there's probobly some way to copy files to your pc without a cord.
    
# Start modding

## Setup
Before you start modding, you need to extract the apk, fortunately, APK Editor Studio has you covered.

To start, open APK Editor Studio. You will need to set some things up before we extract the apk.

Under Settings, click options.

- Go into the Java tab, click browse, and enter the Java directory.

- Go into the ApkTool tab. Set the path to `apktool.jar` that you downloaded. You should change the extraction path to something that is easier to access. Leave the frameworks path unchanged.

  If you want to modify the code, then select Decompile Source Code (smali).

- In the ApkSigner tab, enter the path to it.

  Open Android Studio. If you installed it for the first time, you probably downloaded the Android SDK Tools.
  
  If you didn't download it, then  go into settings, head over to Appearance & Behavior > System Settings > Android SDK, then go into the SDK Tools tab. Check `Android SDK Build Tools`, then click OK. It will then download it.
  
  The path to the SDK Build Tools is likely in `%localappdata%\Android\Sdk\build-tools\`. The path to `apksigner.jar` is `\lib\apksigner.jar`. I recommend copying the file to some other, easier to access folder.

  Once you have the path to ApkSigner, you should create a keystore. Open the Key Manager, then check custom keystore. After that click create (both buttons do the same thing). Enter the information (you can enter fake info). Only the passwords, alias, and name are required. Do not share the password(s).

  If it throws an error when you press ok, then you need to check that you entered the correct path to Java.

- Finally, you need to add the path to ADB in the ADB tab. This is only needed if you want to use the android explorer, or install the app directly to you device from this program.

Once you got that setup, it's time to unpack the apk.

Click on the folder icon, or file > Open APK. Select the wmw APK. It should decompress the apk after that.

You're now all set to start modding!

## Modding `water.db`
