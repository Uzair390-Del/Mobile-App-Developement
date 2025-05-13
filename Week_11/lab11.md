  ## Lab Title: Data Transfer Between Components (Activities and Fragments)

---

## Lab Objectives:

By the end of this lab, students will be able to:

- Transfer data from **Activity to Activity**
- Transfer data from **Activity to Fragment**
- Transfer data from **Fragment to Fragment**
- Understand how to use `Intent`, `Bundle`, and Fragment communication techniques

---

##  Part 1: Data Transfer - Activity to Activity

We’ll create a simple Sign-Up form in one Activity and send that data to another Activity to display it.

---

###  Project Structure

```
- MainActivity.java  → Input from user
- SecondActivity.java → Receive and display data
- activity_main.xml
- activity_second.xml
```

---

###  MainActivity.java

```java
package com.example.sendingdatabetweenactivities;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    EditText editName, editEmail, editPhoneNumber;
    Button signUp;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Getting references to views
        editName = findViewById(R.id.editName);
        editEmail = findViewById(R.id.editEmail);
        editPhoneNumber = findViewById(R.id.editPhoneNumber);
        signUp = findViewById(R.id.button);

        // Set click listener on the sign up button
        signUp.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Read user input
                String userName = editName.getText().toString();
                String userEmail = editEmail.getText().toString();
                String phoneNumber = editPhoneNumber.getText().toString();

                // Create Intent to start SecondActivity
                Intent i = new Intent(MainActivity.this, SecondActivity.class);

                // Attach data using key-value pairs
                i.putExtra("name", userName);
                i.putExtra("email", userEmail);
                i.putExtra("phone", phoneNumber);

                // Start SecondActivity
                startActivity(i);
            }
        });
    }
}
```

---

###  activity_main.xml (Simplified layout structure)

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <EditText android:id="@+id/editName"
        android:hint="Enter Name"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <EditText android:id="@+id/editEmail"
        android:hint="Enter Email"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <EditText android:id="@+id/editPhoneNumber"
        android:hint="Enter Phone Number"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button android:id="@+id/button"
        android:text="Sign Up"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />
</LinearLayout>
```

---

###  SecondActivity.java

```java
package com.example.sendingdatabetweenactivities;

import android.content.Intent;
import android.os.Bundle;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class SecondActivity extends AppCompatActivity {
    TextView name, email, phone;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_second);

        // Connect views from layout
        name = findViewById(R.id.textViewName);
        email = findViewById(R.id.textViewEmail);
        phone = findViewById(R.id.textViewPhone);

        // Receive intent and extract data
        Intent i = getIntent();
        String userName = i.getStringExtra("name");
        String userEmail = i.getStringExtra("email");
        String userPhone = i.getStringExtra("phone");

        // Set received data to TextViews
        name.setText("Hello, " + userName);
        email.setText("Your email is " + userEmail);
        phone.setText("Your phone number is " + userPhone);
    }
}
```

---

###  activity_second.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <TextView android:id="@+id/textViewName"
        android:textSize="20sp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

    <TextView android:id="@+id/textViewEmail"
        android:textSize="20sp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

    <TextView android:id="@+id/textViewPhone"
        android:textSize="20sp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />
</LinearLayout>
```

---

## What You Learned in This Part

✅ How to send data from one activity to another  
✅ How to use `Intent` and `putExtra()`  
✅ How to retrieve data using `getIntent().getStringExtra()`  

---

##  Next Steps

- ✅ Part 2: Data Transfer from Activity to Fragment
- ✅ Part 3: Data Transfer from Fragment to Fragment
