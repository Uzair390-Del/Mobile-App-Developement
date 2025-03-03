# Android Development Lab 1

## Lab Title: Introduction to Android Studio & File Structure Overview

### Objectives:
- Understand the installation process of Android Studio.
- Explore the complete Android Studio file structure.
- Learn about the importance of SDK (Software Development Kit) and JDK (Java Development Kit).
- Gain awareness of Java and XML files used in Android development.
- Understand the different directories and components within an Android project.

---

## Lab Outline:

### 1. Android Studio Installation Guide
- Download **Android Studio** from the official website:  
  [https://developer.android.com/studio](https://developer.android.com/studio)
- Install **Android Studio** and launch the setup wizard.
- Configure required **SDK components** during installation.
- Verify installation by running **Android Studio IDE**.

---

### 2. Understanding SDK & JDK

#### Software Development Kit (SDK):
- Provides essential **tools and libraries** for Android development.
- Includes:
  - **Platform-specific APIs**
  - **Emulator system images**
  - **Build tools**
- Located in the **sdk/** directory inside the Android Studio installation.
- Managed using the **SDK Manager** in Android Studio.

#### Java Development Kit (JDK):
- Required for **compiling and running Java code** in Android applications.
- Includes:
  - **Java Compiler (javac)**
  - **Java Runtime Environment (JRE)**
  - **Development tools**
- Verify **JDK installation** by running the following command in the terminal:
  ```sh
  java -version
#### 3. Android Studio File Structure Guide

##### Project Root Directory:
- Contains the complete Android project structure, including source files and configuration settings.

##### Important Directories:

###### `app/` Directory:
- Contains all application-related source code and resources.
- **Subdirectories:**
  - `manifests/` → Contains `AndroidManifest.xml` (App metadata, permissions, services).
  - `java/` → Stores Java/Kotlin source code.
  - `res/` → Stores all app resources (layouts, images, strings, etc.).

###### `gradle/` Directory:
- Manages build automation using Gradle.
- Contains `gradle-wrapper.properties` for dependency management.

###### `build/` Directory:
- Stores compiled files, generated APKs, and cache data.

###### `libs/` Directory (if present):
- Stores external libraries (JAR/AAR files).

#### 4. Java Files Awareness
- Java files reside in `app/src/main/java/`.
- Every Android app has an entry point in `MainActivity.java`.

##### Example of a Basic Java Activity:
```java
package com.example.myapp;
import android.os.Bundle;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
}
```

#### 5. XML Files Awareness
- XML files reside in `res/layout/`.
- Define UI components and layouts.

##### Example of `activity_main.xml`:
```xml
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello, Android!" />
</LinearLayout>
```

#### 6. Directories Awareness
- `res/drawable/` → Stores images and icons.
- `res/values/` → Stores strings, colors, and dimensions.
- `res/menu/` → Stores menu XML files.
- `assets/` → Stores raw files needed as assets.

#### 7. Other Important Components Awareness
- `AndroidManifest.xml` → Defines app metadata, permissions, and activities.
- **Gradle Build Files** → Controls dependencies and build configurations (`build.gradle`).
- **Emulator Setup** → Used to test apps without a physical device.

---

## 🎯 Lab Tasks
- Install and configure Android Studio on your system.
- Locate and explore SDK and JDK directories.
- Create a new Android project and navigate through its file structure.
- Identify and understand the purpose of each directory in the project.
- Open and analyze `MainActivity.java` and `activity_main.xml`.
- Run the default app on an emulator or physical device.

## 📌 Summary
- Successfully installed and set up Android Studio.
- Explored the project structure and key files.
- Understood the role of SDK, JDK, Java, and XML files in Android development.
- Gained awareness of essential components and directories in an Android project.

## 📝 Homework
- Research more about Gradle and its role in Android development.
- Create a simple UI with a Button and TextView in `activity_main.xml`.
- Write a Java function to display a Toast message when a button is clicked.