# [Apple IMessage Push Software] On the server side, you can save the device token and use it to send push notifications to specific devices

define IS_IPHONE (UI_USER_INTERFACE_IDIOM() == UIUserInterfaceIdiomPhone)

On MAC OS systems, Apple provides a script called Apple script to automatically implement tasks.

The Apple script code to implement iMessage group sending is as follows:

tell application "Messages"
set csvDatatoread "/Users/dengzhenhua/Desktop/send.txt"

set csvEntriestoparagraphsofcsvData

repeat with ifrom 1tocountcsvEntries

set phone to (csvEntries'sitemi)'stext
Retina1x (320*480) (before iphone3GS, no need to worry about it now)

Retina2x (640*960) (iphone4/4s)

Retina4 (640*1136) (iphone5/5s/5c)

Retina HD4.7 (750*1334) (iphone6/6s)
<link rel="stylesheet" media="(device-height: 480px) and (-webkit-min-device-pixel-ratio:2)" href="iphone4.css" />

<link rel="stylesheet" media="(device-height: 568px)and (-webkit-min-device-pixel-ratio:2)" href="iphone5.css" />

Using JS

 

//Determine whether it is iPhone 4 or iPhone 5 by height

isPhone4inches = (window.screen.height==480);

isPhone5inches = (window.screen.height==568);

Retina HD5.5 (1242*2208) (iphone6p/6sp)

<?xml version="1.0" encoding="UTF-8"?>

<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">

<plist version="1.0">

<dict>

<key>adjustmentBaseVersion</key>

<integer>0</integer>

<key>adjustmentData</key>

<data>

PY4xD4IwEIX/y5s7ADVqurnpookmOhiHwxapoZS0Bwvhv1vEuN19ee+7G+EMkyYmqBGO

IpuwN/ZVM9Qqk4X4sZvVXEPJrFgJ+GBNy8TWt1DrSaDywRFfTYhflAsMy3xoKz+Ly942

+ti70gQo5Nud3EgIUNf9S0h7fNbG0dkMdmGZQNcQz/oUsKcL0jHS7z6ySx9EqPtj+gA=

</data>

<key>adjustmentEditorBundleID</key>

Regular installation script for Apple computers (complete installation is recommended and can be installed in a few minutes):

/bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"

Apple computer extremely fast installation script (lite version, installation is completed in a few seconds):

 

/bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)" speed

Apple computer uninstall script:

 

/bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/HomebrewUninstall.sh)"

 

Linux computer installation script:

 

rm Homebrew.sh; wget https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh; bash Homebrew.sh

 

Linux computer uninstall script:
Whether you want to share photos with one friend or dozens of friends, set up a collaborative album where everyone can dump vacation photos, or even share your album with the whole world, iCloud Photo Sharing makes it easy to share your photos right from your iPhone or iPad.

Whether you want to share photos with one or dozens of friends, build a collaborative album where everyone can dump your vacation photos, or even share your album with the world, iCloud Photo Sharing makes it easy to share from your iPhone Photo or iPad.

Turn On iCloud Photo Sharing
First things first, you need to turn on iCloud Photo Sharing. The best thing about iCloud Photo Sharing, by the way, is that even if you don't regularly use iCloud for backing up all your photos and videos—because, perhaps, you followed our tutorial on banishing iCloud's constant nagging about storage upgrades and now use Google Photos—you can still enable photo sharing for the photos you want. The free iCloud storage is palatial in size if you're only using it for photo and video sharing and not a total backup.

First, you need to turn on iCloud photo sharing. By the way, the best thing about iCloud photo sharing is that even if you don't regularly use iCloud to back up all your photos and videos, it's probably because you followed our tutorial on eliminating the ongoing iCloud obsession with storage upgrades. Using Google Photos - You can still enable photo sharing for the photos you want. iCloud storage is huge in size if you only use it for photo and video sharing instead of full backup.

To check on the status of iCloud Photo Sharing open up the Settings app on your iOS device. Select “iCloud” from the main menu.

To check the status of iCloud photo sharing, open the Settings app on your iOS device. Select "iCloud" from the main menu.

rm HomebrewUninstall.sh; wget https://gitee.com/cunkai/HomebrewCN/raw/master/HomebrewUninstall.sh; bash HomebrewUninstall.sh
<string>com.apple.camera</string>

<key>adjustmentFormatIdentifier</key>

<string>com.apple.photo</string>

<key>adjustmentFormatVersion</key>

<string>1.4</string>

<key>adjustmentTimestamp</key>

<date>2020-10-25T10:29:06Z</date>

</dict>

</plist>
set myid to get idof firstservice

set theBuddy to buddyphoneof serviceidmyid

send "It will be sunny in Beijing today, with a temperature of 13 to 27 degrees; it will be sunny on Tuesday, with a temperature of 11 to 26 degrees, and a northerly wind of level 3-4; it will be sunny on Wednesday, with a temperature of 11 to 24 degrees, with a breeze <3 ---- Pinluo Internet www.pinluo .com"totheBuddy

delay 1

set FailNum to (getcountchat)

if FailNum > 100 then

repeat withjfrom 1 to FailNum



end tell
 
There are two methods for mass sending, one is through the iMessage client, and the other is through the AppleScript (Mac OS comes with it) script to control the iMessage client to send.

The second type is briefly described below:

First of all, make sure that the iMessage account sent must be valid, otherwise the error "buddy id "C0B35E7F-A0FB-49E1-BDD7-C867BC06D920:+86136xxxx0000"" will be reported.

Secondly, use EXCEL to save the account to be sent as a csv file, and then control the iMessage client to send via AppleScript. The content of the script is as follows:

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

Since sending iMessage is sent on the client, not in the background, when the amount of information is large, the iMessage client will run slowly or even be unable to be opened. You can clear the sent iMessage or log out of the account and log in again.

Introduction to the overall implementation idea
Many of them are fragments and can only be sent, but there is no overall project-level solution. But the following solutions can be achieved!
wx.getSystemInfo({

   success: function(res) {

     // Match according to mobile phone model

     if (res.model.search('iPhone X') != -1

     || res.model.search('iPhone Max') != -1

     || res.model.search('iPhone 11') != -1

     || res.model.search('iPhone 12') != -1) {

       console.log('is full screen')

     }