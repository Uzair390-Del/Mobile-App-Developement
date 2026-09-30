#  Learning Objectives

By completing this assignment, students will be able to:

- Understand how to manage **version codes** and **version names** in Android apps.  
- Learn how to **generate and sign** an Android App Bundle (AAB) or APK file.  
- Understand the **Play Console workflow** — including developer account setup and app publishing.  
- Produce a **LaTeX-based technical report** explaining the full Play Store publishing process.

---

##  Assignment Components

###  1. Study Materials

Students must carefully study the following tutorial transcripts (provided as VTT files):

- **Part 1:** Understanding APK Release Versions  
- **Part 2:** Generating a Signed APK (or AAB) File  
- **Part 3:** Uploading an App to the Google Play Store  

They can convert the VTTs to readable text using any subtitle-to-text tool or manually extract key concepts.

---

###  2. Understanding Questions

Students must answer the following questions **in their own words** (in LaTeX):

#### **Part 1: APK Versioning**

1. What are `versionCode` and `versionName`, and why are they important?  
2. What happens if you don’t increase the `versionCode` when updating your app?  
3. Where can you find and edit these values in Android Studio?

#### **Part 2: Generating a Signed Build**

4. What is a `.jks` (keystore) file, and why is it critical?  
5. What’s the difference between `.apk` and `.aab` files?  
6. Explain step-by-step how to generate a signed release file in Android Studio.  
7. What precautions should you take with your keystore file and passwords?

#### **Part 3: Publishing to Google Play**

8. What is required to open a Google Play Developer account?  
9. List the major steps involved in publishing an app on the Google Play Console.  
10. What common errors or rejections might occur during app submission, and how can they be avoided?

---

###  3. Practical Task

####  Task:

Create a small Android application (even a basic **“Hello World”** app is fine).  
Then, simulate the following steps:

1. Assign a `versionCode` and `versionName`.  
2. Generate a **signed release (AAB)** file in Android Studio.  
3. *(Optional simulation)* — Take screenshots showing:
   - The `build.gradle` version settings  
   - The “Generate Signed Bundle” window  
   - The resulting `.aab` file in your folder  

> Students do **not** need to actually publish the app — only demonstrate their understanding.
