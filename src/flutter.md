# Flutter

## Prepare for the Flutter environment

Set the config at `.zshrc`

```bash
sudo vi ~/.zshrc

# ~/.zshrc
export PATH="$PATH:/Users/<User名に置き換える>/project/flutter/bin"

source ~/.zshrc
```

## Install Android Studio

Install according to the instructions of the installation wizard　from [DOWNLOAD ANDROID STUDIO](https://developer.android.com/studio/?hl=ja). The SDK installation wizard appears at the first startup, but select Standard and install with the default settings

### Check license

If you are using Windows, start `C: \ src \ flutterflutter_console.bat` and hit it there

```bash
flutter doctor --android-licenses
```

## Flutter Plugins

When installing the Flutter plugin, you will be asked if you want to install the Dart plugin as well, so install it as well

Start Android Studio. The SDK installation wizard appears at the first startup, but select Standard. Install with default settings Start Android Studio

![](https://i.imgur.com/1Eqwm4n.jpg)

Press `configure`. A menu list should be displayed, so select `Plugins`

![](https://i.imgur.com/NI9E46H.jpg)

Search for `flutter` in the search box, select the Flutter plugin provided by the official flutter.io and press Install to install the Flutter

![](https://i.imgur.com/bSPTVY5.png)

Also search for Dart plugins

![](https://i.imgur.com/3uZ1lPx.png)

Press `configure` to start AVD Manager, and press `create virtual device`

![](https://i.imgur.com/V1ljhWf.jpg)

Select `Pixel2` and press` next`

![](https://i.imgur.com/Zok0WgT.jpg)

You will be asked for the API level of the system image, so select `29 (Q)` and press `next`. At this time, if SystemImage has not been downloaded, it should be displayed as `Download` in ReleaseName, so download it

![](https://i.imgur.com/fQDeoIp.jpg)

Press `finish`

![](https://i.imgur.com/DEVlzLk.jpg)
