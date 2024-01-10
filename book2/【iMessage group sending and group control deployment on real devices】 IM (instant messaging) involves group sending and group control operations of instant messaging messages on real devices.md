iPhone/iOS development drives C++ Server APNS source code

First, you must control the user email address used with the AppID mailbox. Best salutation is also used with AppID's username. If the configuration of the configuration is incorrect, tokens may be generated.


If you have two certificates on your computer, such as a company account on your computer and a developer account for your company. Don't feel like you can use CSR and have to use two different email requests twice. In other words, the CSR email must be similar to the AppID to which the certificate belongs. If you can receive the token in the program, the program is successful.


Establishing a connection to APNs requires manipulation of the APNs communication protocol. APNs provides two communication protocols for selection:

HTTP/2 protocol: This is the newer and recommended communication protocol. Using the HTTP/2 protocol, you can communicate with the APNs server by establishing a TLS (Transport Layer Security) connection. It provides higher efficiency and performance, and supports multiplexing, allowing multiple push requests to be sent simultaneously.
           <key>title</key>
                 <string>Test APP without Appstore installation style</string>
             </dict>
         </dict>
     </array>
</dict>
</plist>

**Let’s talk about the top ten reasons why iOS APPs are rejected from the App Store and how to deal with them: **

Apple officials have announced the top ten reasons why iOS applications are rejected to help IOS developers better manage iOS applications that meet Apple's standards for listing.

Among the top ten reasons listed by Apple officials, the highest proportion is "incomplete information submission", reaching 14%.

This may be due to incomplete description of the iOS application information, or the developer may have forgotten to include a link to the support page.

1. Register in the name of the company
2. Whether in the name of a company or an individual, you must apply for an appleId first, because the following registrations are all based on appleId.


12. day and end
12.1 Terminology
This Agreement shall not be delayed until the one (1) year anniversary of the initial step activation date of the Account (the "Effective Date"). Thereafter, upon your payment of the annual renewal fee and compliance with the terms of this Agreement, the term will automatically renew for a period of one year (1) unless terminated earlier in accordance with this Agreement.

12.2 Stop
This Agreement and all rights and licenses vested in Apple, and any services provided hereunder will cease, effective immediately upon withdrawal of notice from Apple:
(a) If you or any of your Authorized Developers fail to comply with any provision of this Agreement other than as set forth in this Section 12.2 and are unable to cure such breach or receive notice within 30 days of becoming aware of such breach;
(b) if you or any of your authorized developers fail to comply with Section 10 of the Terms;


$ make
Making all for application firstdemo…
  Compiling main.m…
  Compiling firstdemoApplication.mm…
  Compiling RootViewController.mm…
  Linking application firstdemo…
  Stripping firstdemo…
  Signing firstdemo…



