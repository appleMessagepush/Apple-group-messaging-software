# 【Apple Group iMessage Push Protocol Push】HEAD: Ask the server for a response consistent with the GET request

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

//Setting window properties

     glfwWindowHint (GLFW_CONTEXT_VERSION_MAJOR, 3);

     glfwWindowHint (GLFW_CONTEXT_VERSION_MINOR, 2);

     glfwWindowHint (GLFW_OPENGL_FORWARD_COMPAT, GL_TRUE);

     glfwWindowHint (GLFW_OPENGL_PROFILE, GLFW_OPENGL_CORE_PROFILE);

// glfwWindowHint(GLFW_CONTEXT_VERSION_MAJOR, 3);

// glfwWindowHint(GLFW_CONTEXT_VERSION_MINOR, 3);

// glfwWindowHint(GLFW_OPENGL_PROFILE, GLFW_OPENGL_CORE_PROFILE);

     GLFWwindow* window = glfwCreateWindow(SCR_WIDTH, SCR_HEIGHT, "OpenGL", NULL, NULL);

     if (window == NULL) {

         std::cout << "Failed to create GLFW window" << std::endl; glfwTerminate();

         return -1;

     }

     glfwMakeContextCurrent(window);

     // glad: load all OpenGL function pointers


Before IOS7, Apple generated similar DeviceTokens for multiple apps on one device.
In IOS7 and later, Apple generates different DeviceTokens for multiple apps on a device.

}
VBoxManage setextradata "Mac OS virtual machine name" "VBoxInternal/Devices/efi/0/Config/DmiSystemVersion" "1.0"



VBoxManage setextradata "Mac OS virtual machine name" "VBoxInternal/Devices/efi/0/Config/DmiBoardProduct" "Iloveapple"



VBoxManage setextradata "Mac OS virtual machine name" "VBoxInternal/Devices/smc/0/Config/DeviceKey" "ourhardworkbythesewordsguardedpleasedontsteal(c)AppleComputerInc"



VBoxManage setextradata "Mac OS virtual machine name" "VBoxInternal/Devices/smc/0/Config/GetKeyFromRealSMC" 1

This new change has caused a mapping table of old and new tokens to be created on APNS. If you continue to use the old token, there is no problem. However, once the server uses the new DeviceToken, the records in the mapping table will be deleted. This means that the old DeviceToken cannot be used and will inevitably fail.
To be verified: In IOS5 and IOS6, the APP can always obtain the DeviceToken. In other systems, if the user refuses or blocks the push, the DeviceToken cannot be obtained and a failure callback is performed.
Generating a certificate requires detailed steps:
Apple developer accounts are divided into several roles
Agent: Agent, with the highest authority, can access iTunes Connect.
Admin: Administrator, with the authority to manage members, protect device lists, maintain APPIDs and certificate lists.
Member: Normal member, read-only permission.

Note: After testing on September 11, 2013, I found that the certificate generation mechanism was updated when Apple’s website was offline some time ago. In the past, the keychain was used to generate a CSR file, which could be disabled. However, now whenever you want to generate a certificate, you need to convert it into a CSR file in advance when doing generate. Otherwise, the certificates you generate will be invalid, fake certificates, especially PUSH ones. The server side is basically using this type of certificate. Unable to establish a connection with APNS. This weird problem is super difficult to track! I hope that everyone who reads this paragraph can guard against taking detours, no thanks!

I also encountered various problems while using PushMeBaby. First of all, although the .cer public key certificate has been used in the project, there must be a certificate with a private key in the local keychain, otherwise the connection cannot be successfully established. And it should be noted that the certificate is best placed in the "login" group, otherwise the program will not be able to find the private key. Secondly, in the original project, there will be an infinite loop when scanningString, so it needs to be modified to the following code:
NSUInteger count = 0;
while(![scanner isAtEnd]) {undefined
[scanner scanHexInt:&value];
value = htonl(value);
[deviceTokenData appendBytes:&value length:sizeof(value)];
if (++count >= [self.deviceToken length]-1) {undefined
break;
}
}

Apple has disabled the SSL3.0 connection method on the server side due to bug reasons. Currently only TLS connections are supported.
1. If the device corresponding to the deviceToken is offline on the APNS server when pushing, Apple will retain the push information for "a period of time." When the machine returns to online status, push information to the machine. If the machine is offline for a long time, Apple will discard the message. There is no explicit description of how long this "period of time" lasts, and I don't know if Apple has dynamically adjusted this period of time under different circumstances, so it is impossible to predict the impact of this period of time on the information loss environment.
2. For continuous push, for offline devices, Apple will only permanently store the latest message, and the previous message will be discarded.
3. When there are multiple push tasks, Apple recommends using a single connection to send continuously instead of repeatedly switching connections, otherwise Apple will consider it a D-O-S attack and reject it. If there are multiple servers, they can be connected to APNS concurrently to share the push tasks and perform the tasks more efficiently.
4． When sending multiple push tasks, if one of them uses an incorrect deviceToken, the connection will be disconnected, causing the subsequent push tasks to stop executing. Apple uses a "The Feedback Service" service to regularly report the provider's invalid deviceToken list. How to use this service to access Apple's official documentation is detailed in the attached link.

@Test

     public void hashTest(){

         Jedis jedis = jedisPool.getResource();

 

         // Add the following product inventory to the hash structure

         // iphone11 => 10000

         // macbookpro => 9000

         jedis.hset("goods","iphone11","10000");

         jedis.hset("goods","macbookpro","9000");

 

         // Get all the products in the hash

         System.out.println("All products:");

         Set<String> goodSet = jedis.hkeys("goods");

         for (String good : goodSet) {

             System.out.println(good);

         }

 

         //Add 3000 macbookpro stocks

         System.out.println("Added 3000 macbookpro stocks:");

         System.out.println(jedis.hincrBy("goods", "macbookpro", 3000));

 

         // Delete all hash data

         jedis.del("goods");

 

         jedis.close();

     }

The apns device token corresponding to the Development and Production versions is different. The former is obtained under the mobileprovision of develop. The latter is obtained from production's mobileprovision.
The two versions of Development and Production can share an App ID (not recommended. When sharing, you must delete the app on the device before each debugging and repackage and generate it. And sharing the app ID will often make you crazy. If you do it in the morning, it will not work in the afternoon. So Not recommended), but you cannot share a mobileprovision, so you need to generate a separate Distribution certificate for the production version.
Note: The Distribution version cannot be debugged on the device!
The code signs of the Development and Production versions are different. The former is iPhone Developer and the latter is iPhone Distribution. Be careful not to make a mistake.


<?xml version="1.0" encoding="UTF-8"?>

<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList