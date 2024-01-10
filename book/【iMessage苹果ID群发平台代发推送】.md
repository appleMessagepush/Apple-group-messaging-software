# 【iMessage苹果ID群发平台代发推送】

调试器设置装备摆设办理；
调试器启动、遏制、步进操纵；
源代码、函数、前提、断点和日记点；
仓库跟踪，多线程和多过程支撑；
在视图和 hover 中阅读繁杂的数据结构；
变量值表现在 hover 和源代码中；
watch 表达式管理
主动完成的交互式评价的调试节制台。
2、起头调试
1. 建立一个 testvscodedebug 目次，在此中创建 index.js 文件
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

console.log(isTrue);2. 点击调试按钮

需要创建 launch.json 文件

3. 点击【创建 launch.json】按钮，挑选 NodeJS

会发明在文件夹中多了一个 .vscode 的文件夹，内里有一个 launch.json 文件


4. 从新点击调试

便可开始调试

5. 调试工具栏

● 继承/停息 F5
● 跳过 F10
● 步入 F11
● 走出去 ⇧F11
● 重启 ⇧⌘F5
● 停止 ⇧F5

6. 红点调试
不消在代码里面增加 debugger，在代码侧添加红点，在举行调试。


7. 日志点
在每一行小红点位置上右键点击，选择添加日志点

如：此日志点记实轮回中 i 的值：{i}

实行时能够看到会有日志打印进去。


