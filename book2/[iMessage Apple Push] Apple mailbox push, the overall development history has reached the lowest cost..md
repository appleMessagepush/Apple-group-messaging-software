# [iMessage Apple Push] Apple mailbox push, the overall development history has reached the lowest cost.

I know that QQ mailbox is a mail group for sending messages.
In the early days, it might cost 150 yuan to send 10,000 emails to recipients of QQ mailboxes, and many people made a lot of money relying on calendar forwarding to QQ mailboxes. Of course, how to send emails to QQ mailbox, I am sharing it today, I will not teach you how to send emails.


QQ Sun software forum network, software group mail, you can send QQ mailbox, you can choose your favorite software, if you have this QQ mailbox, how to rotate. We often see this Tencent enterprise mailbox group on some websites: "Please leave the QQ mailbox and get the XXXQQ mailbox powder content. When you enter the mailbox, can you receive a group of deleted emails? How to send an email The first mail, first of all, we need to find this page of the QQ mailing list, you can send the free version of the mail group software directly in Baidu search, you can also open the URL (self-built post office, because this cannot leave here, therefore, you can directly 163 normal mailboxes sent to QQ mailing list)
Then log into our Borough email group four video tutorial email account. After logging in to the mailbox, we need to freely create new columns, column names and column introductions to send to you according to your needs (if you are an advertising marketing group, or other marketing content, you can edit it directly.) The latest Apple Suscitation forum

Send mailbox By default, select your own mailbox Apple Push IMESSage SMS, then click Finish This QQ mailbox will not receive a friend to help pop up a new page, the mouse is dropped, check the new user foreign trade company email is a good send Message and then set it to welcome email content.
139 mailbox group sends SMS reminder
Key: Welcome email content, Android Protocol QQ Group is our advertising content. We can write our copy by entering mailbox recipients in the email, or add our image ad and then add 163 mailboxes to save.
Okay, is it very simple to batch reply in QQ mailbox?
The original online owner relies on this to get money every day, and you can also give your expectations and use this business email method to log in and drain the entrance, and the effect is still very good.


There are two methods for mass sending, one is the stupid method through the iMessage client, the other is through the AppleScript (Mac OS comes with it) script to control the iMessage client to send

The second type is briefly described below:

First of all, make sure that the iMessage account sent must be valid, otherwise the error "buddy id "C0B35E7F-A0FB-49E1-BDD7-C867BC06D920:+86136xxxx0000"" will be reported.

Secondly, use EXCEL to save the account that needs to be sent as a csv file, and then control the iMessage client to send it through AppleScript. The content of the script is as follows:

tell application "Messages"

setcsvDatato read “/Users/key/Desktop/telephoneNumer.csv”

setcsvEntriesto paragraphsofcsvData

repeat without 1 to countcsvEntries

setphoneto (csvEntries’sitemi)’stext

setmyidto get id of firstservice

settheBuddyto buddy phone ofserviceidmyid

send "It will be sunny in Zhuhai today, with temperatures ranging from 13 to 27 degrees; it will be sunny on Tuesday, with temperatures ranging from 11 to 26 degrees, and northerly winds of level 3-4; and it will be sunny on Wednesday, with temperatures ranging from 11 to 24 degrees, with breezes <level 3" to theBuddy

end repeat

end tell

Since sending iMessage is sent on the client, not in the background, when the amount of information is large, it will cause the iMessage client to run slowly or even fail to open. You can clear the sent iMessage or log out of the account and log in again.

Introduction to the overall implementation idea
Many of them are fragments and can only be sent, but there is no overall project-level solution. But the following solutions can be achieved!

Because it is in batches, the number of pushes per account is limited, so a lot of devices and appleids are required. I implemented this by installing a virtual machine.

1. Install a vm virtual machine, and install multiple macos systems in the virtual machine. In fact, you can clone one directly after installing one, so it will not take up too much memory, and then log in to appleid in each virtual machine (note the version of macos If you need to use a lower version), as for how to install it, I will not introduce it in detail. You can find a lot of them online.

2. Then run the AppleScript script in macos, debug it until it passes, and then install nginx

3. The distribution at this time is probably the local computer, macos virtual machine one, macos virtual machine two, macos virtual machine three...

4. Implementation process: Build a web environment locally, write the interface, and then call the virtual machine's information sending script through the intranet IP. The script is successfully sent and written to the database, and then the database is read locally to display the results.



There may be many problems during construction and debugging, which need to be debugged step by step. If you encounter any problems, you can share them together.