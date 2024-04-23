# Open Other App Android Application

This Android application demonstrates how to interact with another app installed on the device and perform actions like opening a specific activity and passing data to it. The app also includes features related to obtaining device location, handling permissions, reading XML configuration files, and more.

## Features:

- **Open Other App Activity**: Allows the user to open a specific activity of another app installed on the device.
- **Location Services**: Utilizes Google Play Services to obtain the device's current location (latitude and longitude).
- **Permission Handling**: Requests and handles runtime permissions required for location access and file reading.
- **XML File Reading**: Reads configuration values from an XML file stored in the device's downloads directory.
- **UI Interaction**: Provides a simple user interface with buttons to trigger actions and display progress.

## Usage:

To use this application, follow these steps:

1. Clone this repository to your local machine.
2. Open the project in Android Studio.
3. Build and run the application on an Android device or emulator.
4. Grant necessary permissions when prompted.
5. Use the provided buttons to interact with other installed apps or view location-related information.

## Requirements:

- Android Studio
- Android device or emulator running Android API level 23 or higher
- Min SDK Version 27+
- Target SDK Version 33+

## Permissions:

This application requires the following permissions:

- `ACCESS_FINE_LOCATION`: Required to access precise location information.
- `ACCESS_COARSE_LOCATION`: Required to access approximate location information.
- `READ_EXTERNAL_STORAGE`: Required to read XML configuration files stored in the device's downloads directory.
- `android.permission.MANAGE_EXTERNAL_STORAGE`: Allows managing external storage. Ignored for scoped storage

## Application Attributes:
- `android:requestLegacyExternalStorage="true": Requests legacy external storage access mode.

## Credits

This application utilizes the following libraries and technologies:

- **Google Play Services**: Used for location services.
- **PermissionX**: Simplifies the process of requesting runtime permissions.
- **Gson**: JSON library for handling data serialization and deserialization.
- **XMLPullParser**: Java-based XML parser for reading XML files.

### Step 1: Declare dependency

Add to your app's build.gradle:

```gradle
dependencies {
    implementation 'com.google.code.gson:gson:2.8.9'
    implementation 'com.google.android.gms:play-services-location:18.0.0'
    implementation 'com.guolindev.permissionx:permissionx:1.7.1'
}
```

### Step 2: Configure the AndroidManifest.xml

Add to your app's build.gradle:

```XML
    <uses-permission android:name="android.permission.START_ACTIVITY" />
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
    <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
    <uses-permission android:name="android.permission.ACCESS_MEDIA_LOCATION" />
    <uses-permission android:name="android.permission.MANAGE_EXTERNAL_STORAGE" tools:ignore="ScopedStorage"/>
```

## License

This project is licensed under the [MIT License](LICENSE).
