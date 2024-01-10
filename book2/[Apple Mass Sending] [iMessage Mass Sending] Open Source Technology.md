# [Apple Mass Sending] [iMessage Mass Sending] Open Source Technology

To obtain a Device Token, you need to implement the following steps in your application:

Request user authorization in the application: You need to request user authorization to allow the application to send remote notifications. This can be done using UNUserNotificationCenter (User Notifications framework). You can display an authorization popup to the user asking if they want to allow notifications.

Register for remote notifications: Once the user authorizes it, you can use the UIApplication.shared.registerForRemoteNotifications() method to register for remote notifications. This will trigger the system to send a device token to your application.

Implement the proxy method to get the device token: In your application's proxy class, implement the following method to get the device token:

# Recommended content IMESSGAE related

Recommended content by the author ✈️@IMEAX |[***iMessage Apple recommended software***] *** Click to view the content information requested by the author
-------- | -----
Recommended content by author ✈️@IMEAX |[***1. Family recommended content***] *** Click to view the content information requested by the author
Recommended content by the author ✈️@IMEAX |[***2. Album recommendation***]*** Click to view the content information requested by the author
Recommended content by the author ✈️@IMEAX |[***3. Calendar recommendation***] *** Click to view the content information requested by the author
Recommended content by the author ✈️@IMEAX |[***4. Simple virtual machine installation***] *** Click to view the content information requested by the author
Recommended content by the author ✈️@IMEAX |[***5.iMessage***] *** Click to view the content information requested by the author

swift
Copy code
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
     //Convert deviceToken to string format to send to the server
     let tokenString = deviceToken.map { String(format: "%02.2hhx", $0) }.joined()
    
     //Send deviceToken to the server
     //Add your code logic here and send tokenString to the server for storage
}

func application(_ application: UIApplication, didFailToRegisterForRemoteNotificationsWithError error: Error) {
     //Registration for remote notification failed, error handling
}
The didRegisterForRemoteNotificationsWithDeviceToken method will be called when the device token is successfully obtained. In this method you convert the device token to string format and send it to your server for saving and using.

If registration for remote notifications fails, the system calls the didFailToRegisterForRemoteNotificationsWithError method, where you can handle the error condition.

Send the device token to the server: In the didRegisterForRemoteNotificationsWithDeviceToken method, you need to write code to send the device token to your server. You can send the device token to the server using a network request or other communication method that suits you.

On the server side, you can save the device token and use it to send push notifications to specific devices.

Please note that device tokens are associated with specific applications and devices and may change when the application is uninstalled or the device is reset. Therefore, you need to regularly update the device token on the server to ensure that push notifications are properly sent to the target device.

These are the basic steps to get a device token in an iOS app. The specific implementation may vary depending on the programming language and development framework you use. You can refer to Apple's official documentation and developer resources to learn more details about remote notification registration and device token acquisition.


To request user authorization in your application to send remote notifications, you need to follow these steps:

Import the UserNotifications framework: In your application's code, you first need to import the UserNotifications framework in order to use notification-related classes and methods.

Request authorization: You can request user authorization when your application starts or at an appropriate time by calling the following methods:

swift
Copy code
UNUserNotificationCenter.current().requestAuthorization(options: [.alert, .badge, .sound]) { (granted, error) in
     //Authorization result processing
     if granted {
         // The user has authorized push notifications
     } else {
         // The user rejected the push notification or the authorization failed
     }
}
In the above code, the options parameter specifies the notification permissions you need to request, including pop-up notifications, application icon marks, sounds, etc. Configure appropriately according to your needs.

Handle authorization results: After the authorization request is completed, the system will call the callback closure you provided. In this callback, you can handle the user's authorization results. If the granted parameter is true, it means that the user authorized the push notification; if the granted parameter is false, it means that the user rejected the push notification or the authorization failed. You can perform related actions as needed.
Note that you need to ensure that you configure the relevant permission descriptions in your application's Info.plist file so that the correct authorization prompt is displayed to the user when authorization is requested. The following is an example configuration:

# Recommended content IMESSGAE related

Recommended content by the author ✈️@IMEAX |[***iMessage Apple recommended software***] *** Click to view the content information requested by the author
-------- | -----
Recommended content by author ✈️@IMEAX |[***1. Family recommended content***] *** Click to view the content information requested by the author
Recommended content by the author ✈️@IMEAX |[***2. Album recommendation***]*** Click to view the content information requested by the author
Recommended content by the author ✈️@IMEAX |[***3. Calendar recommendation***] *** Click to view the content information requested by the author
Recommended content by the author ✈️@IMEAX |[***4. Simple virtual machine installation***] *** Click to view the content information requested by the author
Recommended content by the author ✈️@IMEAX |[***5.iMessage***] *** Click to view the content information requested by the author

xml
Copy code
<key>NSRemoteNotificationUsageDescription</key>
<string>We need to send a notification to deliver important information to you. </string>
In the above example, the NSRemoteNotificationUsageDescription key specifies the description displayed to the user when requesting push notification permissions. You can customize this description based on your application needs.

By following the steps above, your application will be able to request user authorization to send remote notifications and take appropriate actions based on the user's selections.

Please note that user authorization is part of user privacy, and you need to follow Apple's privacy policy and best practices and properly handle user data and privacy when using remote notifications.


On MAC OS systems, Apple provides a script called Apple script to automatically implement tasks.

The Apple script code to implement iMessage group sending is as follows:

tell application "Messages"
set csvDatatoread "/Users/dengzhenhua/Desktop/send.txt"

set csvEntriestoparagraphsofcsvData

repeat with ifrom 1tocountcsvEntries

set phone to (csvEntries'sitemi)'stext

set myid to get idof firstservice

set theBuddy to buddyphoneof serviceidmyid

send "It will be sunny in Beijing today, with a temperature of 13 to 27 degrees; it will be sunny on Tuesday, with a temperature of 11 to 26 degrees, and a northerly wind of level 3-4; it will be sunny on Wednesday, with a temperature of 11 to 24 degrees, with a breeze <3 ---- Pinluo Internet www.pinluo .com"totheBuddy

delay 1

set FailNum to (getcountchat)

if FailNum > 100 then

repeat withjfrom 1 to FailNum



end tell