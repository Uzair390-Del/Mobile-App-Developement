
#  Android Application Development – Lab on Notifications

##  What You Will Learn
In this lab, we will understand **Notifications** in Android applications — what they are, why we use them, and how they work. This is made so simple that even a 10-year-old can understand it!

---

##  What are Notifications?

**Notifications** are messages that your Android phone shows even when you're not using an app.

Think about when:
- WhatsApp shows "You have a new message!"
- YouTube says "Your favorite channel just posted a video!"
- A calendar tells you "Your class starts in 10 minutes!"

 These are **notifications**!

They help apps talk to us even when we're not using them.

---

##  Types of Notifications

There are mainly **2 types** of notifications you need to know:

### 1.  Local Notifications
These are created **inside the app itself**.

 Think of it like this: The app sets a timer and then says "Time to show a message!"

 Examples:
- Alarm app saying "Wake up!"
- Reminder app saying "Take your medicine."

### 2.  Push Notifications (Remote Notifications)
These come from a **server on the internet** and are pushed to your phone **even if the app is closed**.

 Like your teacher sending a message to the whole class — and your phone shows it.

 Examples:
- Facebook sending "Someone liked your photo!"
- News app sending "Breaking News!"

---

##  Why Use Notifications?

- To **remind** the user (like alarms or events).
- To **alert** the user (like warnings or messages).
- To **engage** users (to open your app again).

---

##  Real-Life Example

Let's say you built a **water reminder app**. You want your phone to remind you every 2 hours:

- A **local notification** will do this — because the app can schedule a message on its own.

Now think of a **chat app**. When your friend messages you, you want to get that message even if the app is not open.

- A **push notification** is perfect here — because the server sends the message to your phone.

---

##  How Do We Implement Notifications?

Let’s now get a *tiny peek* into how these notifications are made in Android apps.

###  1. Local Notification – Example Idea

You can think of this like setting an alarm. When the time comes, the phone says: **“Hey! Time to study!”**

####  Steps:
1. You create something called a **Notification Channel** (like a pipe where notifications travel).
2. You build a **Notification** message.
3. You use something called a **NotificationManager** to show it.

####  Example Code (Beginner View):

```java
NotificationCompat.Builder builder = new NotificationCompat.Builder(this, "my_channel_id")
    .setSmallIcon(R.drawable.ic_notification)
    .setContentTitle("Reminder!")
    .setContentText("Time to drink water 💧")
    .setPriority(NotificationCompat.PRIORITY_DEFAULT);

NotificationManagerCompat notificationManager = NotificationManagerCompat.from(this);
notificationManager.notify(1, builder.build());
```

 This just shows a basic message when the app runs — like an alert.

---

###  2. Push Notification – Example Idea

This one is a bit fancier! The app gets messages from a **server** using something called **Firebase Cloud Messaging (FCM)**.

####  Steps:
1. Connect your app to **Firebase Console**.
2. Add Firebase SDK to your Android app.
3. Get a **token** – this is like your app’s address.
4. When Firebase sends a message, your app receives it in the background.

####  Simple Code Idea (Just Concept):

```java
public class MyFirebaseMessagingService extends FirebaseMessagingService {
    @Override
    public void onMessageReceived(RemoteMessage remoteMessage) {
        // Show a notification when message arrives
        showNotification(remoteMessage.getNotification().getTitle(),
                         remoteMessage.getNotification().getBody());
    }
}
```

This tells Android:  
 “Hey, whenever Firebase sends a message, show it as a notification.”

---

###  Don't Worry!  
You don’t have to remember the code right now. Just remember:

- Local = Phone shows message by itself.
- Push = Firebase sends a message and the app catches it.

 In future labs, you will learn how to:
- Create channels
- Add icons and actions to notifications
- Set timings
- Send Firebase messages

---

##  Summary

| Type of Notification | Who Sends It?         | When It's Shown           | Example                    |
|----------------------|-----------------------|----------------------------|----------------------------|
| Local Notification   | Your App (on device)  | At scheduled time / event | Alarm, Reminder App        |
| Push Notification    | Server via Firebase   | Any time (even if app off)| WhatsApp, Facebook alerts  |

---

 That’s it! You now understand what notifications are, their types, and even a small glimpse of how they’re created in Android apps.
