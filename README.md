# Getting Started

- [Getting Started](#getting-started)
  - [What you need](#what-you-need)
    - [Getting the apk](#getting-the-apk)
- [Start modding](#start-modding)
  - [Setup](#setup)
  - [Modding `water.db`](#modding-waterdb)
  - [Modding levels](#modding-levels)
    - [The `png` file](#the-png-file)
    - [The `xml` file](#the-xml-file)
- [Finishing the mod](#finishing-the-mod)


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

`water.db` is where all the data for the game is stored, such as level info, collectables, default settings and more. This is not needed to mod, but it's important to know if you want to change the name of a level, and/or the path to it. `water-lite.db` and `water-demo.db` are similar, but they hold the data for the lite and demo versions. If you have the full apk, you won't need to modify these.

Alright, let's get started.

In Apk Editor Studio (apk editor), click `Open Contents`. All the assets are in the `assets` folder. The later games tend to have the assets be in `assets/game-name`, such as `assets/perry`. `water.db` may also be under a different name, but it should be pretty easy to figure out. `water.db` is located in `assets/Data/water.db`.

Open `water.db` in DB Browser. This is where all the editing is going to be.

DB Browser is kind of weird. You need to go into the `Browse Data` tab to edit the contents. There are many different tables, some notable ones are, `HubInfo`, `LevelInfo`, `LevelPackInfo`, and `PlayerData`.

To edit a cell, just double click it. It will edit in another view. Once you're done editing the cell, you need to click apply. Alternately, you can just click the cell, and start typing to edit it directly. It will edit it in the cell, and when you click out of it, it will save, just like google sheets.

## Modding levels

Now here comes the fun part, editing the levels.

The levels are stored in `assets/Levels`. Each level has an `xml` and `png` file.

### The `png` file

This file is where all the liquids and terrain is defined. This can be edited in any image editor, although saving is a bit specific. The bit depth has to be 8-bit, so you need to be able to save the file to a specific bit depth. I recommend [Paint.net](https://getpaint.net/), although photoshop might also work. The image has a width of 90px, and usually has a height of 120px, although levels can have a bigger or smaller height. I'm not sure if the width can be bigger of smaller than 90px, but I'm pretty sure it can be.

Here's the color mapping

<img width="60%" src="images/color%20mapping.png">

This image can be found at `assets/Levels/LevelEditor.psd`. To open it in pain.net, you need the [PSD Plugin](https://www.psdplugin.com/). It will open just fine in PhotoShop since it's a PhotoShop file.

### The `xml` file

This is where all the objects and level metadata are defined. To make the editing experience better, it's best to use [Where's My Editor](https://github.com/wmw-modding/wheres-my-editor), (WIP).

More will be explained at a later date.

# Finishing the mod

Alright, it's time to test the mod.

You first need to make sure everything is saved. Then in APK Editor, open the key manager. Make sure you have a keystore with the correct details entered. If you didn't create one, then you should. Once you made sure you have a keystore file setup, just click on the box (save APK) next to the folder (Open APK), or file > Save APK. Enter the location you want to save the APK to.

Once it's finished saving, copy the APK onto your device. If you have ADB setup, you should be able to click `Install APK` to install it directly to your device. If that doesn't work, you can open a command prompt and enter
```
adb uninstall com.disney.WMW
adb install file.apk
```
(uninstall the app first to avoid errors when installing)

You're now all set to open the app, and see if your mod worked!
