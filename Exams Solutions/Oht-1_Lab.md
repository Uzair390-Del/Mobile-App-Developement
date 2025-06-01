
# **Android App Development Lab Exam OHT-1 - Solution Guide**

**Institute:** Dr. A.Q. Khan Institute of Computer Sciences & Information Technology, Kahuta  
**Affiliated with:** Institute of Space Technology, Islamabad  
**Department:** Computer Engineering  
**Exam:** One-Hour Test (OHT-I) Lab Exam Spring 2025  
**Teacher:** Uzair Hassan  
**Class/Semester:** CE-VIII / 8th  
**Date:** 8-04-2025  
**Duration:** 3 Hours  
**Total Marks:** 30  

---

## **Q1[a]. Android Activity Lifecycle and Intents**  
**Marks: 5**  

### **Android Activity Lifecycle:**  
The activity lifecycle represents the different states an activity goes through during its existence in an Android app. Understanding the lifecycle is crucial for efficient app behavior, memory management, and handling user interactions.  

#### **Key Lifecycle Methods:**  
1. `onCreate()`: Called when the activity is first created. Used for initialization.
2. `onStart()`: Activity becomes visible to the user.
3. `onResume()`: Activity starts interacting with the user.
4. `onPause()`: Activity is partially visible; another activity is in the foreground.
5. `onStop()`: Activity is no longer visible.
6. `onRestart()`: Called after onStop() if the activity is restarting.
7. `onDestroy()`: Final call before the activity is destroyed.

### **Significance in Development:**  
- Saves resources by releasing unused components.
- Helps in saving/restoring state during configuration changes.
- Provides predictable behavior for user navigation.

### **Explicit vs Implicit Intents:**  

| Type        | Description | Example |
|-------------|-------------|---------|
| **Explicit Intent** | Directly specifies the target component (e.g., class name). | `Intent intent = new Intent(this, SecondActivity.class);` |
| **Implicit Intent** | Does not specify the target component. Android finds a suitable app/component. | `Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse("http://www.google.com"));` |

---

## **Q2[a]. Application Demonstrating Lifecycle and Intents**  
**Marks: 20**  

### **Requirements:**  
- Use of lifecycle methods: `onCreate()`, `onStart()`, etc.  
- Two buttons: Increase counter and launch second activity.  
- Explicit intent used to navigate between activities.  
- Logcat used to display lifecycle logs.  

### **Project Structure:**  
- **Activities:** FirstActivity.java, SecondActivity.java  
- **Layouts:** activity_first.xml, activity_second.xml  

### **FirstActivity.java:**  
```java
public class FirstActivity extends AppCompatActivity {
    private int counter = 0;
    private TextView counterTextView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_first);
        Log.d("Lifecycle", "onCreate called");

        counterTextView = findViewById(R.id.counterTextView);
        Button incrementButton = findViewById(R.id.incrementButton);
        Button navigateButton = findViewById(R.id.navigateButton);

        incrementButton.setOnClickListener(v -> incrementCounter());
        navigateButton.setOnClickListener(v -> launchSecondActivity());
    }

    private void incrementCounter() {
        counter++;
        counterTextView.setText("Counter: " + counter);
    }

    private void launchSecondActivity() {
        Intent intent = new Intent(this, SecondActivity.class);
        startActivity(intent);
    }

    @Override protected void onStart() { super.onStart(); Log.d("Lifecycle", "onStart called"); }
    @Override protected void onResume() { super.onResume(); Log.d("Lifecycle", "onResume called"); }
    @Override protected void onPause() { super.onPause(); Log.d("Lifecycle", "onPause called"); }
    @Override protected void onStop() { super.onStop(); Log.d("Lifecycle", "onStop called"); }
    @Override protected void onDestroy() { super.onDestroy(); Log.d("Lifecycle", "onDestroy called"); }
}
```

### **SecondActivity.java:**  
```java
public class SecondActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_second);
        Log.d("Lifecycle", "SecondActivity onCreate called");
    }
}
```

### **activity_first.xml:**  
```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical" android:layout_width="match_parent"
    android:layout_height="match_parent" android:padding="16dp">

    <TextView android:id="@+id/counterTextView" android:text="Counter: 0"
        android:layout_width="wrap_content" android:layout_height="wrap_content"
        android:textSize="24sp" />

    <Button android:id="@+id/incrementButton" android:text="Increase Counter"
        android:layout_width="wrap_content" android:layout_height="wrap_content" />

    <Button android:id="@+id/navigateButton" android:text="Go to Second Activity"
        android:layout_width="wrap_content" android:layout_height="wrap_content" />
</LinearLayout>
```

### **activity_second.xml:**  
```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical" android:layout_width="match_parent"
    android:layout_height="match_parent" android:gravity="center">

    <TextView android:text="This is Second Activity" android:textSize="20sp"
        android:layout_width="wrap_content" android:layout_height="wrap_content" />
</LinearLayout>
```

---

## **Q3[a]. Practice with XML and Modular Java Code**  
**Marks: 5**  

### **Separate Layout Files:**  
- `activity_first.xml`: UI for first screen (includes counter and two buttons).  
- `activity_second.xml`: UI for second screen (includes a TextView).  

### **Modular Java Code:**  
- Button click logic separated into methods like `incrementCounter()` and `launchSecondActivity()` for better readability and reusability.  

---

## **Grading Rubrics Applied in Solutions**  

| Category | Explanation |
|----------|-------------|
| **Application Design** | UI includes two buttons and text with proper layout. |
| **Framework Setup** | Android Studio project with correct manifest, activities, and XML files. |
| **Implementation** | Lifecycle methods and Logcat correctly used and activities handled. |
| **Coding** | Code is modular, clean, and self-explanatory. |
| **Outcome** | App performs as required and logs lifecycle events. |

---

**End of Solution Guide**
