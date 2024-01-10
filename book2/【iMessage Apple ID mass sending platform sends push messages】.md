# [iMessage Apple ID mass sending platform sends push on behalf]

Debugger configuration management;
Debugger start, stop, step control;
Source code, functions, premises, breakpoints and journal points;
Warehouse tracking, multi-threading and multi-process support;
Read complex data structures in views and hover;
Variable values are represented in hover and source code;
watch expression management
A debugging console for automated interactive evaluation.
2. Start debugging
1. Create a testvscodedebug directory and create the index.js file in it
const a = '1';
const b = '2';
debugger;
for(let i = 0; i < 10; i++) {
     console.log(i);
}

const arr = [1,2,3,4,5];

const isTrue = arr.some(item => {
     console.log(item);
     return item > 4;
});

console.log(isTrue);2. Click the debug button

Need to create launch.json file

3. Click the [Create launch.json] button and select NodeJS

You will find that there is an additional .vscode folder in the folder, with a launch.json file inside


4. Click debug again

You can start debugging

5. Debugging toolbar

● Sustain/pause F5
● Skip F10
● Step into F11
● Go out ⇧F11
● Restart ⇧⌘F5
● Stop ⇧F5

6. Red dot debugging
There is no need to add a debugger to the code, just add a red dot on the side of the code to debug.


7. Log point
Right-click on the little red dot in each row and select Add Log Point

For example: this log point records the value of i in the cycle: {i}

You can see that logs will be printed when executing.


