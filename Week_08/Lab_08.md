
# ✅ Lab : SharedPreferences in Android

## 🧠 Introduction
In Android development, sometimes we need our apps to remember things — like if a user logged in, their name, or any simple settings like sound on/off. For this purpose, SharedPreferences is used.

It’s like a small notebook 📒 in your phone where the app can write and read information — and it stays even after the app is closed.

---

## 📚 Theory Recap
SharedPreferences is a simple way to store small pieces of data in the form of key-value pairs.

### 🔧 Functions You’ll Use:

| Function | Purpose |
|---------|---------|
| `getSharedPreferences()` | Used to access preferences from multiple activities or app-wide. |
| `putString()`, `putInt()`, `putBoolean()` | Used to store data. |
| `getString()`, `getInt()`, `getBoolean()` | Used to retrieve data. |

> 💡 Only primitive data types can be stored, like `String`, `int`, `boolean`, etc.

---

## 📱 App Overview (What This Lab Will Build)
We’re going to make an Android app that:

- Takes **user name** and **message** input.
- Has a button to **increase a counter**.
- Includes a checkbox to **remember the user**.
- Saves all the data using **SharedPreferences**.
- Restores and displays this data when the app is reopened.

Basically, it remembers everything you did the last time you used it.

---

## 🤖 Understanding SharedPreferences!
Imagine you have a drawer at home where you keep:

- Your favorite toy’s name
- Your notebook with your score
- A sticky note that says "I brushed my teeth today!"

SharedPreferences is like that drawer — but inside your phone.  
You put stuff there so your app doesn’t forget the next day!

---

## ✨ Why Is SharedPreferences Useful?
- You don’t want users to **log in again and again**.
- You want to remember if a switch was ON or OFF.
- You want to save a score or last message typed.

**Example:**  
When a user logs in successfully, we store a “login flag” that says `true`.

Then next time the app opens:
- If it sees `true`, it skips login and takes the user to the **home screen**.
- If not, it shows the **login screen**.

On logout? We clear the flag — just like erasing the board 🧽

---

## 🗂️ Real-World Use in This Lab
In this lab:
- We will ask for **user input** (name and message).
- We will **remember the input** using SharedPreferences.
- When the app opens again, we’ll **show the stored data**.
- A **counter** will increase on each button press and also be saved.
- The **checkbox** will save whether the user wanted to be remembered.

---

## 🔄 How It Works (Behind the Scenes)
1. **User enters data** → app saves it using `putString()` etc.
2. **User checks checkbox** → flag is saved with `putBoolean()`.
3. **User taps button** → counter goes up and is saved.
4. **App is closed** → data is safe because it's stored.
5. **App is reopened** → data is loaded using `getString()`, `getInt()`, etc.

---

## 📌 Key Concepts You’ll Learn
- What is SharedPreferences and why it’s used
- How to save and retrieve:
  - Strings (user name, message)
  - Integers (counter)
  - Booleans (checkbox state)
- How to **make your app smart** so it remembers users
- How to **clear the data** when needed

---

## 🧑‍🎓 Key Points (Lab Summary)
- SharedPreferences is a **simple way to store small data**.
- It uses **key-value pairs** (like a dictionary).
- It can store **primitive data types** only.
- Data is **saved permanently** until cleared.
- Great for login status, user preferences, and small data.

**In this lab, we:**
- Take and save user input (name, message)
- Save a counter and checkbox state
- Restore all data on next app launch
