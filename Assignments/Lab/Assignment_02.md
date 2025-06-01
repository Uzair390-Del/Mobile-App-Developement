
#  Android App Development Lab Assignment

##  Title: Quiz App (Part-1) – Splash, Login, and Firebase Authentication

---

###  Objective:
In this lab, you will begin building the **Quiz App**. This part focuses on creating the **splash screen**, a **login screen**, and **Firebase authentication setup**.

You will:
- Create a **modern splash screen**.
- Design a **user-friendly login screen** with essential fields.
- Add a **Google Sign-In button**.
- Implement **listeners for UI interactions** (e.g., Forgot Password).
- Set up and connect your project to **Firebase Authentication** (Email/Password login only for now).
- Navigate the user to the **next screen (Home/Dashboard Activity)** after login.

---

###  Assignment Tasks

1. **Create a Splash Screen:**
   - Show your app logo or animation.
   - Set a delay (2–3 seconds), then move to the Login Activity.

2. **Design a Unique Login Screen:**
   - Fields: Email, Password.
   - Buttons:
     - "Login"
     - "Google Sign-In" (button design must match Material Design standards)
   - A **"Forgot Password?"** clickable TextView (must be interactive).
   - Good UI/UX design (avoid default-looking forms).

3. **Set up Listeners:**
   - **Login button:** Validate fields and trigger Firebase Email/Password login.
   - **Google Sign-In button:** No need to fully implement for now, just set up the button and listener.
   - **Forgot Password:** Show a toast or navigate to a placeholder activity.

4. **Firebase Authentication:**
   - Set up Firebase in your project.
   - Connect to Firebase Authentication using **Email and Password only**.
   - If login is successful, move to the next screen (e.g., a blank DashboardActivity or HomeActivity).
   - Handle invalid login attempts properly (show error message or toast).

5. **Navigation Flow:**
   - SplashScreen → LoginActivity → HomeActivity (on successful login)

6. **GitHub Help:**
   - You are allowed to **refer to the my GitHub repository** for guidance.

---

###  Technologies to Use:
- Java
- Firebase Authentication (Email/Password)
- Android Studio
- Material Design Components

---

###  Submission Guidelines:
- Include screenshots of working app screens.
- Add a short PDF explaining what you have implemented.
- Upload your project to your own GitHub and share the link.
- - **Deadline:** [June 4,2025]

---

###  Bonus (Optional for Extra Marks):
- Implement Firebase **"Forgot Password"** feature using `sendPasswordResetEmail()`.
- Show animation or transitions in Splash Screen or Login screen.

---


