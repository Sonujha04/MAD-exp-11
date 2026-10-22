# EXPERIMENT 11: DEVELOP AN APPLICATION TO DISPLAY A MAP USING GOOGLE MAPS API

## 1. Aim

To design and develop an Android application using Android Studio that integrates the Google Maps API to display an interactive geographical map. The application allows users to view geographical areas, zoom in and out, move around the map, and explore different locations using the Google Maps SDK for Android.

## 2. Introduction

Maps are an important part of modern mobile applications because they help users understand geographical locations, find places, and navigate between different areas. Applications related to transportation, tourism, food delivery, shopping, and location tracking use digital maps to provide location-based services.

Google Maps is a widely used digital mapping service that provides geographical information, satellite imagery, road maps, location details, and navigation-related functionality. Developers can integrate Google Maps into their own Android applications using the Google Maps SDK for Android.

In this experiment, an Android application is developed using Kotlin and XML in Android Studio. The application integrates Google Maps into its user interface and displays a map on the screen. Users can interact with the map using gestures such as dragging, zooming, and moving across geographical regions.

The application requires a Google Cloud project and a valid API key. The API key connects the Android application to the Google Maps Platform and allows the application to request map data according to the project's API configuration and usage restrictions.

This experiment provides practical knowledge of third-party API integration, Android application development, resource configuration, API authentication, and map-based user interfaces.

## 3. Objectives

The main objectives of this experiment are:

1. To understand the basic concepts of Google Maps and location-based mobile applications.
2. To learn how to create an Android application using Android Studio.
3. To understand the integration of external APIs into Android applications.
4. To configure the Google Maps Platform through Google Cloud Console.
5. To generate and securely configure a Google Maps API key.
6. To design an application interface capable of displaying a map.
7. To understand the role of Kotlin in initializing and controlling map functionality.
8. To learn how to configure the Android Manifest file and string resources.
9. To test map loading, zooming, and map movement on an emulator or physical device.
10. To identify and troubleshoot common API configuration and network errors.

## 4. Software and Hardware Requirements

### 4.1 Software Requirements

| Software / Tool | Purpose |
|---|---|
| Android Studio | Used to create, develop, build, and test the Android application |
| Kotlin | Used to implement application logic and initialize map functionality |
| XML | Used to define the application's user interface and string resources |
| Google Maps SDK for Android | Used to integrate Google Maps into the application |
| Google Cloud Console | Used to configure the project, enable APIs, and create an API key |
| Gradle | Used to manage project configuration and dependencies |
| Android SDK | Provides the libraries and tools required to build Android applications |
| Logcat | Used to identify runtime errors and API authorization problems |

### 4.2 Hardware Requirements

- A computer or laptop capable of running Android Studio.
- An Android emulator or a physical Android device.
- A stable internet connection.
- Sufficient memory and storage for Android Studio and its SDK components.

## 5. Technologies Used

### 5.1 Android Studio

Android Studio is the official integrated development environment for Android application development. It provides tools for writing Kotlin code, designing XML layouts, managing dependencies, building APK files, running emulators, and debugging applications.

### 5.2 Kotlin

Kotlin is the programming language used to implement the application logic. It can initialize the map, handle map-related callbacks, configure camera positions, and add markers or other map features.

### 5.3 XML

XML is used to define Android layouts and application resources. In this experiment, `activity_main.xml` defines the screen that hosts the map, while `strings.xml` stores textual resources and the Google Maps API key reference.

### 5.4 Google Maps SDK for Android

The Google Maps SDK for Android provides the classes and interfaces needed to display and interact with Google Maps inside an Android application. It supports map movement, zoom controls, camera positioning, map markers, and other map-related functionality.

### 5.5 Google Cloud Console

Google Cloud Console is used to create or select a cloud project, enable the Maps SDK for Android, configure billing when required, generate API keys, and apply security restrictions.

## 6. Project Structure

The main files of the application are organized as follows:

```text
exp11/
├── app/
│   ├── src/
│   │   └── main/
│   │       ├── java/
│   │       │   └── <package-name>/
│   │       │       └── MainActivity.kt
│   │       ├── res/
│   │       │   ├── layout/
│   │       │   │   └── activity_main.xml
│   │       │   └── values/
│   │       │       └── strings.xml
│   │       └── AndroidManifest.xml
│   └── build.gradle.kts
├── build.gradle.kts
├── settings.gradle.kts
└── README.md
```

