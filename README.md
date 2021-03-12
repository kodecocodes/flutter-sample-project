# Flutter sample project

This repository is a mini-tutorial with the resources you need to create the sample project that will accompany your written tutorial.

## Sample project requirements

All projects for raywenderlich.com Flutter tutorials should include the following items:

- launch screen (Android and iOS)
- app icons for all sizes (Android, iOS, web)
- base app package name (Android, iOS)
- copyright notice
- linting file

The following directions will give further details on how to do that.

## Setup directions

Make sure you are on the stable channel with the most recent version of Flutter.

```
flutter channel stable
flutter upgrade
```

Then create a Flutter project using the base package name for raywenderlich.com. Replace `appname` with your project name.

```
flutter create --org com.raywenderlich appname
```

This is used for both the Android package name and the iOS bundle identifier.

### License

The guides require adding the license to the top of each code file, but many developers expect to find a file called LICENSE in the root of the project, also. So add that file in your project root. You can find the text for that file in this repository. Change the date to the current year if needed.

### Linting rules

Adding linting rules will help you to follow the Flutter team coding style and just write better code in general.

In **pubspec.yaml** add `effective_dart` to the dev dependencies:

```
dev_dependencies:
  effective_dart: ^1.0.0
```

Also add a file named **analysis_options.yaml** to the root of your project. Paste in the following options:

```
include: package:effective_dart/analysis_options.yaml

analyzer:
  exclude: [build/**]
  strong-mode:
    implicit-casts: false
    implicit-dynamic: false
```

This will let you know if you are not following the recommendations in the [Effective Dart](https://dart.dev/guides/language/effective-dart) guidelines.

### Update pubspec.yaml

Here is a checklist for things to pay attention to in pubspec.yaml:

- Set the app name and description.
- Set the minimum Dart SDK to 2.12.0 in order to take full advantage of sound null safety. The only reason you wouldn't do this is if your app absolutely requires a package that hasn't been upgraded to null safety.
- Remove all the default comments.

There is a sample pubspec.yaml file in the root of this repository for your guidance.

### .gitignore

When you create a new Flutter project it comes with a good `.gitignore` file. Go with what's in there. Also consider this a good list of things not to include when you upload your project to raywenderlich.com. 

**Hint**: If you develop your project with GitHub, all you have to do is download download it from GitHub and that will ensure that there are no unnecessary files in the project.

## Image assets

You need to add image assets for each platform that Flutter supports in stable.

### Android assets

You need to add an Android splash screen and launch icon. If you don't have your own custom ones that you are using for the app then you can use the standard raywenderlich.com ones.

To use the standard raywenderlich.com launcher and icons replace the contents of your project's **android/app/src/main/res** folder with the contents of the **android_assets/res** folder in this repository.

Run the app on an Android device or emulator to make sure the launch screen and launcher icon are working correctly.

### iOS assets

You also need to add an iOS splash screen and launch icon. To use the standard raywenderlich.com launcher and icons replace the contents of your project's **ios/Runner/Assets.xcassets** folder with the contents of the **ios_assets/Assets.xcassets** folder in this repository.

Run the app on an iOS device or simulator to make sure the launch screen and launcher icon are working correctly. If you don't have a Mac to check this, then mention that on the Trello card so that the TE or FPE can double check.

### Web assets

You should also add a favicon and other asset images for the web. To use the standard raywenderlich.com asset images go to your project's **web** folder and replace **favicon.png** and the contents of the **icons** folder with the image assets found in the **web_assets** folder in this repository.

Run the Flutter web app in a browser to make sure that the favicon shows in the browser tab at the top.

**Note**: If your project does not support the web, then delete the entire **web** folder.

## App display name

Rather than having your launcher icon use your project name, which might be something unsightly like `appname`, you should update the display name for each platform that Flutter supports.

### Android

Open **AndroidManifest.xml** in **android/app/src/main** and set the app display name by editing the `android:label` property. 

```
<application
     android:label="Super App"
```

This name will appear under the app's launch icon on the user's Android device.

### iOS

Open **Info.plist** in **ios/Runner** and set the app display name by editing the `CFBundleName` string property.

```
<dict>
	<key>CFBundleName</key>
	<string>Super App</string>
```

This name will appear under the app's launch icon on the user's iOS device.

### Web

Open **index.html** in the **web** folder of your project root. Then set the display name by editing the `title` property.

```
<head>
  <title>Super App</title>
```

This will change the display name used in the pages browser tab next to the favicon.

## Further notes

This guide is up to date for Flutter 2.0. When desktop versions enter the stable channel without the need for any special flags, then the required resources should be added for them as well.

Are there new Flutter updates that break this guide? Please open a GitHub issue or submit a pull request.