3. Launch.json attribute
1. Dynamic configuration
{
     // Use IntelliSense to understand related properties.
     // Hover to view the description of an existing property.
     // "version": "0.2.0",
     "configurations": [
      
     ]
}
1
2
3
4
5
6
7
8
9
2. configurations configurations
interface common {
   //Environment example, such as node
   type: string
   // debug method
   request: 'launch' | 'attach'
   // debugger name The name displayed in the debugger management
   name: string
   // abide by the agreement
   protocol: 'auto' | 'inspector' | 'legacy'
   // debug port
   port:number
   // TCP/IP address of the debug port
   address: string
   // Enable source mapping by configuring this to true
   sourceMaps: boolean
   //glob pattern array, used to locate generated JavaScript files
   outFiles: array
   //Restart session when stopped
   restart: boolean
   autoAttachChildProcesses: boolean
   // When restarting the session, abandon after this number of milliseconds
   timeout: number
   // Stop immediately when the program starts
   stopOnEntry: boolean
   //The root directory of VS Code
   localRoot: string
   //Root directory of the node
   remoteRoot: string
   //Try to automatically skip code that is not mapped to the source file
   smartStep: boolean
   // Automatically skip files covered by these glob patterns
   skipFiles: array
   // Whether to enable diagnostic output
   trace: boolean
   presentation: {
     // Whether to hide, true means hidden, default is false
   hidden: boolean,
     // Sort with smaller numbers in front
     order: number,
     //Group, a group with the same group name
     group: string
   }
}
interface launch {
   // The absolute path to the Node.js program to be debugged
   program: string
   //Parameters notified to program debugging
   args: array
   // Start the program in this directory for debugging
   cwd: '${workspaceFolder}'
   // Absolute path to the runtime executable to use. The default is node
   runtimeExecutable: 'node' | 'npm' | string
   // Optional parameters passed to the runtime executable
   runtimeArgs: string
   // Select a specific version of Node.js
   runtimeVersion: string
   // This property expects environment variables as a list of string type key/value pairs
   env: {}
   // Optional path including files defined by environment variables
   envFile: '${workspaceFolder}/.env'
   //Start the program's console
   console: 'internalConsole' | 'integratedTerminal' | 'externalTerminal'
   outputCapture: string
}
interface attach {
   // When using the processId attribute, the debug port is automatically determined based on the Node.js version (and protocol used) and cannot be configured explicitly. So do not specify the port attribute.
   processId: string3. Platform-specific properties
Launch.json supports different property values for different operating systems
args uploads values in Windows, stopOnEntry uploads values in MacOS

{
   "version": "0.2.0",
   "configurations": [
     {
       "type": "node",
       "request": "launch",
       "name": "Launch Program",
       "program": "${workspaceFolder}/node_modules/gulp/bin/gulpfile.js",
       "args": ["myFolder/path/app.js"],
       "windows": {
         "args": ["myFolder\\path\\app.js"]
       },
       "stopOnEntry": true,
       "osx": {
         "stopOnEntry": false
       }
     }
   ]
}

1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
Windows - windows
Linux-linux
MacOS-osx
4. Launch vs Attach
Launch refers to attaching debug sessions to the node debugger that is started indirectly (that is, following –inspect-brk=port). Note that the debug port must correspond to –inspect-brk=port;
Attach refers to attaching debug sessions to the corresponding port of the specified running node program in debug mode. If it is a node program in debug mode, you need to provide the processId.

5. Source Maps
VS Code turns on source maps by default. If the compiled file is not in the same directory, you need to set the outFiles attribute to tell debug adpater where the source file is.

6. Variable replacement
Paths and other values frequently used by VSCode can be used as variables.

{
   "type": "node",
   "request": "launch",
   "name": "Launch Program",
   "program": "${workspaceFolder}/app.js",
   "cwd": "${workspaceFolder}",
   "args": ["${env:USERNAME}"]1. Variable list
${workspaceFolder} - the path to the folder opened in VS Code;


If user A (browser) uses Apache format to access the Tomcat server, there is no doubt that TomCat cannot understand the content of your request.

In other words, the browser has to send protocol data packets in different formats according to different server types. This is indeed too poor!
Since we are all accessing websites, why not unify one data format? Wouldn’t it be great if we just transfer data in this format every time we visit the website?

Therefore, the international standardization organization proposed a unified HTTP protocol.
All browser companies must design their own programs according to the settings of the HTTP protocol.
Similarly, all server companies must design their own server programs in accordance with the HTTP protocol settings.

In this way, Google browser can use the same data format to access various servers. Not only that, but also IE and 360. Everyone can get along well with each other and there will be no communication problems.

transport layer
The representative protocols of the transport layer are TCP and UDP. The important role of the transport layer is to control the reliability of the data transmission process. (Except UDP)
Generally speaking, the functions of the transport layer are implemented by the operating system.

Just imagine, if Windows and Linux implement different transport layer protocols, they will not be able to communicate with each other due to differences in data formats.

Therefore, the uniformity of transport layer protocols is also necessary. It enables reliable transmission between different operating systems
The International Organization for Standardization has proposed two unified standards, TCP and UDP.

collection layer
The same goes for the network layer. To complete the addressing function, it must have addresses in the same format. Then the IP protocol came into being. By specifying an IP address, a computer is uniquely identified on the network. If the address formats are different, how to address them?

In addition, the same network layer protocol allows data packets to be transmitted through routers produced by different manufacturers. Regardless of whether you are a Huawei router or a TPLink router, as long as both comply with the IP protocol, you can transmit data packets.

data link layer
The data link layer is mainly responsible for the transmission of information between links.

As long as you have an Ethernet network card, no matter which company produces it, it is required to be designed according to the Ethernet protocol and be able to recognize the Ethernet header. Therefore the Ethernet protocol is specified.

physical layer
We all know that computers are all 1010
Then in physical transmission, high-level, light, wireless signals and other methods can be used to simulate binary transmission.
If the physical protocols used by both parties in communication are inconsistent, then the understanding of the information will inevitably be wrong:


3. Summary
Why should there be a protocol in the network?
Why should protocols with the same functions be unified?
Why do both parties of communication need to use the same protocol?

For quick and useful communication! ! !

4. Introduction to TCP/IP protocol
The mainstream protocol suite currently used by the Internet is the TCP/IP protocol suite, which is a layered, multi-protocol communication system. Briefly talk about the TCP/IP protocol family architecture and main protocols

1.TCP/IP protocol suite architecture and main protocols
The TCP/IP protocol suite is a four-layer protocol system, which is the data link layer, network layer, transport layer and application layer from bottom to top. Each layer completes different functions and implements them through several protocols. The upper-layer protocol uses the services provided by the base-layer protocol, as shown in the figure below.


1.1 Data link layer
The data link layer implements the network driver of the network card interface to handle the transmission of data on physical media (such as Ethernet, Token Ring, etc.). Different physical networks have different electrical characteristics, and network drivers hide these details and provide a unified interface to upper-layer protocols.
Two commonly used protocols in the data link layer are the ARP protocol (Address Resolve Protocol, address resolution protocol) and the RARP protocol (Reverse Address Resolve Protocol, reverse address resolution protocol). They implement IP addresses and machine physical addresses (usually M