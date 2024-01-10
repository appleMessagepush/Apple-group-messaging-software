# [iMessage Apple bulk advertising software technology]

Change the pop-up dialog box to the directory where the relevant tag request file is located, and then select and open the CSR file. Click "Continue APNS-10.png11"

(iv) Apple's permitted use, promotion or delivery of Your Licensed Application, Licensed Application Information, OS X Website Push Notification, Safari Extension (if applicable), Pass, Pass Information, metadata, related trademarks and logos, or images and other materials that You provide to Apple under this Agreement, including Schedule 2 or Schedule 3 (if applicable); (v) any claims, including but not limited to any end-user claims, regarding Your Covered Products, Licensed Application Information, Pass Information, or related logos, trademarks, content or images; or (vi) Your use (including Your Authorized Developers' use) of the Apple Software or services, Your Licensed Application Information, Pass Information, metadata, Your Authorized Test Devices, Your Registered Devices, Your Covered Products, or Your development and distribution of any of the foregoing.
You acknowledge that the Apple Software and Services were developed to cover products, defective or inaccurate content, results, services, data or information provided by any of the foregoing or that any corruption of the foregoing may result in death, personal injury, or serious physical or environmental damage, and, to the extent permitted by law, you hereby agree to indemnify, protect and hold harmless each Apple and other Apple Indemnifiers for any losses resulting from any such manipulation.
In no event shall you enter into any agreement or agreement with a third party that affects Apple's rights in any manner or will be transferred to Apple, without the prior written consent of Apple.




author$ $THEOS/bin/nic.pl
NIC 1.0 - New Instance Creator
——————————
   [1.] iphone/application
   [2.] iphone/library
   [3.] iphone/preference_bundle
   [4.] iphone/tool
   [5.] iphone/tweak
Choose a Template (required): 1




After downloading the relevant files, you should generate the certificate. Click the "Load" button such as Download Certificate to open the downloaded certificate file, usually open .apns-11. PNG12 Retrieve the certificate and private key to the newly opened certificate in the regular keychain, and then click the right triangle to open the certificate and display the corresponding private key APNS-12.png13. Use the public copy of the private copy that was created when importing the public copy, click on the private key part, and click "Export Frequency Name" APNS-13.PNG14. Javamail com.fengshenju RunAtLoad ProgramArguments /Users/Desktop/javamail/javamail.sh


# Import which node to check the nodejs installation location just now
(base) yudd@ydduongs-MacBook-Air ~ % which node
/usr/local/bin/node
 
# Install picgo (enter password later): sudo npm install picgo -g
(base) yudd@ydduongs-MacBook-Air ~ % sudo npm install picgo -g
Password:
npm WARN deprecated request-promise-native@1.0.9: reque can be directly entered without setting up
(base) yudd@ydduongs-MacBook-Air ~ % picgo set uploader
?Choose a(n) uploader gitee
? repo: yddhhhg/markdown-img
? branch: master
? token: bc48xxxxxxxxxxxxxxxxx9f49260
? path:
? customPath: default
?customUrl:
[PicGo SUCCESS]: Configure config successfully!
 
#Select the default gitee as the default image bed
(base) yudd@ydduongs-MacBook-Air ~ % picgo use uploader
?Use an uploader gitee
[PicGo SUCCESS]: Configure config successf3.1 IOS 13 adaptation
3.1.1 LaunchImage to be deprecated
Since iOS 8, Apple has introduced LaunchScreen. We can configure the device to arrange LaunchScreen as the startup page. Of course, now you can also use LaunchImage to set the launch image. However, using LaunchImage requires us to provide launch images of various screen sizes to adapt to various devices. As Apple device sizes increase, this method is obviously not flexible enough. If you use LaunchScreen, the situation will become very simple. LaunchScreen supports AutoLayout+SizeClass, so it can be easily adapted to various screens.

To be specific⚠️, starting from April 2020, all apps using the iOS13 SDK will be required to provide LaunchScreen, and LaunchImage will soon withdraw from the stage of history*.
3.1.2 Sign in with Apple - Provide details of third-party login
If your application uses a third-party login, you may also need to add "Sign in with Apple"
Sign In with Apple will be available for beta testing this summer. It will be required as an option for users in apps that support third-party sign-in when it is commercially available later this year.

How to integrate? You can refer to this blog: Sign in with Apple
3.1.3 iOS 13 DeviceToken has changes
NSString *dt = [deviceToken description];
dt = [dt stringByReplacingOccurrencesOfString: @"<" withString: @""];
dt = [dt stringByReplacingOccurrencesOfString: @">" withString: @""];
dt = [dt stringByReplacingOccurrencesOfString: @" " withString: @""];
This code can no longer obtain the correct DeviceToken string when running on iOS 13. The content obtained through [deviceToken description] in iOS 13 has changed.

Planning
- (void)application:(UIApplication *)application didRegisterForRemoteNotificationsWithDeviceToken:(NSData *)deviceToken
{
     if (![deviceToken isKindOfClass:[NSData class]]) return;
     const unsigned *tokenBytes = [deviceToken bytes];
     NSString *hexToken = [NSString stringWithFormat:@"%08x%08x%08x%08x%08x%08x%08x%08x",
                           ntohl(tokenBytes[0]), ntohl(tokenBytes[1]), ntohl(tokenBytes[2]),
                           ntohl(tokenBytes[3]), ntohl(tokenBytes[4]), ntohl(tokenBytes[5]),
                           ntohl(tokenBytes[6]), ntohl(tokenBytes[7])];
     NSLog(@"deviceToken:%@",hexToken);
}

3.1.4 MPMoviePlayerController is no longer available in iOS 13
‘MPMoviePlayerController is no longer available. Use AVPlayerViewController in AVKit.’


StartInterval 60 StartCalendarInterval Weekday 1 Hour 8 Minute 58 Weekday 2 Hour 8 Minute 52 StandardOutPath /Users/Desktop/javamail/stdout.log StandardErrorPath /Users/Desktop/javamail/stderr.log Keep the exported private key file to select the storage location, and then Entry to collect private key username selection. Click "Warehouse APNS-14.png15" for P12 pattern

If necessary, set optional password protection for .p12 files. You can set a protection password for stored .p12 files. Then click "Direct click Password" without setting a password. APNS-15.png Now you have a .p12 format file which includes the primary private key