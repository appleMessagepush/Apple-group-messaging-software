# [iMessage Apple group push, IM group sending platform push, Apple push service] You can save the device token and use it to send push notifications to specific devices

The industry terminology for “iMessages bulk sending” calls this “Apple push message”.

To put it bluntly, it is to send messages to a group of people using Apple devices.

### What is iMessage?

Apple official description: [About iMessage and SMS/MMS] [About iMessage and SMS/MMS]

> iMessages are texts, photos, or videos you send to iOS devices and Macs over Wi-Fi or cellular data networks. The information is sent through Apple, not the carrier, and appears encrypted in a blue text bubble. To turn iMessage on or off, go to Settings > Messages.

iMessage is a free messaging application that comes with Apple devices (iPad, iPhone, iPod touch). Its messages are sent over the network, unlike carrier text messages.

### How to implement iMessage group sending?

Apple official tutorial: [Send a group message on iPhone, iPad, or iPod touch][Send a group message on iPhone, iPad, or iPod touch]

Of course, you will definitely scold me after reading the tutorial. I guess this is not what you want to see. You want to complete the promotion of company operations, send iMessages to many, many, many people, and send mass spam messages, right?

[Here] [How to implement iMessage group sending] There is an article for reference.

I didn't try it in depth, and I didn't achieve mass distribution. Just control the Messages client through AppleScript script to send small batches.
#### AppleScript code for sending iMessage
Store the phone number in a `.csv` file separated by `,` and read and send it through a script.
```javasCript
tell application "Messages"
set csvData to read "/Users/xxx/Desktop/test.csv"
set csvEntries to paragraphs of csvData
repeat with i from 1 to count csvEntries
set phone to (csvEntries's item i)'s text
set myid to get id of first service
set theBuddy to buddy phone of service id myid
send "It will be sunny in Beijing today, with a temperature of 13 to 27 degrees; it will be sunny on Tuesday, with a temperature of 11 to 26 degrees, with a northerly wind of level 3-4; it will be sunny on Wednesday, with a temperature of 11 to 24 degrees, with a slight breeze <3" to theBuddy
end repeat
end tell
```

AppleScrip:

AppleScript is a scripting language built with OSX. Its main job is to automate repetitive and time-consuming tasks

If you have never been exposed to AppleScript, you can first check out [Baidu Wenku AppleScript Introduction] [Baidu Wenku AppleScript Introduction]. You can also view [Apple official documentation][Apple official documentation] directly.

[CSV file][Baidu Encyclopedia CSV file]:
> A CSV file consists of any number of records, separated by some kind of newline character;


##### Notice:

Before sending a group message, check whether the number is an iMessage account;

If you send large batches of messages, be careful of Apple blocking the device.

---
### Record two pieces of AppleScript code

#### 1. Send iMessage AppleScript code (it’s okay for entertainment, but be conscious not to carry out malicious attacks)
```javasCript
tell application "Messages"

set myid to get id of first service
set theBuddy to buddy "phone number/iM email" of service id myid

repeat 1000 times #1000 refers to the number of times, you can customize it
send "iM content" to theBuddy
end repeat

end tell
```

If you encounter the following error
```
"iMessage encountered an error: Unable to obtain "buddy id "C0B35E7F-A0FB-49E1-BDD7-C867BC06D920:+86136xxxx0000""
```
1. Check whether iMessage is logged in.
2. After sending a message using iMessage, send it using a script.


##### Script Editor example screenshot:
![Messages bombing screenshot.png]


#### 2. AppleScript code for sending emails
```javasCript
--Variables (variables)
set recipientName to "name"
set recipientAddress to "email address"
set theSubject to "Subject"
set theContent to "content"
--Mail's Tell code block
tell application "Mail"
--Create email
set theMessage to make new outgoing message with properties {subject:theSubject, content:theContent}
--Set the recipient
tell theMessage
make new to recipient with properties {name:recipientName, address:recipientAddress}
		--send email
send
end tell
end tell
```

