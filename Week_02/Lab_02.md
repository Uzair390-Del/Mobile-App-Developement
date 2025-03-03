# Android Development Lab 2

## Lab Title: Creating a Basic Android App with UI Components & Customization

### Objectives:
- Understand and implement **RelativeLayout** in an Android application.
- Learn to use **TextView** and **ImageView**.
- Implement **custom logging** for debugging.
- Apply a **custom theme** to enhance the UI.

---

## 1. Understanding **RelativeLayout**
RelativeLayout is a **ViewGroup** that positions child views relative to each other or the parent layout.

### **Key Attributes of RelativeLayout**:
- `layout_alignParentTop` → Aligns the view to the top of the parent.
- `layout_below` → Positions the view below another view.
- `layout_centerHorizontal` → Centers the view horizontally.

### **Example XML: RelativeLayout with TextView and ImageView**
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
        android:layout_centerHorizontal="true"
        android:padding="10dp" />

    <ImageView
        android:id="@+id/appLogo"
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:src="@drawable/logo"
        android:layout_below="@id/titleText"
        android:layout_centerHorizontal="true" />

</RelativeLayout>
```

---

## 2. Working with **TextView**
- **TextView** is used to display static or dynamic text.
- You can customize the font, size, color, and style.

### **Example: TextView in Java**
```java
TextView welcomeText = findViewById(R.id.titleText);
welcomeText.setText("Hello, Android!");
welcomeText.setTextColor(Color.RED);
```

---

## 3. Using **ImageView**
- **ImageView** is used to display images from **drawables** or an online URL.

### **Example: Loading an Image**
```xml
<ImageView
    android:id="@+id/myImage"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:src="@drawable/sample_image"
    android:layout_below="@id/titleText"
    android:layout_centerHorizontal="true" />
```

---

## 4. Implementing **Custom Log Messages**
Logging helps track application behavior and debug issues.

### **Example: Using Logcat for Debugging**
```java
import android.util.Log;

public class MainActivity extends AppCompatActivity {
    private static final String TAG = "CustomLogTag";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Log.d(TAG, "App Started Successfully");
        Log.e(TAG, "Error: Something went wrong");
        Log.i(TAG, "Info: App is running smoothly");
    }
}
```
- `Log.d(TAG, "Debug Message");` → Debugging message.
- `Log.e(TAG, "Error Message");` → Error message.
- `Log.i(TAG, "Info Message");` → Informational message.

---

## 5. Applying **Custom Theme**
A **custom theme** changes the UI appearance of the app.

### **Steps to Implement a Custom Theme**:
1. Open `res/values/styles.xml`
2. Define a new theme:

```xml
<style name="CustomTheme" parent="Theme.AppCompat.Light.DarkActionBar">
    <item name="android:colorPrimary">#6200EE</item>
    <item name="android:colorPrimaryDark">#3700B3</item>
    <item name="android:colorAccent">#03DAC5</item>
</style>
```

3. Apply the theme in `AndroidManifest.xml`:
```xml
<application
    android:theme="@style/CustomTheme">
</application>
```

---

## 🎯 **Lab Tasks**
1. Create a new Android project.
2. Implement **RelativeLayout** with **TextView** and **ImageView**.
3. Use **Logcat** to display custom logs.
4. Apply a **custom theme** to change the UI style.

---

## 📌 **Summary**
- Built a basic Android app using **RelativeLayout**.
- Learned to use **TextView** and **ImageView**.
- Implemented **custom log messages** for debugging.
- Applied a **custom theme** to style the application.

---

## 📝 **Homework**
- Modify the app to include a **Button** that logs a message when clicked.
- Experiment with different **theme colors** and styles.
- Research **ConstraintLayout** and compare it with RelativeLayout.

🚀 **Happy Coding!**