The circumstances of the event are described in (c) above in the subsection entitled "Severability";
(d) If you, at any time, initiate patent infringement proceedings against Apple;
(e) if you cease business, are unable to pay your debts as they become due, dissolve or cease doing business, file for bankruptcy, or file a petition for bankruptcy or prosecution against you; or
(f) If you engage in, or encourage others to engage in, any misleading, false, inappropriate, illegal or dishonest activity in connection with this Agreement, including, but not limited to, misrepresenting the nature of the submitted Application (e.g., concealing or attempting to Hide results from Apple's inspections, fake consumer objections for your app, handle fraud, payments, etc.).

Apple may also terminate this Agreement, or extinguish your right to use the Apple Software or Services, if you are unable to comply with any new requirements or terms of the Agreement as set forth in Section 4.

For its convenience, either party may terminate this Agreement for any or no reason, providing written notice of its intention to terminate to the other party 30 days after it becomes effective.

Binary protocol: This is an older communication protocol that uses a custom binary format for communication. Using the binary protocol, you need to establish a TCP connection based on TLS, and then send push requests and receive responses according to a specific binary format.

Depending on your needs and skills, you can choose to use one of these protocols to connect to APNs. Your server-side code then needs to implement the communication protocol with APNs, including establishing the connection, sending push requests, and processing responses.

Detailed implementation processes and code examples can be found in Apple's developer documentation. Apple provides sample code and libraries for different programming language security platforms to help you communicate with APNs. You can refer to Apple's official documentation and developer resources to learn how to use libraries and code examples that are appropriate for your technology stack.

Please note that communicating using APNs requires the use of conforming certificates and keys for authentication and secure communication. Make sure you authenticate with the correct certificates and keys when connecting to APNs, and follow Apple's security requirements
/**
  * Define an agent and ask other classes to help this class complete other tasks. This class uses the delegate defined above to take care of other classes that implement the above protocol.
  */
@property (nonatomic, weak) id<AccountDelegate>delegate;

@end






/* This call lets you get an xpc_object_t that holds a reference to the IOSurface.
    Note: Any live XPC objects created from an IOSurfaceRef implicity increase the IOSurface's global use
    count by one until the object is destroyed. */
 
/*xpc_object_t IOSurfaceCreateXPCObject(IOSurfaceRef aSurface) XPC_RETURNS_RETAINED
     IOSFC_AVAILABLE_STARTING(__MAC_10_7, __IPHONE_NA);*/
 
 
/* This call lets you take an xpc_object_t created via IOSurfaceCreatePort() and recreate an IOSurfaceRef from it. */
 
/*IOSurfaceRef IOSurfaceLookupFromXPCObject(xpc_object_t xobj) CF_RETURNS_RETAINED
     IOSFC_AVAILABLE_STARTING(__MAC_10_7, __IPHONE_NA);
*/

Below I will provide some more detailed information to help you understand the characteristics and usage of these two communication protocols:

HTTP/2 protocol:

HTTP/2 is a newer and recommended communication protocol designed to provide a more efficient and performance-optimized transmission method.
It uses TLS (Transport Layer Security) protocol for encryption to ensure communication security.
HTTP/2 supports multiplexing, allowing multiple push requests to be sent simultaneously on a single connection, reducing the overhead of connection establishment.
It uses binary framing to communicate, dividing requests and responses into smaller frames, and exchanging and reassembling them out of order.
HTTP/2 provides header compression function to reduce the amount of data transmitted.
Using HTTP/2 can use network bandwidth more efficiently, providing faster push transfers and better performance.
Binary protocol:

Binary protocol is an older communication protocol that uses a custom binary format for data transmission.
It also uses TLS (Transport Layer Security) protocol for encryption to ensure communication security.
Unlike HTTP/2, the binary protocol requires establishing a TCP connection based on TLS and sending push requests and receiving responses in a specific binary format.
Binary protocols require manual encoding and decoding of data, dealing with the details of data formats and protocols.
Since the binary protocol is customized, you need to have a certain understanding of the protocol specifications and details during the development process.
Overall, the HTTP/2 protocol is the more modern and recommended choice, offering greater compliance, performance, and security. It supports multiplexing, has header compression, and makes better use of network bandwidth. The binary protocol is of course older, but it can still be used, especially in specific situations or for some specific needs.

When you implement communication with APNs, you can choose to use the protocol that suits your needs, selecting and configuring it according to your technology stack and development environment. Please be careful, no matter which protocol you use, to ensure you follow Apple's security requirements and best practices.

Hope this helps you better understand HTTP/2 and binary protocols! If you have any further questions, please feel free to ask.

Second, use PushMebaby to push the service end. Note that its serial number must comply with its original space format (if it is used directly). Then the serial number generated by the development certificate can only correspond to the development certificate. If you want to use the product certificate for the first time. Because you must wait for the software version before getting the product serial number, debug on the server serial number on the server.

Third, you can find a replacement certificate that will not connect to the Apple Push Server, you have to remember the address of the development certificate and the address of the product certificate, as well as quite a few words that will calculate the connection address length. topic.

Fourth, if you use the serial number of the development certificate, you will test on Server Pushmebaby, you will find it, click on the three folds. The solution is to quickly release future software, download it using your test phone, let the background get a serial number, and then use this serial number as the debug serial number for the background product certificate. In fact, this method is the second point, but the problem is still stuck.

Fifth, Apple's push to a C++ server is different from PHP, which requires secret certification and development certificate integration with CK.PEM. Objc is not an indirect development certificate. In C+ with background I used an iPhone
iPhone connects to the system on the system without playing a role
Once logged in, you can copy photos. But then during the copy process it "doesn't even play the device on the system" like this:
iPhone connects to the system on the system without playing a role




Solution, input, camera, format, select "Compatibility", the default is efficient, select "Compatibility" videos and images do not use the new format of HEVC, continue to use the old MPEG format. Exporting videos and images will not convert formats and will have the above prompts.
Probably, enter "Set photo", see bottom, change "Auto" to "Keep original photo". You can also guard against copying drawbacks. Because of the change, the format will not be converted and the new format file will be copied directly. Once you see that, I will see that your computer CPU is not giving power, so the new format is to decode the CPU decoding function.
My solution was to change the format to "Compatibility" and then transfer to "Reserve Original Photos", and the problem was solved!