The exact structure may differ depending on the project template and package name selected in Android Studio.

### 6.1 MainActivity.kt

`MainActivity.kt` is the primary Kotlin file responsible for controlling the application's main screen. It connects the user interface with the map functionality.

Depending on the implementation, this file may initialize a `SupportMapFragment` or `MapView`, receive a callback when the map is ready, configure the initial camera position, and add markers.

### 6.2 activity_main.xml

`activity_main.xml` defines the visual structure of the application. It contains the component used to display the Google Map.

A map-based layout may use a `SupportMapFragment` inside a suitable Android layout container. The layout must correspond to the map initialization method used in the Kotlin file.

### 6.3 strings.xml

`strings.xml` stores application string resources. In this project, it includes the application name and the Google Maps API key resource.

Example:

```xml
<resources>
    <string name="app_name">exp11</string>
    <string name="google_maps_key" translatable="false">YOUR_API_KEY</string>
</resources>
```

The placeholder `YOUR_API_KEY` must be replaced with a valid key before the application can load Google Maps successfully.

### 6.4 AndroidManifest.xml

The Android Manifest file contains essential information about the application, including its activity declarations, permissions, and application configuration.

The Google Maps API key is normally referenced through metadata inside the `<application>` element. The internet permission, when needed, is declared directly under `<manifest>`.

### 6.5 build.gradle.kts

This file contains the module-level build configuration, including Android SDK settings and the dependencies required by the application. The Google Maps SDK dependency must be added using a compatible version.

## 7. Procedure

### Step 1: Create a New Android Project

1. Open Android Studio.
2. Select **New Project**.
3. Choose a suitable Android application template.
4. Enter the project name as `exp11`.
5. Select Kotlin as the programming language.
6. Choose the minimum SDK appropriate for the experiment.
7. Click Finish and wait for Gradle synchronization to complete.

Android Studio creates the initial project structure, including the activity file, layout resources, manifest, and Gradle configuration.

### Step 2: Create a Google Cloud Project

