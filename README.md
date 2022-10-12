# Flutter sample project

This repository is a mini-tutorial to help you create the sample app for your tutorial on kodeco.com. The repository here includes the resources you'll need to make your app look good wherever your readers build the app.

## Sample project requirements

All projects for kodeco.com Flutter tutorials should include the following items:

- com.kodeco base package name (Android, iOS)
- Kodeco license
- Flutter team linting rules
- A clean **pubspec.yaml** file
- Splash screen (Android and iOS)
- App icons for all sizes (Android, iOS, web)
- App display name

The following directions will give further details on how to do that.

## General setup

In this section you create your sample app with settings that will apply to all platforms.

### Use the stable channel

Make sure you're on the stable channel with the most recent version of Flutter.

```
flutter channel stable
flutter upgrade
```

### Set the base package name

Next create a Flutter project using the base package name for **kodeco.com** in reverse notation. 

```
flutter create --org com.kodeco appname
```

Replace `appname` with your project name. This is used for both the Android package name and the iOS bundle identifier.

### Add the Kodeco license

The guides require adding the license to the top of each code file, but many developers expect to find a file called **LICENSE** in the root of the project also. So create that file. You can find the [text for the file in this repository](https://github.com/raywenderlich/flutter-sample-project/blob/master/LICENSE). Change the date to the current year if needed.

### Set up linting rules

Adding linting rules will help you to follow the Flutter team coding style and just write better code in general.

Add a file named **analysis_options.yaml** to the root of your project. Paste in the [Flutter Team linting rules](https://github.com/raywenderlich/flutter-sample-project/blob/master/analysis_options.yaml), which you can find in the root of this repository.

These linting rules will let your IDE give you warnings or errors if you aren't following the Flutter Team's coding style. This also means that you should fix all of the IDE warnings and errors before you submit your sample app.

### Update pubspec.yaml

Here is a checklist for things to pay attention to in **pubspec.yaml**:

- Set the app name and description.
- Set the minimum Dart SDK to no lower than `2.12.0` in order to take full advantage of sound null safety. The only reason you wouldn't do this is if your app absolutely requires a package that hasn't been upgraded to null safety.
- Remove all the default comments.

There is a sample **pubspec.yaml** file in the root of this repository for your reference.

### Use .gitignore

When you create a new Flutter project it comes with a good `.gitignore` file. Go with what's in there. Also consider this a good list of things not to include when you upload your project to kodeco.com. 

**Hint**: If you develop your project with GitHub, all you have to do is download it from GitHub before uploading it to kodeco.com. This is an easy way to ensure that there are no unnecessary files in the project.

### Remove unused folders

If your project doesn't include any tests, then remove the **test** folder. The same is true for platform folders if you are specifically not supporting that platform. (See the **Web assets** section below.)

## Image assets

Including image assets in your app makes it look better and feel more polished. You can either create your own or use the standard kodeco.com assets.

### Android assets

On Android you need to add a splash screen and launch icon. To use the kodeco.com assets for these, replace the contents of your project's **android/app/src/main/res** folder with the contents of the **android_assets/res** folder in this repository.

### iOS assets

You also need to add an iOS splash screen and launch icon. To use the standard kodeco.com image assets, replace the contents of your project's **ios/Runner/Assets.xcassets** folder with the contents of the **ios_assets/Assets.xcassets** folder in this repository.

### Web assets

You should also add a favicon and other asset images for the web. To use the standard kodeco.com asset images, go to your project's **web** folder and replace **favicon.png** and the contents of the **icons** folder with the image assets found in the **web_assets** folder in this repository.

**Note**: If your project does not support the web, then delete the entire **web** folder.

## App display name

Rather than having your launcher icon use your project name, which might be something unsightly like `appname`, you should update the display name for each platform that Flutter supports.

### Android

Open **AndroidManifest.xml** in **android/app/src/main** and set the app display name by editing the `android:label` property. 

```
<application
     android:label="Super App"
```

This name will appear under the app's launcher icon on the user's Android device.

### iOS

Open **Info.plist** in **ios/Runner** and set the app display name by editing the `CFBundleName` string property.

```
<dict>
	<key>CFBundleName</key>
	<string>Super App</string>
```

This name will appear under the app's launcher icon on the user's iOS device.

### Web

Open **index.html** in the **web** folder of your project root. Then set the display name by editing the `title` property.

```
<head>
  <title>Super App</title>
```

This will change the display name used in the page's browser tab next to the favicon.

## Testing it out

Run the app on an Android and iOS device or emulator/simulator to make sure the splash screen, launcher icon and app name display correctly. If you don't have a Mac, then mention that on the Trello card so that the TE or FPE can double check the iOS version.

Run the Flutter web app in a browser to make sure that the favicon and app name show on the browser tab.

## Future changes

This guide is up to date for Flutter 2.0. When desktop versions enter the stable channel without the need for any special flags, the required resources should be added for them as well.

Are there new Flutter updates that break this guide? Please open a GitHub issue or submit a pull request.
