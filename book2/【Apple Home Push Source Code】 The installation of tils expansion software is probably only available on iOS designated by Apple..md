# [Apple Home Push Source Code] The tils expansion software installation is probably only available on iOS designated by Apple.

To obtain a Device Token, you need to implement the following steps in your application:

Request user authorization in the application: You need to request user authorization to allow the application to send remote notifications. This can be accomplished by using UNUserNotificationCenter (User Notifications framework). You can present an authorization popup to the user and ask them if they agree to receive notifications.

Register for remote notifications: Once the user has authorized it, you can use the UIApplication.shared.registerForRemoteNotifications() method to register for remote notifications. This will trigger the system to send a device token to your application.

Implement the proxy method to obtain the device token: In your application's proxy class, implement the following method to obtain the device token:

swift
Copy code
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
     //Convert deviceToken into string format to send to the server
     let tokenString = deviceToken.map { String(format: "%02.2hhx", $0) }.joined()
    
     //Send deviceToken to the server
     //Add your code logic here to send tokenString to the server for retention
}

func application(_ application: UIApplication, didFailToRegisterForRemoteNotificationsWithError error: Error) {
     // Failed to register remote notification, handle error
}
The didRegisterForRemoteNotificationsWithDeviceToken method will be called when the device token is successfully obtained. In this method you convert the device token into string format and send it to your server for saving and using.

If registration for remote notifications fails, the system will call the didFailToRegisterForRemoteNotificationsWithError method, where you can handle the error environment.

Send the device token to the server: In the didRegisterForRemoteNotificationsWithDeviceToken method, you need to write code to send the device token to your server. You can send the device token to the server side using a network request or other communication method that suits you.

On the server side, you can save the device token and use it to send push notifications to specific devices.

Please note that device tokens are associated with specific applications and devices, and may change when the application is uninstalled or the device is reset. Therefore, you need to regularly update the device token on the server to ensure that push notifications are accurately sent to the target device.

These are the basic steps to get a device token in an iOS app. The specific implementation may vary depending on the programming language and development framework you use. You can refer to Apple's official documentation and developer resources for more detailed information on remote notification registration and device token acquisition.


To request user authorization in your application to send remote notifications, you need to follow these steps:

Import the UserNotifications framework: In the application code, you first need to import the UserNotifications framework in order to use notification-related classes and methods.

Request authorization: You can request user authorization when the application starts or at the appropriate opportunity by calling the following methods:

swift
Copy code
UNUserNotificationCenter.current().requestAuthorization(options: [.alert, .badge, .sound]) { (granted, error) in
     //Authorization result processing
     if granted {
         // The user has authorized push notifications
     } else {
         // The user declined the push notification or the authorization failed
     }
}
In the above code, the options parameter specifies the notification permissions you need to request, including pop-up notifications, application icon flags, sounds, etc. Appropriately set up to suit your needs.

Handle authorization results: After the authorization request is completed, the system will call the callback closure you provided. In this callback, you can handle the user's authorization results. If the granted parameter is true, it means that the user authorized the push notification; if the granted parameter is false, it means that the user rejected the push notification or the authorization failed. You can perform related operations as needed.
Note that you need to ensure that you configure the relevant permission descriptions in your application's Info.plist file so that the correct authorization reminder is displayed to the user when authorization is requested. The following is an example configuration:

xml
Copy code
<key>NSRemoteNotificationUsageDescription</key>
<string>We need to send a notification to inform you of important information. </string>
In the above example, the NSRemoteNotificationUsageDescription key specifies the description displayed to the user when requesting push notification permissions. You can customize this description based on your application needs.

By following the steps above, your application will be able to request user authorization to send remote notifications and take actions in response based on the user's choice.

Please note that user authorization is part of user privacy, and you need to comply with Apple's privacy policy and best practices, and properly handle user data and privacy when using remote notifications.