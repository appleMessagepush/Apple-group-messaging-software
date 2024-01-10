# [Apple group sending iMessage protocol group sending software]

To implement APNs authentication for iMessage push, here are the general steps:

Create an Apple Developer Account: Make sure you have an Apple Developer Account. If not, please register for a developer account.

Log in to the Apple Developer Center: Log in to the Apple Developer Center (developer.apple.com) using your developer account.

Create an app identifier: In the Developer Center, go to Certificates, Identifiers & Profiles and select Identifiers. Click the "+" sign to create a new App ID, making sure the "App IDs" option is selected.

Configure App Identifier: Provide a name and a unique Bundle Identifier for your App Identifier. Make sure the "Push Notifications" feature is enabled in the "Capabilities" option.
In any application, excessive round trip will definitely affect performance.
b. Next is the detailed http protocol. Each time a general request is responded to, the client and server are required to encrypt/decrypt the content of the session. Although the symmetric encryption/decryption efficiency is relatively high, the simulation still consumes too much CPU, so there is a special SSL chip for this purpose. If the CPU power is relatively low, the performance will inevitably be reduced and more requests will not be served. The amount of data will increase after encryption. These processes are why so many security authentication prompts appear.

URI defines a unified resource identification in an abstract, high-level concept, while URL and URN are specific methods of resource identification. Both URL and URN are a type of URI. Abstractly speaking, every URL is a URI, but not every URI is a URL. This is because URIs also include a subclass, the Uniform Resource Name (URN), which names the resource but does not specify how to locate the resource. The mailto, news, and isbn URIs below are examples of URNs.

In Java's URI, a URI instance can represent absolute or relative, as long as it conforms to the syntax of URI. The URL class not only conforms to the semantics, but also contains information about locating the resource, so it cannot be relative.
   In the Java class library, the URI class does not include any methods to access resources, and its only function is analysis.
   In contrast, the URL class opens a stream to a resource.

4. Introduction to 8 request models of HTTP protocol
The HTTP protocol defines eight methods or "actions" to express different ways of controlling the resources specified by Request-URI. The details are as follows:

OPTIONS: Returns the HTTP request methods supported by the server for specific resources. You can also manipulate sending '*' requests to the web server to test the functionality of the server.
HEAD: Ask the server for a response consistent with the GET request, but the response body will not be returned. This method allows you to obtain meta-information contained in the response headers without having to transmit the entire response content.
GET: Make a request to a specific resource.
POST: Submit data to the specified resource for processing request (such as submitting a form or uploading a file). The data is included in the request body. POST requests may result in the creation of new resources and/or modification of existing resources.
PUT: Upload the latest content to the specified resource location.
DELETE: Requests the server to delete the resource identified by Request-URI.
TRACE: Echo the request received by the server, mainly used for testing or diagnosis.
Create APNs keys: On the "Certificates, Identifiers & Profiles" page, select the "Keys" option. Click the "+" sign to create a new key, give it a name, and make sure the "Apple Push Notifications service (APNs)" option is selected.

Download the APNs key: After creating the APNs key, download the generated key file (.p8 format) and save it to a safe location.

Register your app: In Xcode, open your app project, select your target, and go to the "Signing & Capabilities" tab. Make sure you select the correct developer account and add your app identifier under "Push Notifications".

Use APNs key: When implementing the code on the server side, use the APNs key file (.p8 format) you downloaded for authentication. Depending on the programming language and framework you use, there are corresponding libraries or tools available to handle APNs authentication and the sending of push notifications.

Please note that these steps provide general guidance and actual operations may vary due to updates to the Apple Developer Center interface and processes. Therefore, it is recommended to refer to the official documentation and guides from the Apple Developer Center for the latest detailed steps and instructions.


Apple has disabled the SSL3.0 connection method on the server side due to bug reasons. Currently only TLS connections are supported.
1. If the device corresponding to the deviceToken is offline on the APNS server when pushing, Apple will retain the push information for "a period of time." When the machine comes back online, push information to the machine. If the machine is offline for a long time, Apple will discard the message. There is no explicit description of how long this "period of time" lasts, and I don't know if Apple has dynamically adjusted this period of time under different circumstances, so it is impossible to predict the impact of this period of time on the information loss environment.
2. For continuous push, for offline devices, Apple will only permanently store the latest message, and the previous message will be discarded.
3. When there are multiple push tasks, Apple recommends using a single connection to send continuously instead of repeatedly switching connections, otherwise Apple will consider it a D-O-S attack and reject it. If there are multiple servers, they can be connected to APNS concurrently to share the push tasks and perform the tasks more efficiently.
4. When sending multiple push tasks, if one of them uses an incorrect deviceToken, the connection will be disconnected, causing the subsequent push tasks to stop executing. Apple uses a "The Feedback Service" service to regularly report the provider's invalid deviceToken list. How to use this service to access Apple's official documentation is detailed in the attached link.

@Test

     public void hashTest(){

         Jedis jedis = jedisPool.getResource();

 

         // Add the following product inventory to the hash structure

         // iphone11 => 10000

         // macbookpro => 9000

         jedis.hset("goods","iphone11","10000");

         jedis.hset("goods","macbookpro","9000");