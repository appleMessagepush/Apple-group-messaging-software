# 【苹果群发】轻松实现iMessage群发技术开源需求


群发有两个方法，一个是笨方法通过iMessage客户端，另一个是通过AppleScript（Mac OS自带）脚本控制iMessage客户端发送

下面简述下第二种：

首先，要确定发送的iMessage账号必须有效，否则会报错“buddy id “C0B35E7F-A0FB-49E1-BDD7-C867BC06D920:+86136xxxx0000””。

其次，用EXCEL把需要发送的账号保存为一个csv文件，然后通过AppleScript控制iMessage客户端发送，脚本本内容如下：

tell application “Messages”

setcsvDatato read “/Users/key/Desktop/telephoneNumer.csv”

setcsvEntriesto paragraphsofcsvData

repeat withifrom 1 to countcsvEntries

setphoneto (csvEntries’sitemi)'stext

setmyidto get id of firstservice

settheBuddyto buddy phone ofserviceidmyid

send "今天珠海晴，气温13到27度；周二晴，气温11到26度，北风3-4级；周三晴，气温11到24度，微风<3级"totheBuddy

end repeat

end tell

由于发送iMessage是在客户端发送的，不是在后台，所以信息量很大时，会导致iMessage客户端运行缓慢，甚至无法开启，可以通过清空已发送的iMessage或注销账号重新登陆

总体实现思路介绍
很多都是片段，只能实现发送，但是没有整体的项目级解决方案。但是以下方案可以实现！

因为是批量，每个账户的推送数量是有限制的，所以需要很多的设备和appleid，我通过安装虚拟机的形式实现

1.安装vm虚拟机，并且在虚拟机中安装多个macos系统，其实安装好一个其他可以直接克隆，这样就不会占用太多内存，然后在每个虚拟机中登录appleid(注意macos的版本要使用低版本的)，至于怎么去安装，就不再详细介绍了，网上一抓一大把。

2.然后在macos中运行AppleScript脚本，调试到通过，然后安装nginx

3.这时候的分布大概就是 本地电脑 ，macos虚拟机一，macos虚拟机二，macos虚拟机三 …

4.实现流程 本地搭建web环境，编写界面，然后 通过内网ip调用虚拟机的发送信息脚本，脚本发送成功写入数据库，然后本地读取数据库展示结果



可能在搭建和调试中会有很多问题，需要一步一步去调试，其中遇到的问题大家可以一起交流

