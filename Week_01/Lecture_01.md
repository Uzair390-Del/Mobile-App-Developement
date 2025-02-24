# Android Application Development - Week 1 Lecture

## Course Policies and Guidelines
- **Attendance & Participation:** Regular attendance is required. Active participation in discussions and practical sessions is encouraged.
- **Assignment & Projects:** Assignments must be submitted on time. Projects should follow the given guidelines.
- **Plagiarism Policy:** Any form of plagiarism in assignments or projects will result in strict action.
- **Evaluation Criteria:** Includes quizzes, assignments, practical implementation, and final projects.

## Introduction to Android Development
### What is Android?
- Android is an open-source mobile operating system developed by Google.
- Used for smartphones, tablets, smart TVs, and IoT devices.
- Built on the Linux kernel and supports Java and Kotlin as primary programming languages.

### Android Architecture
Android's architecture is divided into several key layers:
1. **Linux Kernel:**
   - Core foundation of Android OS.
   - Manages low-level hardware interactions, memory management, and process scheduling.
   - Includes essential drivers for display, camera, audio, and networking.

2. **Hardware Abstraction Layer (HAL):**
   - Acts as a bridge between hardware components and higher-level system APIs.
   - Provides interfaces to interact with device hardware such as sensors, audio, and cameras.

3. **Android Runtime (ART) and Core Libraries:**
   - ART is the runtime environment that executes applications efficiently.
   - Uses Ahead-of-Time (AOT) compilation for better performance and reduced application launch time.
   - Includes Java core libraries for essential functionalities.

4. **Native Libraries:**
   - Provides essential libraries for graphics (OpenGL), databases (SQLite), and multimedia (Media Framework).
   - Includes WebKit for browser rendering and SSL for security features.

5. **Application Framework:**
   - Offers high-level APIs for developers to build applications.
   - Manages activities, notifications, resources, location services, and package management.

6. **Applications Layer:**
   - Includes pre-installed system applications like Phone, Messages, and Browser.
   - Supports user-installed applications from the Google Play Store.

## Introduction to Mobile Applications & Android Platform
- **Types of Mobile Applications:**
  - Native Apps: Developed for specific platforms (Android, iOS).
  - Web Apps: Accessed through web browsers.
  - Hybrid Apps: Combination of native and web technologies.

- **Why Choose Android Development?**
  - Open-source and widely used platform.
  - High demand in the industry.
  - Vast community support.
  - Easy deployment and distribution.

## Brief Introduction to Programming Language and Tool
- **Programming Languages for Android:**
  - Java: Official language for Android development.
  - Kotlin: Recommended modern alternative to Java.
- **Development Tools:**
  - Android Studio: Official IDE for Android development.
  - SDK & AVD Manager: For creating virtual devices.
  - Gradle: Build automation tool.

## Setting Up Development Environment
### **How to Install Android Studio (Latest Version)**
1. Download Android Studio from the official website: [https://developer.android.com/studio]
2. Install and launch Android Studio.
3. Configure required settings and install necessary SDKs.

### **Setting Up Environment for Application Development**
1. Open Android Studio and select "Start a new Android Studio project."
2. Choose a project template (e.g., Empty Activity).
3. Configure project settings:
   - Enter application name.
   - Choose programming language (Java/Kotlin).
   - Select minimum API level.
4. Set up an emulator using AVD (Android Virtual Device) Manager.
5. Install required dependencies and libraries.

## Creating and Executing the First Basic Android Application
### **Steps to Create a Simple Android App**
1. Open Android Studio and create a new project.
2. Modify `activity_main.xml` (UI Design):
   ```xml
   <TextView
       android:layout_width="wrap_content"
       android:layout_height="wrap_content"
       android:text="Hello, Android!" />
   ```
3. Modify `MainActivity.java` (Logic Implementation):
   ```java
   package com.example.helloworld;
   import android.os.Bundle;
   import androidx.appcompat.app.AppCompatActivity;
   import android.widget.TextView;

   public class MainActivity extends AppCompatActivity {
       @Override
       protected void onCreate(Bundle savedInstanceState) {
           super.onCreate(savedInstanceState);
           setContentView(R.layout.activity_main);
       }
   }
   ```
4. Run the application on an emulator or physical device.
5. Observe "Hello, Android!" displayed on the screen.

## Summary
- Understood Android development fundamentals.
- Installed and set up Android Studio.
- Configured environment and created a basic Android app.

## Homework
- Install Android Studio and create your first Android application.
- Explore Android Studio’s interface and tools.
