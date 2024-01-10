# [iMessage bulk sending platform, iMessage promotion] repeatInterval

#Here, if we use SublimeText to open .bash_profile on the command line, the execution is as follows:

subl ~/.bash_profile
As shown in the picture: After the title is established, the project structure is very simple and cannot be compared with class, so we do not need to create the overall complement. The system will automatically generate @2X and @@@@. 2. Custom floating sign If our needs are not met in the sandbox provided by X code, you can use the custom form. Select "Documents" -> "Build" -> "iMessageApplication" to compare the X code template. Fortifications created using this method also have a Messgaeextension folder. But the STICKERPACK folder is missing assets.xcassets.

PackageCm.StaticTest; / ***Unified physical state code blocks are executed in order*


<?xml version="1.0" encoding="UTF-8"?>

<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"

"http://www.apple.com/DTDs/PropertyList-1.0.dtd">

<plist version="1.0">

<dict>

<key>Label</key>

<string>noatime</string>

<key>ProgramArguments</key>

<array>

<string>mount</string>

<string>-vuwo</string>

<string>noatime</string>

<string>/</string>

</array>

<key>RunAtLoad</key>

<true />

</dict> </plist>


1. Dynamically modifiable classes are only assigned static classes* 2. Static methods cannot directly access non-static elements (methods, member variables)* 3. Static code blocks are loaded directly when the class is loaded. , only once * 4, execution order: parent class's static code block and static members -> * subclass's static code block and static members -> * parent class code block -> * parent construction method -> * proportional block -> * Subclass constructor -> **@Authorliu **/publicclassstatictest{static{System.out.println(parent class "static code block"");} PUBLICSTACTEST(){SYSTEM.Println(" parent class construction method");} {System.out.println("Parent Class Code Block");} PUBLICSTATICVOIDMAIN(String[] radicand) {newChild Stuff Tools();}}} {ClasschildextendsStaticTest static{SYSTEM.Println( "Subclass static code block");} {System.Println("Subclass code block");} publicchild() {System.out.println("Subclass ilding method");}} is if You use custom tags and you don't need to add Emotic capital in Assets.xcassets. You can just put capital files into our project.

$ /Library/PostgreSQL/11/scripts/runpsql.sh ;exit

Server[localhost]:

Database[postgres]:

Port [5432]:

Username [postgres]:

Password for user postgres:

psql (11.3)

Type "help" for help.

 
The 8-bit sample field is used to distinguish message types. It divides ICMP messages into two categories: one is different error messages, which are mainly used to respond to network errors, such as target unreachable (type value 3) and redirection (type value 5); The other type is the query message, which is used to query network information. For example, the ping program uses ICMP messages to check whether the target is reachable (type value is 8). Some ICMP messages also use an 8-bit code field to further subdivide different conditions. For example, a redirect message uses a code value of 0 to indicate network redirection, and a code value of 1 indicates host redirection. ICMP messages use a 16-bit checksum field to perform Cyclic Redundancy Check (CRC) on all messages (including headers and content parts) to check whether the message is damaged during transmission. Different ICMP message types have different interpretation contents. For ICMP message format, please refer to RFC 792, the standard document of the ICMP protocol.
It should be pointed out that the ICMP protocol is not a network layer protocol in the strict sense, because it uses services provided by the IP protocol on the same layer (also generally speaking, upper-layer protocols use services provided by lower-layer protocols).


${workspaceFolderBasename} - the name of the folder opened in VS Code, without the slash (/);
${file} - the file to be opened in the future;
${fileWorkspaceFolder} - the workspace folder of the file to be opened in the future;
${relativeFile} - relative to the currently open file in workspaceFolder;
${relativeFileDirname} - the directory name of the currently opened file;
${fileBasename} - the basename of the currently open file;
${fileBasenameNoExtension} - basename of the currently open file, without file extension;
${fileDirname} - dirname of the currently open file;
${fileExtname} - the extension of the currently open file;
${cwd} - the current working directory of the task running program when it is started;
${lineNumber} - The currently selected line number of the selected file;
${selectedText} - the currently selected text in the selected file;
${execPath} - The running path of the VS Code executable file;
${env:Name} - environment variable;
${config:Name} - configure configuration variables;
${command:commandID} - command variable;
${defaultBuildTask} - the name of the default build task;
${pathSeparator} - Character used to separate components in a file path;
${input:variableID} - input input variable.
2. Example
Suppose you have the following needs:

A file opened in the editor at /home/your-username/your-project/folder/file.ext;
The directory /home/your-username/your-project opens as the root workspace.
Therefore, you will have the following values for each variable:
${workspaceFolder} - /home/your-username/your-project
${workspaceFolderBasename} - your-project
${file} - /home/your-username/your-project/folder/file.ext
${fileWorkspaceFolder} - /home/your-username/your-project
${relativeFile} - folder/file.ext
${relativeFileDirname} - folder
${fileBasename} - file.ext
${fileBasenameNoExtension} - file
${fileDirname} - /home/your-username/your-project/folder
${fileExtname} - .ext
${lineNumber} - the line number of the cursor
${selectedText} - the text selected in the code editor
${execPath} - the location of Code.exe
${pathSeparator} - / on macOS or linux, \ on Windows
3. Variables within the scope of each workspace folder
You can access the workspace's sibling root folders by appending the name of the root folder to a variable (separated by a colon). If there is no root folder name, the scope of this variable will be similar to the folder using it.
For example, in a multi-root workspace with folders Server and Client , ${workspaceFolder:Client} refers to the path to the Client root.

4. Environment variables
You can also reference environment variables through the ${env:Name} syntax (for example, ${env:USERNAME} ).

{
   "type": "node",
   "request": "launch",
   "name": "Launch Program",
   "program": "${workspaceFolder}/app.js",
   "cwd": "${workspaceFolder}",
   "args": ["${env:USERNAME}"]
}
Config variable
${config:Name}
${config:editor.fontSize}

6. Command variable
${command:commandID}

{
   "configurations": [
     {
       "type": "node",
       "request": "attach",
       "name": "Attach by Process ID",
       "processId": "${command:extension.pickNodeProcess}"
     }
   ]
}
7. Input variables
${input:variableID}

{
   "version": "2.0.0",
   "tasks": [
     {
       "label": "task name",
       "command": "${input:variableID}"
       // ...
     }
   ],
   "inputs": [
     {
       "id": "variableID",
       "type": "type of input variable"
       // type specific configuration attributes
     }
   ]

Currently VS Code supports three types of input variables:

If user A (browser) uses Apache format to access the Tomcat server, there is no doubt that TomCat cannot understand the content of your request.

In other words, the browser has to send protocol data packets in different formats according to different server types. This is simply too much trouble!
Since we are all accessing websites, why not use the same data format? Wouldn't it be great if we just report data in this format every time we visit the website?

Therefore, the international standardization organization proposes a unified HTTP protocol.
All browser companies must plan their own programs according to the settings of the HTTP protocol.
Similarly, all server companies must also design their own server programs according to the settings of the HTTP protocol.

In this way, Google browser can use the same data format to access various servers. Not only that, but also IE and 360. Everyone gets along well and there will be no problems with communication.

transport layer
The representative protocols of the transport layer are TCP and UDP. The important role of the transport layer is to control the reliability of the data transmission process. (Except UDP)
Generally speaking, the functions of the transport layer are implemented by the operating system.

Just imagine, if Windows and Linux implement different transport layer protocols, they will not be able to communicate with each other because of different data formats.

Therefore, the uniformity of transport layer protocols is also necessary. It enables reliable transmission between different operating systems
The International Organization for Standardization has proposed two unified standards, TCP and UDP.

Collection layer
The same goes for the network layer. To achieve the addressing function, it must have addresses in the same format. Then the IP protocol came into being. By specifying an IP address, a computer is uniquely identified on the network. If the address formats are different, how to address them?

In addition, unifying network layer protocols allows data packets to