3、Launch.json 属性
1. 动态配置
{
    // 操纵 IntelliSense 领会相干属性。 
    // 悬停以检察现有属性的描写。
    //     "version": "0.2.0",
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
2. configurations 配置
interface common {
  // 情况范例，好比 node
  type: string
  // debug方法
  request: 'launch' | 'attach'
  // debugger 称号 展如今调试器管理中的名称
  name: string
  // 遵守协定
  protocol: 'auto' | 'inspector' | 'legacy'
  // debug port
  port: number
  // 调试端口的 TCP/IP 地点
  address: string
  // 经由进程将此配置为 true 来启用源映照
  sourceMaps: boolean
  // glob 形式数组，用于定位天生的 JavaScript 文件
  outFiles: array
  // 停止时重新启动会话
  restart: boolean
  autoAttachChildProcesses: boolean
  // 当重新启动会话时，在这个毫秒数以后抛却
  timeout: number
  // 当步伐启动时当即间断
  stopOnEntry: boolean
  // VS Code的根目录
  localRoot: string
  // 节点的根目录
  remoteRoot: string
  // 测验考试自动跳过没有映射到源文件的代码
  smartStep: boolean
  // 自动跳过这些 glob 模式笼盖的文件
  skipFiles: array
  // 是不是启用诊断输出
  trace: boolean
  presentation: {
    // 是否暗藏，true 为隐藏不成见 默许 false
  	hidden: boolean,
    // 排序 数字越小越在前
    order: number,
    // 组，组名一样一个组
    group: string
  }
}
interface launch {
  // 要调试的 Node.js 程序的绝对途径
  program: string
  // 通报给程序调试的参数
  args: array
  // 在这个目录中启动程序进行调试
  cwd: '${workspaceFolder}'
  // 要使用的运转时可执行文件的绝对路径。默认是 node
  runtimeExecutable: 'node' | 'npm' | string
  // 传递给 runtime 可执行文件的可选参数
  runtimeArgs: string
  // 选择 Node.js 的特定版本
  runtimeVersion: string
  // 该属性盼望环境变量作为字符串类型键/值对的列表
  env: {}
  // 包括环境变量界说的文件的可选路径
  envFile: '${workspaceFolder}/.env'
  // 启动程序的控制台
  console: 'internalConsole' | 'integratedTerminal' | 'externalTerminal'
  outputCapture: string
}
interface attach {
  // 使用该processId属性时，调试端口是依照 Node.js 版本（和使用的协议）自动肯定的，不克不及显式配置。以是不要指定 port 属性。
  processId: string3. 特定于平台的属性
Launch.json 支持分歧的操作系统不同的属性值
args 在 windows 上传值，stopOnEntry 在 MacOS 上传值

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
Linux - linux
MacOS - osx
4. Launch vs Attach
launch 是指把 debug sessions 附加到接下来间接启动的 node 调试程序（即跟从 –inspect-brk=port），细致 debug port 得和 –inspect-brk=port 对应；
attach 是指把 debug sessions 附加到指定的正在运行的处于 debug 模式的 node 程序的对应端口上，若是黑白 debug 模式的 node 程序，则需要供给 processId。

5. Source Maps
VS Code 默认会开启 source maps。如果编译后的文件不在同级目录，则需要设置 outFiles attribute 告诉 debug adpater 源文件在哪。

6. 变量更换
VSCode 经常使用的路径和其余一些值可以作为变量使用。

{
  "type": "node",
  "request": "launch",
  "name": "Launch Program",
  "program": "${workspaceFolder}/app.js",
  "cwd": "${workspaceFolder}",
  "args": ["${env:USERNAME}"]1. 变量列表
${workspaceFolder} - 在 VS Code 中翻开的文件夹的路径；


如果用户A（浏览器）用Apache的格局去访问Tomcat办事器，毫无疑义，TomCat没法明白你哀求的内容。

也便是说，浏览器得根据不同的服务器类型，发送不同格式的协议数据包。这的确是太贫苦了！
既然都是访问网站，为何不统一一种数据格式呢？咱们每次访问网站就按照这种格式传递数据不就好了嘛？

是以，国际尺度化组织提出统一的HTTP协议。
全部的浏览器公司，都要按照HTTP协议的设定，来计划本身的程序。
同样的，所有的服务器公司，也要按照HTTP协议的设定，设计自己的服务器程序。

如斯一来，Google浏览器可以用雷同的数据格式访问各类服务器，不仅如此，IE, 360都是如此，大师相处敦睦，通讯不会有题目。

传输层
传输层的代表协议是TCP和UDP。传输层的紧张感化就是控制数据传输过程的靠得住性。（UDP除外）
一样平常来讲，传输层的功效都是由操作系统实现了。

试想，如果Windows和Linux实现不同的传输层协议，那末因为数据格式的差别，彼此之间无法通信。

因此，传输层协议的统一性也是必要的。 它使不同操作系统之间也能进行可靠传输
国际标准化组织就提出了TCP和UDP这两个统一标准。

收集层
网络层同理。它要完成寻址的功能，必定要有同种格式的地址才行。那么IP协议应际而生，通过划定IP地址，在网络中独一标识一台计算机。如果地址格式都不同，那若何寻址？

别的，统一网络层协议，可以让数据包颠末不同厂商出产的路由器进行传布。甭管你是华为路由器仍是TPLink路由器，只有都从命IP协议，那就可以传输数据包。

数据链路层
数据链路层主要卖力一个链路之间信息的传递。

只要你是以太网网卡，那么无论你是哪一个公司生产的，都请求是根据以太网协议设计而来，都能辨认以太网的首部。因此规定了以太网协议。

物理层
我们都晓得，计算机里面都是1010
那么物理传输中，可以用凹凸电平、光、无线旌旗灯号等本领摹拟二进制来传播。
如果通信两边使用的物理协议都纷歧致，那么对信息的理解必然会犯错：


三.总结
为什么网络中要有协议这个观点？
为什么要将相同功能的协议进行统一化？
为什么通信双方要用相同的协议？

为了快捷有用的通信！！！

四. TCP/IP协议简介
现在Internet（因特网）使用的支流协议族是TCP/IP协议族，它是一个分层、多协议的通信体系。简略说一下TCP/IP协议族体系结构以及主要协议

1.TCP/IP协议族体系结构以及主要协议
TCP/IP协议族是一个四层协议系统，自底而上别离是数据链路层、网络层、传输层和应用层。每一层完成不同的功能，且通过多少协议来实现，上层协议使用基层协议提供的服务，以下图所示。


1.1 数据链路层
数据链路层实现了网卡接口的网络驱动程序，以处置数据在物理前言（比如以太网、令牌环等）上的传输。不同的物理网络具备不同的电气特征，网络驱动程序隐藏了这些细节，为上层协议提供一个统一的接口。
数据链路层两个常用的协议是ARP协议（Address Resolve Protocol，地址剖析协议）和RARP协议（Reverse Address Resolve Protocol，逆地址解析协议）。它们实现了IP地址和呆板物理地址（凡是是MAC地址，以太网、令牌环和802.11无线网络都使用MAC地址）之间的互相转换。
网络层使用IP地址寻址一台机器，而数据链路层使用物理地址寻址一台机器，因此网络层必需先将方针机器的IP地址转化成其物理地址，才气使用数据链路层提供的服务，这就是ARP协议的用处。RARP协议仅用于网络上的某些无盘事情站。由于缺少存储设备，无盘工作站无法记着自己的IP地址，但它们可以利用网卡上的物理地址来向网络管理者（服务器或网络管理软件）盘问本身的IP地址。运行RARP服务的网络管理者通常存有该网络上所有机器的物理地址到IP地址的映射。

1.2 网络层
网络层实现数据包的选路和转发。WAN（Wide Area Network，广域网）通常使用浩繁分级的路由器来毗连分离的主机或LAN（Local Area Network，局域网），因此，通信的两台主机一般不是直接相连的，而是通过多个中心节点（路由器）连接的。网络层的使命就是选择这些中间节点，以确定两台主机之间的通信路径。同时，网络层对上层协议隐藏了网络拓扑连接的细节，使得在传输层和网络应用程序看来，通信的双方是直接相连的。
网络层最焦点的协议是IP协议（Internet Protocol，因特网协议）。IP协议根据数据包的目标IP地址来决议如何送达它。如果数据包不能直接发送给目标主机，那么IP协议就为它探求一个符合的下一跳（next hop）路由器，并将数据包交付给该路由器来转发。多次重复这一过程，数据包终极达到目标主机，大概由于发送失利而被抛弃。可见，IP协议使用逐跳（hop by hop）的方式确定通信路径。
网络层别的一个重要的协议是ICMP协议（Internet Control Message Protocol，因特网控制报文协议）。它是IP协议的重要弥补，主要用于检测网络连接。ICMP协议使用的报文格式如下图所示。

上图中，8位类型字段用于区别报文类型。它将ICMP报文分为两大类：一类是不对报文，这类报文主要用来回应网络毛病，比如目标不可到达（类型值为3）和重定向（类型值为5）；另一类是查询报文，这类报文用来查询网络信息，比如ping程序就是使用ICMP报文查看目标是否可到达（类型值为8）的。有的ICMP报文还使用8位代码字段来进一步细分不同的条件。比如重定向报文使用代码值0暗示对网络重定向，代码值1表示对主机重定向。ICMP报文使用16位校验和字段对全部报文（包含头部和内容部门）进行循环冗余校验（Cyclic Redundancy Check,CRC），以查验报文在传输过程中是否毁坏。不同的ICMP报文类型具有不同的注释内容。ICMP报文格式可以参考ICMP协议的标准文档RFC 792。
需要指出的是，ICMP协议并不是严酷意思上的网络层协议，因为它使用处于同一层的IP协议提供的服务（一般来说，上层协议使用下层协议提供的服务）。


${workspaceFolderBasename} - 在 VS Code 中打开的文件夹的名称，不带斜杠(/)；
${file} - 以后打开的文件；
${fileWorkspaceFolder} - 当前打开的文件的工作区文件夹；
${relativeFile} - 相对于于 workspaceFolder 当前打开的文件；
${relativeFileDirname} - 当前打开的文件的目录名；
${fileBasename} - 当前打开的文件的 basename；
${fileBasenameNoExtension} - 当前打开的文件的 basename，没有文件扩展名；
${fileDirname} - 当前打开的文件的 dirname；
${fileExtname} - 当前打开文件的扩展名；
${cwd} - 任务运行程序在启动时的当前工作目录；
${lineNumber} - 选中的文件当前选定的行号；
${selectedText} - 选中的文件中当前选定的文本；
${execPath} - VS Code 可执行文件的运行路径；
${env:Name} - 环境变量；
${config:Name} - 配置变量；
${command:commandID} - command 变量；
${defaultBuildTask} - 默认构建任务的名称；
${pathSeparator} - 用于分开文件路径中的组件的字符；
${input:variableID} - input 输入变量。
2. 示例
假如您有如下需要：

位于在 /home/your-username/your-project/folder/file.ext 编辑器中打开的文件；
该目录 /home/your-username/your-project 作为根工作区打开。
因此，您将具有每一个变量的以下值：
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
${lineNumber} - 光标的行号
${selectedText} - 在代码编辑器当选择的文本
${execPath} - Code.exe 的位置
${pathSeparator} -在 macOS 或 linux 上为 /，在 Windows 上位 \
3. 每个工作区文件夹范畴内的变量
通过将根文件夹的名称附加到变量（用冒号分隔），可以访问工作区的同级根文件夹。如果没有根文件夹名称，该变量的范围将与使用它的文件夹相同。
比方，在具有文件夹 Server 和的多根工作区中 Client， ${workspaceFolder:Client} 指的是 Client 根的路径。

4. 环境变量
您还可以通过 ${env:Name} 语法（例如，${env:USERNAME} ）援用环境变量。

{   
  "type": "node",   
  "request": "launch",   
  "name": "Launch Program",   
  "program": "${workspaceFolder}/app.js",   
  "cwd": "${workspaceFolder}",   
  "args": ["${env:USERNAME}"] 
}
Config 变量
${config:Name}
${config:editor.fontSize}

6. Command 变量
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
7. Input 变量
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

今朝 VS Code 支持三种类型的输入变量：

promptString：显示一个输入框以从用户那边获得字符串。
pickString：显示快速选择下拉菜单，让用户从多个选项中进行选择。
command：运行肆意号令。
PromptString：
description：显示在快速输入中，为输入提供上下文。
default：如果用户不输入其他内容将使用的默认值。
password：设置为 true 以使用不会显示键入值的暗码提醒输入。
PickString：
description：显示在快速选择中，为输入提供上下文。
options：供用户选择的选项数组。
default：如果用户不输入其他内容将使用的默认值。它必须是选项值之一。
Command：
command：在变量插值上运行的命令。
args：传递给命令实现的可选选项包。