1. Open [Google Cloud Console](https://console.cloud.google.com/).
2. Sign in using a Google account.
3. Create a new project or select an existing project.
4. Give the project a suitable name.
5. Open the selected project in the Google Cloud Console.

A cloud project is required to manage Google Maps APIs, API credentials, usage limits, and billing configuration.

### Step 3: Enable Maps SDK for Android

1. Open APIs & Services in Google Cloud Console.
2. Select Library.
3. Search for **Maps SDK for Android**.
4. Open the API details page.
5. Click Enable.

This step allows the cloud project to use the Maps SDK for Android. Merely creating an API key does not automatically enable the required API.

### Step 4: Configure Billing and Generate an API Key

1. Check the billing configuration required for the Google Maps Platform.
2. Open APIs & Services → Credentials.
3. Select Create Credentials.
4. Choose API key.
5. Copy the generated key.
6. Apply appropriate API restrictions and Android application restrictions.

An API key identifies the cloud project used for map requests. Its access should be limited to the necessary API and application.

For Android application restrictions, configure the correct application package name and signing certificate SHA-1 fingerprint. Debug and release builds may use different signing certificates.

**Security note:** Never commit an unrestricted API key or other private credentials to a public GitHub repository. Use appropriate restrictions and a suitable secret-management approach.

### Step 5: Add the API Key to strings.xml

Open `app/src/main/res/values/strings.xml` and define the `google_maps_key` resource.

Replace the placeholder with the actual API key generated in Google Cloud Console.

This resource makes the key available to the application through Android's resource system. It also avoids hardcoding the key directly into the Kotlin activity.

### Step 6: Configure AndroidManifest.xml

Open `AndroidManifest.xml` and verify that the Google Maps API key is referenced inside the application element.

The metadata name should be `com.google.android.geo.API_KEY`, and its value should reference `@string/google_maps_key`.

Declare the internet permission outside the application element when required by the application.

Correct placement is important because an incorrect metadata declaration may prevent the Maps SDK from retrieving the API key.

### Step 7: Add the Required Google Maps Dependency

Open the module-level `app/build.gradle.kts` file.

Ensure that the project includes the Google Maps SDK for Android dependency and that the required repositories are configured.

Use a compatible dependency version based on the current official documentation. After modifying the Gradle file, click **Sync Now** and wait for synchronization to finish.

### Step 8: Design the Application Layout

Open `activity_main.xml` in Android Studio.

Create a layout that can host the map component. The map may be integrated using a `SupportMapFragment` or a `MapView`, depending on the implementation.

If a fragment-based approach is selected, ensure that the fragment identifier used in the XML matches the identifier used by the Kotlin activity.

The map component should occupy the intended screen area so that users can interact with the map comfortably.

### Step 9: Implement Map Initialization

Open `MainActivity.kt`.

Initialize the map component according to the chosen implementation. For a fragment-based implementation, the activity typically requests the map asynchronously and receives a callback when the map becomes ready.

Once initialization is complete, the application can configure map settings, move the camera to an initial geographical position, or add markers.

The callback approach is important because map initialization may take time and the map object is not necessarily available immediately when the activity starts.

### Step 10: Run the Application

1. Save all modified files.
2. Complete Gradle synchronization.
3. Start an Android emulator or connect a physical Android device.
4. Select the target device in Android Studio.
5. Click Run.
6. Wait for the application to install and launch.
7. Verify that the map appears on the screen.

An emulator or device needs working internet connectivity to load online map data.

### Step 11: Test the Map

After the application opens, perform the following tests:

- Verify that the map is visible.
- Drag the map to move across different geographical areas.
- Zoom in and zoom out using gestures or the available controls.
- Confirm that the map remains responsive.
- Check Logcat if the map fails to load.

## 8. Working Principle

The application integrates the Google Maps SDK for Android into an Android activity. When the user launches the application, Android creates the activity and loads its layout.

The map component initializes the Maps SDK and uses the configured API key to access the Google Maps Platform. The SDK retrieves the required map data over the network and renders the map in the application's user interface.

Once the map is ready, the application can configure its initial camera position and enable supported map interactions. Users can drag the map, zoom into specific regions, and move to other geographical areas.

The overall process can be represented as follows:

```text
Launch Android Application
           |
           v
    Create Main Activity
           |
           v
     Load XML Layout
           |
           v
   Initialize Map Component
           |
           v
   Validate API Configuration
           |
           v
  Request Map Data Over Network
           |
           v
    Render Google Map
           |
           v
 User Interacts With the Map
```

The map will load only if the required API, key restrictions, network connectivity, billing configuration, and application setup are valid.

## 9. Features and Functionality

### 9.1 Displaying a Geographical Map

The primary feature of the application is displaying Google Maps within the Android interface. It allows users to visualize roads, geographical areas, and other map details supported by the configured map type and available map data.

### 9.2 Zooming

Users can zoom in to examine smaller geographical areas and zoom out to view larger regions. Zooming changes the scale of the displayed map.

### 9.3 Map Movement

Users can drag the map to explore nearby or distant geographical areas. The camera position changes according to the user's gestures.

### 9.4 Camera Positioning

The application can be extended to open the map at a predefined latitude and longitude. This makes it possible to display a particular city, landmark, or campus when the application starts.

### 9.5 Marker Integration

A marker can be added to identify a particular point on the map. Markers are useful for showing colleges, offices, tourist destinations, or other locations of interest.

Marker and camera-position features require additional implementation if they are not already included in the current project.

## 10. Testing and Expected Results

| Test Case | Procedure | Expected Result |
|---|---|---|
| Application launch | Open the application | Main activity appears |
| Map initialization | Wait for map loading | Google Map is displayed |
| Zoom in | Use a zoom gesture | A closer map view appears |
| Zoom out | Use a zoom gesture | A wider map view appears |
| Map movement | Drag the map | Different geographical areas appear |
| Invalid API key | Test with an invalid key | Map may fail to load and errors may appear |
| Network unavailable | Disable internet access | Online map data may fail to load |

The expected results depend on successful API configuration and the implementation of the features described above.

## 11. Troubleshooting

### 11.1 Map Is Blank or Gray

Possible causes include an invalid API key, a disabled Maps SDK, incorrect API restrictions, network issues, or billing configuration problems.

**Solution:** Verify the Google Cloud project, API enablement, API key restrictions, and internet connectivity. Check Logcat for detailed Maps SDK error messages.

### 11.2 API Key Authorization Error

The application package name or SHA-1 fingerprint may not match the configured Android application restrictions.

**Solution:** Confirm the application ID and the SHA-1 fingerprint of the certificate used to sign the build. Make sure the correct Maps API is permitted for the key.

### 11.3 Gradle Synchronization Error

The project may have an incompatible dependency version or an incorrectly configured repository.

**Solution:** Review the Gradle error message, verify the dependency declaration, check repository configuration, and synchronize the project again.

### 11.4 Application Crashes on Launch

The layout identifier, fragment initialization, dependency configuration, or activity implementation may be incorrect.

**Solution:** Review the implementation in `MainActivity.kt`, verify the map component in `activity_main.xml`, and inspect the crash details in Logcat.

### 11.5 Map Does Not Load on the Emulator

The emulator may lack internet connectivity or may be using an incompatible system image.

**Solution:** Check the emulator's internet access, update the emulator system image if necessary, and test the application on a compatible physical device if available.

## 12. Advantages

1. Provides geographical information within an Android application.
2. Offers a familiar and interactive map interface.
3. Supports zooming and map movement.
4. Can be extended with markers, place details, and location-based functionality.
5. Demonstrates the practical use of third-party APIs in mobile development.
6. Helps developers understand API configuration, resource management, and runtime debugging.



## 14. Limitations

1. An internet connection is generally required to retrieve current online map data.
2. Google Maps Platform usage is subject to applicable quotas, billing, and pricing policies.
3. A valid and correctly configured API key is necessary.
4. Incorrect API restrictions can prevent the map from loading.
5. Features such as current-location tracking, route calculation, and place search are not automatically implemented by displaying a basic map.
6. Map availability and performance may depend on the device, network, and Google Maps Platform services.

## 15. Future Enhancements

The application can be improved by adding the following features:

1. **Current location:** Display the user's location after implementing the required location permissions and location functionality.
2. **Custom markers:** Mark important places such as colleges, hospitals, offices, or tourist attractions.
3. **Place search:** Allow users to search for a specific location.
4. **Route display:** Show routes between selected destinations using an appropriate routing service.
5. **Info windows:** Display descriptive information when a marker is selected.
6. **Different map types:** Provide supported map types such as normal, satellite, terrain, or hybrid.
7. **Location sharing:** Allow users to share selected geographical coordinates or place details.
8. **User-friendly interface:** Add search fields, buttons, and other controls to improve usability.

## 16. Result

An Android application for displaying a geographical map using the Google Maps SDK for Android has been designed and configured. After successful API setup and implementation, the application can display an interactive Google Map and allow users to explore geographical areas using map movement and zoom controls.

## 17. Conclusion

This experiment demonstrates how Google Maps can be integrated into an Android application using Android Studio, Kotlin, XML, and the Google Maps SDK for Android. It provides practical knowledge of creating an Android project, configuring a cloud project, enabling an API, generating API credentials, defining resource values, and initializing a map component.

The experiment also highlights the importance of API security, internet connectivity, Gradle configuration, and runtime debugging. Through testing, developers can understand how external services are incorporated into mobile applications and how configuration errors can affect their operation.

The knowledge gained from this experiment provides a foundation for developing more advanced location-based Android applications, including applications that display custom markers, search for places, show routes, and provide location-related information
**User Interface:** XML

**Development Environment:** Android Studio

**API:** Google Maps SDK for Android
## screenshots 
<img width="371" height="792" alt="Screenshot 2026-10-22 110201" src="https://github.com/user-attachments/assets/bae1d73f-b48e-46ed-b35d-266e381a9489" />
<img width="358" height="791" alt="Screenshot 2026-10-22 110219" src="https://github.com/user-attachments/assets/368a25d3-e838-4f1a-a5ff-0d7ed3db2b41" />


