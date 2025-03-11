# Lab: Dice Rolling App in Android

## **Objective**
In this lab, students will learn about Android layouts (LinearLayout and RelativeLayout), basic Java concepts for Android development, and event handling using an OnClickListener. By the end of this lab, students will create a simple dice-rolling app with UI components and Java functionality.

![Dicee Application](Dicee.png)
---

## **1. Understanding Layouts in Android**

### **LinearLayout**
A LinearLayout arranges its child views either horizontally or vertically. It is useful when we want to align elements in a single direction.

#### **Key Properties:**
- android:orientation="vertical" → Arranges views in a column.
- android:orientation="horizontal" → Arranges views in a row.
- android:layout_weight → Controls how much space a view should take relative to other views.

### **RelativeLayout vs. LinearLayout**
| Feature         | LinearLayout  | RelativeLayout |
|----------------|--------------|---------------|
| Child Alignment | Aligns children in a single direction (horizontal/vertical). | Allows positioning of elements relative to each other. |
| Flexibility | Less flexible when designing complex UIs. | More flexible, can position views anywhere. |
| Performance | Faster for simple UIs. | Slightly slower for complex layouts. |

### **Example XML Code for Layout**
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/main"
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:paddingLeft="16dp"
    android:paddingRight="16dp"
    android:paddingTop="16dp"
    android:orientation="vertical"
    android:paddingBottom="16dp"
    android:background="@drawable/newbackground"
    tools:context=".MainActivity">

    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="250dp">

        <ImageView
            android:id="@+id/image_dice_logo"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            app:srcCompat="@drawable/dicee_logo"
            android:layout_centerHorizontal="true"/>
    </RelativeLayout>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

        <ImageView
            android:id="@+id/image_leftDice"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            app:srcCompat="@drawable/dice1" />

        <ImageView
            android:id="@+id/image_RightDice"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            app:srcCompat="@drawable/dice2" />
    </LinearLayout>

    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent">

        <Button
            android:id="@+id/Roll_btn"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_centerInParent="true"
            android:layout_centerHorizontal="true"
            android:backgroundTint="#5462B1"
            android:text="@string/button_name"
            android:textColor="@color/white"
            android:textSize="20sp" />
    </RelativeLayout>
</LinearLayout>
```

---

## **2. Java Basics for Android**
Before diving into the implementation, let's understand some core Java concepts used in Android development.

### **AppCompatActivity & Inheritance**
Android activities extend AppCompatActivity, which provides backward compatibility features and support for modern UI elements.

java
public class MainActivity extends AppCompatActivity {


#### **What is Inheritance?**
- Inheritance allows a class to acquire properties and behaviors of another class.
- MainActivity extends AppCompatActivity, meaning it inherits all methods and properties of AppCompatActivity.
- This enables MainActivity to function as an Android activity.

#### **What is Method Overriding?**
- Overriding occurs when a subclass provides a specific implementation of a method already defined in its superclass.
- Example:
  
java
  @Override
  protected void onCreate(Bundle savedInstanceState) {
      super.onCreate(savedInstanceState);
  }

- The onCreate() method in MainActivity overrides the one in AppCompatActivity, modifying its behavior.

### **Difference Between Inheritance and Method Overriding**
| Feature | Inheritance | Method Overriding |
|---------|------------|-----------------|
| Purpose | Allows a class to reuse another class’s code. | Allows a subclass to modify a superclass method. |
| Involves | extends keyword. | @Override annotation. |
| Example | class B extends A {} | @Override void method() {} |

### **OnClickListener Explained**
An OnClickListener is used to handle button clicks in Android.

java
Roll_btn.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        // Code to execute on button click
    }
});

- setOnClickListener() registers a listener for button clicks.
- new View.OnClickListener() creates an anonymous inner class to handle clicks.
- onClick(View v) is the method executed when the button is clicked.

---

## **3. Understanding the Dice Rolling App Code**

### **Java Code: MainActivity.java**

```java
package com.example.mydiceapplication;

