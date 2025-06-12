
# 🧪 Android Lab Quiz 3: Data Passing – Fragment ➝ Activity 

## 🎯 Objective

Build an Android app using **Java** that demonstrates:

1. **Passing data from a Fragment to the Activity**.

---

## 📁 Required Files

```
com.example.fragmenttoactivity
│
├── MainActivity.java
├── InputFragment.java
├── activity_main.xml
├── fragment_input.xml

```

---

## 🎯 Expected Behavior

1. App launches with `InputFragment`.
2. User enters:

```
Name: David
Email: david@gmail.com
```

3. User clicks **SEND DATA**
4. `main activity` appears showing:

```
David
david@gmail.com
```

---

## ✅ Submission Checklist

- [ ] All XML layouts created correctly
- [ ] `InputFragment` sends data using interface
- [ ] `MainActivity` passes data using Bundle

---

## 💡 Tip

If stuck on communication steps:
- Use `Log.d()` to check if the data is being passed.
- Always check for `null` in `getArguments()`.

---

## 🔄 Bonus Task (Optional)

- Add input validation to check if fields are not empty before sending.
- Clear input fields after sending the data.
