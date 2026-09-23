# Android Development - Activity Lifecycle

## Introduction to Activity Lifecycle

In Android development, an **Activity** represents a single screen with a user interface. When a user interacts with an app, different activities get created and destroyed based on their actions.

The **Activity Lifecycle** defines the states an activity goes through from creation to destruction. Understanding the lifecycle helps in managing UI updates, handling resources efficiently, and ensuring a smooth user experience.

## Activity Lifecycle Stages

An activity goes through multiple lifecycle stages controlled by **callback methods**. The key lifecycle methods in an activity are:

### 1. **onCreate()**
- Called when the activity is first created.
- Used for **initializing components** like UI, variables, database connections, etc.
- Called **only once** during the lifetime of an activity.

#### Example:
```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);
    Log.d("Activity Lifecycle", "onCreate called");
}
```

### 2. **onStart()**
- Called when the activity becomes **visible** to the user.
- UI components are rendered but the activity is not yet interactive.
- Called **every time** the activity moves from "stopped" to "visible" state.

#### Example:
```java
@Override
protected void onStart() {
    super.onStart();
    Log.d("Activity Lifecycle", "onStart called");
}
```

### 3. **onResume()**
- Called when the activity is **ready for user interaction**.
- The activity is now in the **foreground** and receives input events.
- Used for tasks like starting animations, tracking user actions, resuming a paused video, etc.

#### Example:
```java
@Override
protected void onResume() {
    super.onResume();
    Log.d("Activity Lifecycle", "onResume called");
}
```

### 4. **onPause()**
- Called when the activity is still visible but no longer in the foreground.
- Used to **pause ongoing tasks**, such as stopping animations, saving unsaved changes, etc.
- The activity might be partially covered by another activity.

#### Example:
```java
@Override
protected void onPause() {
    super.onPause();
    Log.d("Activity Lifecycle", "onPause called");
}
```

### 5. **onStop()**
- Called when the activity is **completely hidden** from the user.
- Used to **release heavy resources** (e.g., closing database connections).
- The activity is still in memory but not visible.

#### Example:
```java
@Override
protected void onStop() {
    super.onStop();
    Log.d("Activity Lifecycle", "onStop called");
}
```

### 6. **onDestroy()**
- Called when the activity is being **removed from memory**.
- Used for final clean-up tasks, releasing resources, and avoiding memory leaks.
- Called **only once** before the activity is destroyed.

#### Example:
```java
@Override
protected void onDestroy() {
    super.onDestroy();
    Log.d("Activity Lifecycle", "onDestroy called");
}
```

### 7. **onRestart()**
- Called if the activity is coming back to the foreground after being stopped.
- Used to **refresh UI elements** and reload data if needed.

#### Example:
```java
@Override
protected void onRestart() {
    super.onRestart();
    Log.d("Activity Lifecycle", "onRestart called");
}
```

---

## Activity Lifecycle Flow
The sequence of method calls based on user interactions:

1. **Launch App** → `onCreate()` → `onStart()` → `onResume()` (Now Active)
2. **Home Button Pressed** → `onPause()` → `onStop()`
3. **Reopen App** → `onRestart()` → `onStart()` → `onResume()`
4. **Back Button Pressed** → `onPause()` → `onStop()` → `onDestroy()`

### Activity Lifecycle Diagram
```
[onCreate()] → [onStart()] → [onResume()] → (Running)
       ↓              ↓             ↓
[onPause()] ← [onStop()] ← [onDestroy()]
       ↓              ↓
    (Background) → (Killed)
```

## Practical Example: Logging Activity Lifecycle
To observe the lifecycle in action, we add log statements inside each method and run the app.

#### Example:
```java
import android.os.Bundle;
import android.util.Log;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Log.d("Lifecycle", "onCreate called");
    }

    @Override
    protected void onStart() {
        super.onStart();
        Log.d("Lifecycle", "onStart called");
    }

    @Override
    protected void onResume() {
        super.onResume();
        Log.d("Lifecycle", "onResume called");
    }

    @Override
    protected void onPause() {
        super.onPause();
        Log.d("Lifecycle", "onPause called");
    }

    @Override
    protected void onStop() {
        super.onStop();
        Log.d("Lifecycle", "onStop called");
    }

    @Override
    protected void onDestroy() {
        super.onDestroy();
        Log.d("Lifecycle", "onDestroy called");
    }

    @Override
    protected void onRestart() {
        super.onRestart();
        Log.d("Lifecycle", "onRestart called");
    }
}
```

### Running the App:
1. Open **Logcat** in Android Studio.
2. Filter logs using **"Lifecycle"** keyword.
3. Perform different actions (minimize app, reopen, press back) and observe logs.

## Summary
✔ **onCreate()** → Initialize UI & components
✔ **onStart()** → Activity becomes visible
✔ **onResume()** → Activity is interactive
✔ **onPause()** → Save unsaved changes, stop animations
✔ **onStop()** → Release heavy resources
✔ **onDestroy()** → Clean up before activity is removed
✔ **onRestart()** → Restart a stopped activity

## Homework
1. Modify the above code to **display lifecycle changes in a Toast message** instead of Logcat.
2. Create a **second activity** and navigate between them to observe lifecycle transitions.
3. Research **savedInstanceState** to learn how to retain UI state during configuration changes.

---
