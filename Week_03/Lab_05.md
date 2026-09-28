# Android Activity Lifecycle and Intents

## Introduction
Android applications consist of one or more activities. An activity represents a single screen with a user interface. The Android system manages the lifecycle of an activity through various stages.

### **Activity Lifecycle Stages:**
1. **onCreate()**: Called when the activity is first created. Used to initialize components.
2. **onStart()**: Called when the activity becomes visible to the user.
3. **onResume()**: Called when the activity starts interacting with the user.
4. **onPause()**: Called when the activity is partially obscured by another activity.
5. **onStop()**: Called when the activity is no longer visible.
6. **onDestroy()**: Called before the activity is destroyed.

## **Understanding Intents in Android**
An **Intent** is a messaging object used to request an action from another activity. There are two types of intents:

1. **Explicit Intent:** Used to launch a specific activity within your app.
2. **Implicit Intent:** Used when you want to perform an action without specifying the target component (e.g., opening a web page).

### **Key Methods:**
- `Intent()` constructor: Creates a new intent.
- `startActivity()` method: Starts a new activity.

## **Detailed Code Explanation**

### **1. MainActivity.java**
```java
package com.example.applicationlifecycle;

import android.content.Intent;
import android.os.Bundle;
import android.util.Log;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;

public class MainActivity extends AppCompatActivity {
    TextView textView;
    Button btn1;
    Button btn2;
    int counter;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_main);

        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main), (v, insets) -> {
            Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom);

            textView = findViewById(R.id.textView);
            btn1 = findViewById(R.id.btn1);
            btn2 = findViewById(R.id.btn2);

            btn1.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View v) {
                    counter = counter + 1;
                    textView.setText("" + counter);
                }
            });

            btn2.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View v) {
                    Intent i = new Intent(getApplicationContext(), MainActivity2.class);
                    startActivity(i);
                }
            });

            Log.d("Message", "First Activity onCreate");
            return insets;
        });
    }

    @Override
    protected void onStart() {
        super.onStart();
        Log.d("Main Activity", "First Activity onStart message is called");
    }

    @Override
    protected void onResume() {
        super.onResume();
        Log.d("Main Activity", "First Activity onResume message is called");
    }

    @Override
    protected void onPause() {
        super.onPause();
        Log.d("Main Activity", "First Activity onPause message is called");
    }

    @Override
    protected void onStop() {
        super.onStop();
        Log.d("Main Activity", "First Activity onStop message is called");
    }

    @Override
    protected void onDestroy() {
        super.onDestroy();
        Log.d("Main Activity", "First Activity destroy message is called");
    }
}
```

### **Explanation:**
1. **onCreate() Method:**
   - Initializes UI components (`TextView`, `Button`).
   - Sets click listeners to buttons.
   - Logs a message when `onCreate()` is called.

2. **Button Actions:**
   - `btn1`: Increments a counter and updates the `TextView`.
   - `btn2`: Launches `MainActivity2` using an explicit intent.

3. **Lifecycle Methods:**
   - Each lifecycle method logs a message when it is called.

### **2. MainActivity2.java**
```java
package com.example.applicationlifecycle;

import android.content.Intent;
import android.os.Bundle;
import android.util.Log;
import android.view.View;
import android.widget.Button;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;

public class MainActivity2 extends AppCompatActivity {

    Button btn3;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_main2);

        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main2), (v, insets) -> {
            Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom);

            btn3 = findViewById(R.id.btn3);

            btn3.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View v) {
                    Intent i = new Intent(getApplicationContext(), MainActivity.class);
                    startActivity(i);
                }
            });

            Log.d("Message", "Second Activity onCreate");
            return insets;
        });
    }

    @Override
    protected void onStart() {
        super.onStart();
        Log.d("Main Activity", "Second Activity onStart message is called");
    }

    @Override
    protected void onResume() {
        super.onResume();
        Log.d("Main Activity", "Second Activity onResume message is called");
    }

    @Override
    protected void onPause() {
        super.onPause();
        Log.d("Main Activity", "Second Activity onPause message is called");
    }

    @Override
    protected void onStop() {
        super.onStop();
        Log.d("Main Activity", "Second Activity onStop message is called");
    }

    @Override
    protected void onDestroy() {
        super.onDestroy();
        Log.d("Main Activity", "Second Activity destroy message is called");
    }
}
```

### **Explanation:**
1. Initializes `btn3` which navigates back to `MainActivity`.
2. Logs each lifecycle method call for tracking activity behavior.

## **Conclusion:**
This lab helps students understand:
- Android activity lifecycle methods.
- Using explicit intents to navigate between activities.
- Managing UI components and event listeners.