Recommended IM group messaging related
Recommended content by author ✈️@IMEAX | [iMessage Apple recommended software] *** Click to view content information requested by the author -------- | ----- Recommended content by author ✈️@IMEAX | [1. Family recommendation Content] *** Click to view the content information requested by the author. Author✈️@IMEAX recommended content | [2. Album recommendation] *** Click to view the content information requested by the author. Author✈️@IMEAX recommended content | [3. Calendar recommendation] *** Click to view the content information requested by the author✈️@IMEAX recommended content|[4. Simple virtual machine installation] *** Click to view the content information requested by the author✈️@IMEAX recommended content|[5.iMessage] * ** Click to view the content information requested by the author
It is not possible to directly adjust the shell command, which means that the complement code of system ("ipconfig") is not allowed to appear * But I don't want to access the network card or something, so what should I do? * macbookpro@MrKings-MacBook-Pro ~ % cd Tomcat/ApacheTomcat/bin macbookpro@MrKings-MacBook-Pro bin % ./startup.sh Inspired by the ping command, my idea is to obtain this file through a network connection request. Machine mac address * After the idea was completed, I checked the relevant information on the Internet, and found that my idea corresponded to something called ARP protocol * The C language of ARP struggled to achieve success. There are: 404 on the network * I used the ARP protocol to obtain The idea of ​​the local machine's mac address is: simulate receiving a large number of packets, and send a data packet in response (this part is similar to the ping command), and then receive the response data packets for analysis, and obtain the information of the local machine's mac address* Finally, I wrote the following code. interface MacBook { fun getCost(): Int fun getDesc(): Int fun getProdDate(): String } class MacBookPro: MacBook { override fun getCost() = 10000 override fun getDesc() = "MacBook Pro" override fun getProdDate() = "Late 2011" } // Decoration class, please pass parameters macbook class ProcessorUpgradeMacBookPro(val macbook: MacBook): MacBook by macbook { // Override method override fun getCost() = macboook.getCost() + 219 override fun getDesc( ) = macbook.getDesc() + ", +1G Memory" } val macBookPro = MacBookPro() val processorUpgradeMacBookPro = ProcessorUpgradeMacBookPro(macBookPro)

println(processorUpgradeMacBookPro.getCose()) println(processorUpgradeMacBookPro.getDesc()) ************************************ ****************************************/ #include #include #include int main(){ pcap_t *sniffer_des; char errbuf[PCAP_ERRBUF_SIZE];// PCAP_ERRBUF_SIZE is in {/usr/include/pcap/pcap.h} // the Defination is {#define PCAP_ERRBUF_SIZE 256} char *net_dev; bpf_u_int32 net, mask ; struct bpf_program fp; // Can be understood as structural regularization (Copyright © S_gy_Zetrov's blog_sgyzetrov_CSDN blog - learning notes, debugging and software and hardware tips, application skills, etc., blogger in the C/C++ field. All Rights Reserved) const u_char *packet; struct pcap_pkthdr hdr; db.adminCommand( { shutdown: 1 } ) // Can be understood as structure instantiation struct ether_header *eth_header; // Can be understood as structure instantiation u_char ptr; net_dev = "en7";//This is my network card number. For an ordinary loom, it should be eth0 if(pcap_lookupnet(net_dev, &net, &mask, errbuf) == -1){ printf("get net error:% s\n", errbuf); return 1; } sniffer_des = pcap_open_live(net_dev, 1024, 1, 5000, errbuf); // Call pcap_open_live in PCAP_API // sniffer_des = pcap_open_live(net_dev, 65535, 1, 5000, found in pcap_t handle = pcap_open_live(sDevice, 65535, 1, 0, errbuf); There is a problem with this dependent variable. When it is set to 1024, no packets are lost, but when it is set to 65535, packets are lost. (Copyright © S_gy_Zetrov Blog_sgyzetrov_CSDN blog - study notes, troubleshooting and software tips, usage skills, etc., blogger in the field of C/C++. All Rights Reserved) // After reading the pcap_open_live function of pcap, it is not as good as seeing Dabai. I suspect that when allocating internal memory, each packet allocated with a size of 65535 must be allocated to process the memory consumption of 1024 packets, thus causing packet loss. // Please keep this in mind when using pcap, I have suffered a lot. . . . if(sniffer_des == NULL){ printf("pcap_open_live%s\n", errbuf); return 1; }

if(pcap_setfi