# **Android App Development Theory Exam OHT-1 - Solution Guide**

**Institute:** Dr. A.Q. Khan Institute of Computer Sciences & Information Technology, Kahuta  
**Affiliated with:** Institute of Space Technology, Islamabad  
**Department:** Computer Engineering  
**Exam:** One-Hour Test (OHT-I) Theory Exam Spring 2025  
**Teacher:** Uzair Hassan  
**Class/Semester:** CE-VIII / 8th  
**Date:** 8-04-2025  
**Duration:** 3 Hours  
**Total Marks:** 30  

---
### 📘 Q#1: Android Architecture

Android architecture consists of four main layers:

1. **Linux Kernel**  
   - The foundation layer of Android OS.  
   - Manages core system services like security, memory management, process management, and device drivers.  
   - Example: Manages camera or Bluetooth driver access.

2. **Hardware Abstraction Layer (HAL)**  
   - Acts as an interface between the hardware drivers and higher-level Java APIs.  
   - Allows Android to support different hardware without changing application code.

3. **Android Runtime (ART) and Core Libraries**  
   - **ART:** Replaces Dalvik; executes app bytecode, uses AOT compilation for performance.  
   - **Core Libraries:** Provide essential Java libraries for Android apps.

4. **Application Framework**  
   - Provides high-level services like activity management, content providers, location services, etc.  
   - Developers interact with this layer when building apps.

5. **Applications**  
   - The top layer where end-user apps (like Dialer, SMS, etc.) run.

---

### 📘 Q#2: Android Activity Lifecycle with Diagram

The Android Activity Lifecycle includes the following callback methods:

```plaintext
onCreate() → onStart() → onResume() → [Activity Running] → onPause() → onStop() → onDestroy()
                                                ↑
                                       (onRestart if coming back)
```

#### 🔁 Callback Methods:
- **onCreate()** – Initializes activity, sets layout. Example: `setContentView()`.
- **onStart()** – Activity becomes visible.
- **onResume()** – Activity starts interacting with the user.
- **onPause()** – Another activity comes in front (partially visible). Save data here.
- **onStop()** – Activity is no longer visible.
- **onDestroy()** – Activity is destroyed; cleanup resources.
- **onRestart()** – Called after onStop() if the activity is coming back.

Example: An app starts → user presses home → app goes to background → user returns → lifecycle resumes from `onRestart()`.

---

### 📘 Q#3: Intents in Android

An **Intent** is a messaging object used to request actions from other components (activity, service, broadcast receiver).

#### ✅ Types of Intents:

1. **Explicit Intent**
   - Targets a specific component (e.g., a specific activity).
   - Used for **intra-app** communication.
   - **Example:**
     ```java
     Intent intent = new Intent(this, SecondActivity.class);
     startActivity(intent);
     ```

2. **Implicit Intent**
   - No specific component defined; Android system resolves the best match.
   - Used for **inter-app** tasks (e.g., open browser, share image).
   - **Example:**
     ```java
     Intent intent = new Intent(Intent.ACTION_VIEW);
     intent.setData(Uri.parse("https://www.google.com"));
     startActivity(intent);
     ```

#### 📌 Use Cases:
- **Explicit:** Move from MainActivity to SettingsActivity within the same app.
- **Implicit:** Open a map app for location, or a dialer to call a number.

---