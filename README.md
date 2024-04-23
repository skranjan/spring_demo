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

## Setup

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

Add to your app's AndroidManifest.xml:

```XML
    <uses-permission android:name="android.permission.START_ACTIVITY" />
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
    <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
    <uses-permission android:name="android.permission.ACCESS_MEDIA_LOCATION" />
    <uses-permission android:name="android.permission.MANAGE_EXTERNAL_STORAGE" tools:ignore="ScopedStorage"/>
```

Note: In the AndroidManifest.xml file, the attribute android:exported="true" must be set to true to enable opening another app.
```
    <activity
        android:name=".YourActivity"
        android:exported="true">
    </activity>

```

## Using the App

### 1. Grant Permissions:
- On first launch, the app will request the necessary permissions. Grant them to proceed.
### 2. Acquire Location:
- The app automatically starts acquiring your GPS location once permissions are granted.
- Ensure your device's location services are turned on.
### 3. Read XML from External Storage:
- Place a file named Gift_Param.xml in the Downloads directory of your device.
- The app reads this file on startup and uses its values to configure certain features.
### 4. Open Another App:
- Click on the "Open App" button to launch a specific activity in another app (ensure the target app is installed).
### 5. Navigate to Settings:
- If any permissions are forcefully denied, use the provided alert dialog to navigate to the app settings page and grant the necessary permissions.

## Code Prospective

### 1. Open Another App Without Params

####

    
## Troubleshooting
- Permissions Not Granted: Ensure you grant all requested permissions. Without them, the app will not function properly.
- XML File Not Found: Make sure the XML file is correctly placed in the Downloads folder.
- `Target App Not Found:` The "Open App" feature will not work if the target app is not installed. Verify the package and activity name.

## Additional Notes
- This app is a demonstration and may require additional configuration for production deployment.

#### For any further issues or contributions, please open an issue or pull request on the GitHub repository.

## License

This project is licensed under the [MIT License](LICENSE).
