# Android Development Lab 2

## Lab Title: Creating a Basic Android App with UI Components & Customization

### Objectives:
- Understand **RelativeLayout** for flexible UI design.
- Learn to use **TextViews** and **ImageView** for displaying text and images.
- Implement a **custom log** for debugging and tracking app behavior.
- Apply a **custom theme** to style the app.
- Add a **custom logo** to the app by placing an image in the `res/drawable` folder and using it in the UI.

---

## Lab Outline:

### 1. Setting Up the Project
1. Open **Android Studio** and create a new project.
2. Select **Empty Activity** and name it `Lab2App`.
3. Choose **Java** as the programming language.
4. Click **Finish** to generate the project.

---

### 2. Understanding RelativeLayout
**RelativeLayout** allows you to position UI elements relative to each other or to the parent container. It provides more flexibility compared to LinearLayout.

#### Example of RelativeLayout:
```xml
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:id="@+id/titleText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Welcome to My App"
        android:textSize="24sp"
        android:textStyle="bold"
        android:layout_centerHorizontal="true"/>

</RelativeLayout>
```
📌 **Key Properties Used:**
- `layout_centerHorizontal`: Centers the `TextView` horizontally.
- `textSize`: Defines text size.
- `textStyle`: Defines the text appearance.

---

### 3. Adding TextViews
**TextView** is used to display text in the UI.

#### Example:
```xml
<TextView
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="This is a TextView"
    android:textSize="18sp"
    android:textColor="@color/black"
    android:layout_below="@id/titleText"
    android:layout_marginTop="10dp" />
```

📌 **Key Properties:**
- `text`: Defines the displayed text.
- `textSize`: Adjusts text size.
- `textColor`: Sets text color.
- `layout_below`: Positions the text below another element.

---

### 4. Adding an ImageView
**ImageView** is used to display images in an app.

#### Steps:
1. Place an image in **res/drawable/** (e.g., `logo.png`).
2. Use the following code in `activity_main.xml`:

```xml
<ImageView
    android:id="@+id/appLogo"
    android:layout_width="150dp"
    android:layout_height="150dp"
    android:src="@drawable/logo"
    android:layout_below="@id/titleText"
    android:layout_centerHorizontal="true"
    android:layout_marginTop="20dp"/>
```

📌 **Key Properties:**
- `src`: Sets the image source.
- `layout_below`: Positions the image below another element.
- `layout_centerHorizontal`: Centers the image horizontally.

---

### 5. Implementing a Custom Log
Logging is useful for debugging. **Custom logs** allow better tracking of app behavior.

#### Example:
Modify `MainActivity.java`:

```java
package com.example.lab2app;
import android.os.Bundle;
import android.util.Log;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    private static final String TAG = "Lab2App"; // Custom Tag

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        
        Log.d(TAG, "App Started Successfully"); // Debug message
    }
}
```
📌 **Key Points:**
- `Log.d(TAG, "message")`: Used to print debug logs in Logcat.
- Custom `TAG` helps filter logs.

---

### 6. Creating a Custom Theme
Themes change the app’s overall look and feel.

#### Steps:
1. Open **res/values/themes.xml**.
2. Modify it as follows:

```xml
<style name="Theme.Lab2App" parent="Theme.MaterialComponents.Light.DarkActionBar">
    <item name="colorPrimary">#6200EE</item>
    <item name="colorPrimaryVariant">#3700B3</item>
    <item name="colorAccent">#03DAC5</item>
</style>
```

3. Apply the theme in `AndroidManifest.xml`:
```xml
<application
    android:theme="@style/Theme.Lab2App">
</application>
```

📌 **Key Customizations:**
- `colorPrimary`: Defines the primary app color.
- `colorAccent`: Defines highlight colors.

---

### 7. Adding a Custom App Logo
You can **set a custom app icon** that appears in the launcher.

#### Steps:
1. Place your **logo.png** in `res/mipmap` (all resolutions: `mipmap-mdpi`, `mipmap-hdpi`, etc.).
2. Open `AndroidManifest.xml` and modify the `<application>` tag:

```xml
<application
    android:icon="@mipmap/logo"
    android:roundIcon="@mipmap/logo_round">
</application>
```

📌 **Key Points:**
- `android:icon`: Sets the app icon.
- `android:roundIcon`: Sets the icon for rounded displays.

---

## 🎯 Lab Tasks
- Create an **Android project** using Java.
- Implement **RelativeLayout**.
- Add **TextViews** and customize text appearance.
- Insert an **ImageView** and display a custom logo.
- Implement **custom logs** for debugging.
- Define and apply a **custom theme**.
- Set a **custom app logo**.

---

## 📌 Summary
✅ Built a **basic app UI** using RelativeLayout.  
✅ Used **TextViews** and **ImageView**.  
✅ Implemented **custom logs** for debugging.  
✅ Created and applied a **custom theme**.  
✅ Added a **custom app logo** in the `res` directory.  

---

## 📝 Homework
- **Modify the app layout** to add buttons.
- **Apply different color themes** and observe UI changes.
- **Use an alternative image for the app logo** and display it inside the UI.

---

🔥 Great job! You’ve successfully created a **basic Android app with a custom UI and branding!** 🚀
