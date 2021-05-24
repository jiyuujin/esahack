# Flutter

Set the config at `.zshrc` to prepare for the environment

```bash
sudo vi ~/.zshrc

# ~/.zshrc
export PATH="$PATH:/Users/<User名に置き換える>/project/flutter/bin"

source ~/.zshrc
```

## Install editors

- Android Studio
- VSCode

### Install Android Studio

Install according to the instructions of the installation wizard　from [DOWNLOAD ANDROID STUDIO](https://developer.android.com/studio/?hl=ja). The SDK installation wizard appears at the first startup, but select Standard and install with the default settings

#### Check license

If you are using Windows, start `C:\src\flutterflutter_console.bat` and hit it there

```bash
flutter doctor --android-licenses
```

#### Install plugins

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

### Install VSCode

Install according to the instructions of the installation wizard　from [Download Visual Studio Code](https://code.visualstudio.com/download). The SDK installation wizard appears at the first startup, but select Standard and install with the default settings

#### Check license

If you are using Windows, start `C:\src\flutterflutter_console.bat` and hit it there

```bash
flutter doctor --android-licenses
```

### Install plugins

When installing the Flutter plugin, you will be asked if you want to install the Dart plugin as well, so install it as well

Search for `flutter` in the search box, select the Flutter plugin provided by the official flutter.io and press Install to install the Flutter

![](https://i.imgur.com/XbfWT6W.jpg)

Also search for Dart plugins

![](https://i.imgur.com/tEcypad.jpg)

Confirm languages

- Swift
- Kotlin

![](https://i.imgur.com/wWraX9v.jpg)

Press `No device` to start AVD Manager, and select AVD manager

![](https://i.imgur.com/jhsoa5d.jpg)

## Create desktop applications

Install Flutter with platform such as Windows, macOS and Linux

```bash
flutter create --platforms=windows,macos,linux .
```

### Run applications

Start from the command on macOS

```bash
flutter run -d macos
```

### Build for release

Build the app for release

```bash
flutter build macos
```

## Reference

[Add desktop support to an existing Flutter app](https://flutter.dev/desktop#add-desktop-support-to-an-existing-flutter-app)