import android.os.Bundle;
import android.util.Log;
import android.view.View;
import android.widget.Button;
import android.widget.ImageView;
import androidx.appcompat.app.AppCompatActivity;
import java.util.Random;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button rollButton = findViewById(R.id.Roll_btn);
        final ImageView leftDice = findViewById(R.id.image_leftDice);
        final ImageView rightDice = findViewById(R.id.image_RightDice);
        final int[] diceArray = {R.drawable.dice1, R.drawable.dice2, R.drawable.dice3, R.drawable.dice4, R.drawable.dice5, R.drawable.dice6};

        rollButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Random rand = new Random();
                int number1 = rand.nextInt(6);
                int number2 = rand.nextInt(6);
                leftDice.setImageResource(diceArray[number1]);
                rightDice.setImageResource(diceArray[number2]);
            }
        });
    }
}
```
---
## 2. Java Basics for Android
### 2.1 Java Essentials for Android Development
- **Classes & Objects:** Used to define components and functionalities.
- **Methods:** Define actions in an app.
- **Variables:** Store data values.
- **Listeners:** Capture user interactions (e.g., button clicks).

---
## 3. Step-by-Step Breakdown of Dice App Code

### 3.1 Java Code (`MainActivity.java`)
```java
package com.example.mydiceapplication;

import android.os.Bundle;
import android.util.Log;
import android.view.View;
import android.widget.Button;
import android.widget.ImageView;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;

import java.util.Random;

public class MainActivity extends AppCompatActivity {
```
**Explanation:**
- `import android.widget.*;` → Imports UI elements like `Button`, `ImageView`.
- `extends AppCompatActivity` → Inherits from `AppCompatActivity` to create the main screen.
- `onCreate(Bundle savedInstanceState)` → Initializes the activity when the app starts.

```java
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_main);
```
**Explanation:**
- `super.onCreate(savedInstanceState);` → Calls parent class constructor.
- `setContentView(R.layout.activity_main);` → Links this Java file to the XML layout.

```java
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main), (v, insets) -> {
            Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom);
```
**Explanation:**
- Ensures the layout adjusts properly to different screen sizes and notches.

```java
            Button Roll_btn;
            Roll_btn = findViewById(R.id.Roll_btn);
            final ImageView image_leftDice = findViewById(R.id.image_leftDice);
            final ImageView image_RightDice = findViewById(R.id.image_RightDice);
```
**Explanation:**
- Declares `Button` and `ImageView` variables.
- `findViewById(R.id.Roll_btn);` → Finds the button from the XML layout.
- `final ImageView image_leftDice` → Represents the left dice image.
- `final ImageView image_RightDice` → Represents the right dice image.

```java
            final int[] diceArray = {
                R.drawable.dice1,
                R.drawable.dice2,
                R.drawable.dice3,
                R.drawable.dice4,
                R.drawable.dice5,
                R.drawable.dice6
            };
```
**Explanation:**
- An array of dice images (`dice1` to `dice6`).

```java
            Roll_btn.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View v) {
                    Log.d("MainActivity", "Roll button clicked!");
                    Random randomNumberGenerator = new Random();
                    int number = randomNumberGenerator.nextInt(6);
                    Log.d("Dicee", "The Random number is " + number);
                    image_leftDice.setImageResource(diceArray[number]);
                    number = randomNumberGenerator.nextInt(6);
                    Log.d("Dicee", "The Random number is " + number);
                    image_RightDice.setImageResource(diceArray[number]);
                }
            });
```
**Explanation:**
- `setOnClickListener` → Waits for the button to be clicked.
- `Random randomNumberGenerator = new Random();` → Generates a random number.
- `number = randomNumberGenerator.nextInt(6);` → Picks a number from 0-5 (mapping to dice images).
- `image_leftDice.setImageResource(diceArray[number]);` → Updates the left dice image.
- `image_RightDice.setImageResource(diceArray[number]);` → Updates the right dice image.

---
## 4. XML Code Breakdown (`activity_main.xml`)
```xml
<LinearLayout android:orientation="vertical">
```
- UI elements are stacked vertically.

```xml
<RelativeLayout android:layout_height="250dp">
    <ImageView android:src="@drawable/dicee_logo"/>
</RelativeLayout>
```
- The logo is centered using `RelativeLayout`.

```xml
<LinearLayout android:orientation="horizontal">
    <ImageView android:id="@+id/image_leftDice"/>
    <ImageView android:id="@+id/image_RightDice"/>
</LinearLayout>
```
- Displays two dice side by side.

```xml
<Button android:id="@+id/Roll_btn" android:text="Roll Dice"/>
```
- Creates a roll button.

---
## Homework
1. Modify the app to roll **three dice** instead of two.
2. Change the button color when clicked.
3. Display a **toast message** showing the sum of both dice rolls.

---
**End of Lab** 