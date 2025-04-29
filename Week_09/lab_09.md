##  Lab: Adapters, ListView, ScrollView, Spinner

---

##  What is an Adapter in Android?

###  Real-life Example:

**Think about a waiter in a restaurant.**

- You (the user) want to see the menu and order food.
- The food (data) is in the kitchen (database or array).
- But you can't go directly to the kitchen — instead, the waiter brings the menu to you and takes your order back.

 In Android:
- The **data** (like a list of student names, products, etc.) is the kitchen.
- The **views** (like ListView, Spinner) are the menu shown to users.
- The **Adapter** is the **waiter** that connects the two!

---

##  Why Do We Need an Adapter?

- Android views like **ListView** or **Spinner** **can’t understand raw data** like arrays or database records directly.
- We need an Adapter to:
  - Pick the data (like a list of names),
  - Format it (using layout),
  - Send it to the view (ListView, Spinner, etc.)

---

##  Types of Adapters

### 1. **ArrayAdapter** –  Simple Lists

Use this when you have:
- A list of strings, numbers, or any simple data.
- Example: Student names, city names, subjects.

```java
String[] cities = {"Lahore", "Karachi", "Islamabad"};
ArrayAdapter<String> adapter = new ArrayAdapter<>(this, android.R.layout.simple_list_item_1, cities);
```

---

### 2. **BaseAdapter** –  Fully Custom Layouts

Use this when:
- You want to design your **own layout** for each item in the list (e.g., showing image + name + rating).
- You have **complex data**, like a list of students with names, photos, roll numbers.

**Example Use Case:**
- An app like FoodPanda showing restaurants – each list item has an image, name, rating, and distance.

**In BaseAdapter, you:**
- Create a custom layout (XML),
- Write Java code to map each view (like ImageView, TextView),
- Control how each list item looks.

> It's more coding but gives **full control** over how the list looks.

---

### 3. **CursorAdapter** –  Data from Database

Use this when:
- Your data is stored in a **SQLite database**.
- You use a **Cursor** to get that data (row by row).
- Ideal for apps with stored data like:
  - Contact apps,
  - Notes apps,
  - Attendance systems.

**Example Use Case:**
- A student database with roll numbers, names, and marks.
- You fetch the records using a **Cursor**.
- `CursorAdapter` takes those rows and shows them in a ListView.

> CursorAdapter helps **bind each row** from the database to a view like ListView.

---

##  Views That Use Adapter

- **ListView** – Vertical list of items.
- **Spinner** – Drop-down menu.
- **GridView** – Items in a grid (like photos).
- **RecyclerView** – More powerful version of ListView (used in advanced apps).

---

## What is ListView?

**ListView** shows items one below the other, like a contact list or settings.

### Example of ListView with ArrayAdapter:

```java
String[] subjects = {"Math", "English", "Science"};

ListView listView = findViewById(R.id.listView);
ArrayAdapter<String> adapter = new ArrayAdapter<>(
    this,
    android.R.layout.simple_list_item_1,
    subjects
);

listView.setAdapter(adapter);
```

 Output: A list showing "Math", "English", and "Science".

---

##  What is ScrollView?

Imagine you created a long form with many fields. But your phone screen is small. You need to scroll.

**ScrollView** lets you **scroll vertically** through content that doesn’t fit on one screen.

### Example of ScrollView:

```xml
<ScrollView
    android:layout_width="match_parent"
    android:layout_height="wrap_content">

    <LinearLayout
        android:orientation="vertical"
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

        <!-- Add multiple TextViews, EditTexts, Buttons here -->

    </LinearLayout>
</ScrollView>
```

Use ScrollView when you want users to scroll down to see more content.

---

## 🎛️ What is Spinner?

**Spinner** = Dropdown menu.

Just like when you fill out a form and pick your **gender**, **country**, or **favorite subject**.

### Example of Spinner with ArrayAdapter:

```java
Spinner spinner = findViewById(R.id.spinner);
String[] countries = {"Pakistan", "India", "USA"};

ArrayAdapter<String> adapter = new ArrayAdapter<>(
    this,
    android.R.layout.simple_spinner_item,
    countries
);

adapter.setDropDownViewResource(android.R.layout.simple_spinner_dropdown_item);
spinner.setAdapter(adapter);
```

 Output: A dropdown with "Pakistan", "India", and "USA".

---

##  Recap (Your Quick Notes)

| Concept         | What It Means                              | When to Use It                               |
|-----------------|---------------------------------------------|----------------------------------------------|
| **Adapter**     | Connects data and view                      | Always – if your view needs data             |
| **ArrayAdapter**| For simple string/number lists              | Student names, subjects, cities              |
| **BaseAdapter** | For custom-designed list items              | Custom layouts with images and multiple views|
| **CursorAdapter**| Shows data from database using a Cursor    | Student records, attendance, saved contacts  |
| **ListView**    | Vertical list of items                      | Contact list, subject list                   |
| **ScrollView**  | Lets you scroll long content                | Forms, long text                             |
| **Spinner**     | Dropdown menu for selection                 | Country, gender, class selection             |
