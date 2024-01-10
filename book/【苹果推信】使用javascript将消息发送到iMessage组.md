# 【苹果推信】使用javascript将消息发送到iMessage组

实现大型iMessage的iMessage推广技术主要需要克服两个技术问题，一个是获得iMessage帐户，另一个是大型iMessage。

# 推荐内容IMESSGAE相关

作者✈️@IMEAE推荐内容     |[***iMessage苹果推软件***] *** 点击即可查看作者要求内容信息
-------- | -----
作者✈️@IMEAE推荐内容     |[***1.家庭推内容***] *** 点击即可查看作者要求内容信息
作者✈️@IMEAE推荐内容     |[***2.相册推***]*** 点击即可查看作者要求内容信息
作者✈️@IMEAE推荐内容     |[***3.日历推***] *** 点击即可查看作者要求内容信息
作者✈️@IMEAE推荐内容     |[***4.虚拟机安装简单***] *** 点击即可查看作者要求内容信息
作者✈️@IMEAE推荐内容     |[***5.iMessage***] *** 点击即可查看作者要求内容信息

 获取iMessage帐户的当前方法是扫描手机号码。 扫描手机号码可以通过代码自动扫描或手动过滤。 我还没有找到通过自动代码扫描的好方法。 我建议您从以下两个方面开始：


1.编写AppleScript脚本来控制MacOS附带的iMessage客户端进行验证，类似于组iMessage。 发送iMessage后，如果捕获到发送失败的异常，则它不是iMessage帐户。 


2.在iOS系统的Messageframework中研究私有api。 通过专用API进行验证需要通过MacOS随附的iMessage客户端进行手动过滤或验证。 该方法是编写一个程序，以将要验证的数字输出到文件中，并以逗号分隔。 然后，将数字粘贴到文件中，然后将其粘贴到iMessage客户端的地址栏中。 iMessage客户端将自动检查该号码是否是iMessage帐户。 检查速度取决于互联网速度。 其中，红色表示不是iMessage帐户，蓝色表示iMessage帐户和未选择的帐户。 在第一部分中，第一步当然是介绍Apple的Push机制（APNS）

继承，这里有一个区分，由于PP文件的开辟测试版必要真机调试，以是咱们需要绑定真机，这里因为以前我增加过一些装备，所以这里就能够间接全选添加，若是没有的话，需要将真机的udid复制出来在此添加，在公布PP文件中，是没有这一步的；



终端ID:112233445566
(void) application:(UIApplication *)application didReceiveRemoteNotification:(NSDictionary *)userInfo 
{
    if ( application.applicationState == UIApplicationStateActive ) {
        // 步伐在运行进程中遭到推送关照
        NSLog("%@", [[userInfo objectForKey: @"aps"] objectForKey: @"alert"]);
    } else {
        //程序为在运行状况受到推送通知
    }
}
上面这段代码处置了利用别离在运行和非active状态下接管推送通知的处理方式。
3：下载php样例程序，将此中的devicetoken字段设为适才保留的token，细致，去掉空格。
将password设为123456abc，将message设为你想设置装备摆设的内容，保存，而后号令行下进入php源码途径，运行php simplepush.php
如果品德够好，你的设备下马上会咚咚的响一下~三：其余注意事项
1：可以利用如下代码果断开启了那些范例的动静通知：
UIRemoteNotificationType enabledTypes = [[UIApplication sharedApplication] enabledRemoteNotificationTypes];
if (enabledTypes & UIRemoteNotificationTypeBadge) {
//开启badge number
}
if (enabledTypes & UIRemoteNotificationTypeSound) {
//开启声音
}
if (enabledTypes & UIRemoteNotificationTypeAlert) {
//开启alert

标准的mac1数据:684C81CE

mac1校验告成！

应用将受到的token发送到办事端，也便是APNS消息的泉源。4：应用服务器经由过程token及证书向苹果的消息服务器发送消息。
5：苹果将接收到的消息发送到对应设备上的对应应用。
6：如果应用未处于Active状态（未启动或backgroud），默认设置下，屏幕顶部会弹出消息框，同时有声音提醒，点击改消息框会进入应用，如不点击则应用图标上会有badge number呈现。
二：使用步调
APNS的使用并不复杂，但轻易犯错的关键比力多，分外是证书申请的部门，要特别的注意。
下面按照我按教程实际操作的步骤举行论述：
筹备事情：
A: 一个Xcode工程，我们将其定名为MyPushChat，以及一个对应的App ID.
B:一台能用于调试的iOS设备（APNS只能在实体设备上工作，模拟器没法运行）
step1:
在"应用程序-使用东西"中翻开"钥匙串拜候"（Keychain Access），如下图所示：
在接下来的对话框中筛选存储到磁盘，邮件可随意填写，称号命名为MyPushChat
点击“继续”，将文件名设为"MyPushChat"，点击存储。如许，会得到一个名为"MyPushChat.certSigningRequest"的文件，此文件要妥帖保管。
从方才建立的csr文件中处处私钥，详细操作如下图所示：
将导出的文件命名为MyPushChatKey.p12，并输入暗码，请服膺此密码，这里临时设为123456abc。
此时，我们已有文件MyPushChat.certSigningRequest，以及MyPushChatKey.p12
step2:
在App IDs中找到与MyPushChat对应的AppID, 点击右边"Configure"按钮，勾选下图所示选择框：
点击”Development Push SSL Certificate“右侧的configure按钮，development版本的应用于测试，有效期只要一年，且只能使用苹果的APNS测试服务器，应用发布时需要申请Distributions版本的证书。Development与Distribution版本的证书获得的Token是不同样的。弹出框如下所示：上传"MyPushChat.certSigningRequest"并点击Generate，半晌后证书天生终了，下载，命名为“aps_developer_identity.cer”。
step3:
打开Provision Portal，点击New Provision，将Provision File命名为"MyPushChat"，选择对应的App ID 以及Device并下载。得到文件MyPushChat.provision。双击导入此MyPushChat.Provision文件，如果一切正常，会弹出Orgnizer, 且表现界面如下所示：
step4:
将上面得到的文件都保存到桌面。打开Console,切换到桌面。
起首将aps_developer_identity.cer转换成MyPushChat.cert
命令：openssl x509 -in aps_developer_identity.cer -inform der-out MyPushChatCert.pem
然后将私钥文件转换为MyPushChatKey.pem
命令：
openssl pkcs12 -nocerts -out MyPushChatKey.pem -in MyPushChatKey.p12
Enter Import Password:
此处密码输入为后面为私钥设置的密码: 123456abc

MAC verified OK

Enter PEM pass phrase:

这里必定要输入新密码,我们设为123456abc

Verifying - Enter PEM pass phrase:

        }

 

        Enumeration<InetAddress> inetAddresses = netint.getInetAddresses();

        for (InetAddress inetAddress : Collections.list(inetAddresses)) {

            out.printf("InetAddress: %s\n", inetAddress);

            System.out

                    .println("InetAddress ip=" + inetAddress.getHostAddress());

        }

        out.printf("\n");

    }

 # 推荐内容IMESSGAE相关

作者✈️@IMEAE推荐内容     |[***iMessage苹果推软件***] *** 点击即可查看作者要求内容信息
-------- | -----
作者✈️@IMEAE推荐内容     |[***1.家庭推内容***] *** 点击即可查看作者要求内容信息
作者✈️@IMEAE推荐内容     |[***2.相册推***]*** 点击即可查看作者要求内容信息
作者✈️@IMEAE推荐内容     |[***3.日历推***] *** 点击即可查看作者要求内容信息
作者✈️@IMEAE推荐内容     |[***4.虚拟机安装简单***] *** 点击即可查看作者要求内容信息
作者✈️@IMEAE推荐内容     |[***5.iMessage***] *** 点击即可查看作者要求内容信息

    public static boolean validateMacAddress(String macAddress)

            throws SocketException {

        boolean returnFlag = false;

        Enumeration<NetworkInterface> nets = NetworkInterface

                .getNetworkInterfaces();

        for (NetworkInterface netint : Collections.list(nets)) {

            byte[] mac = netint.getHardwareAddress();

            StringBuilder sb = new StringBuilder();

            if (mac != null) {

                for (int i = 0; i < mac.length; i++) {

                    sb.append(String.format("%02X%s", mac[i],

                            (i < mac.length - 1) ? "-" : ""));

                }

                System.out.println("mac=" + sb.toString());

            }

            if (sb.toString().equals(macAddress)) {

                returnFlag = true;

            }

        }

        return returnFlag;

 

    }

 

    public static boolean validatoIpAndMacAddress(String ipAddress,

            String macAddress) throws SocketException {

        boolean returnFlag = false;

        Enumeration<NetworkInterface> nets = NetworkInterface

                .getNetworkInterfaces();

        for (NetworkInterface netint : Collections.list(nets)) {

            byte[] mac = netint.getHardwareAddress();

            StringBuilder sb = new StringBuilder();

            if (mac != null) {

                for (int i = 0; i < mac.length; i++) {

                    sb.append(String.format("%02X%s", mac[i],

                            (i < mac.length - 1) ? "-" : ""));

                }

                System.out.println("mac=" + sb.toString());

            }

            if (sb.toString().equals(macAddress)) {

                Enumeration<InetAddress> inetAddresses = netint

                        .getInetAddresses();

                String ip = "";

                for (InetAddress inetAddress : Collections.list(inetAddresses)) {

                    ip = inetAddress.getHostAddress();

                    System.out.println("InetAddress ip="

                            + inetAddress.getHostAddress());

                    if (ipAddress.toString().equals(ip)) {

                        returnFlag = true;

                    }

                }

            }

        }

        return returnFlag;

 

    }

}

DevelopAppDevelopment（1 年份）：用于开发和真正的板滞调试应用程序。 Pushdevelopment（1年）：用于调试ApplePushNotification2，ProductAdhoc：用于颁布ADHOC应用程序。 appstore：用于发布提交的appstore的应用程序。 推力（1年）：用于在发布版本中操纵ApplePushNotification 1.2，AppidAppid，它理当是等同的或结婚Xcode中的BundleId。


ProvisioningProfile供应下面的所有文件：证书，AppID和设备。 要在真机上打包或运转应用程序，您需要证书标识表记标帜以识别此申请是合法的，安全的，完成; 尔后，您需要指示其AppID，并考证BundleId是不是是同等; 一样，如果需要确认设备是否可以运行程序，则是真正的呆板调试。 ProvisioningProfile包装在一起，以便在调试和发布过程中使用它，只有在不同的情况下挑选不同的配置文件文件。 在包装中，ProvisionProfile文件将被嵌入.IPA。 例如，以下所示，开发的ProvisioningProfile包含与AppID，可用证书和设备对应的新成果。 这条本事使用此供给服务包必须具有相应的证书，并将应用程序运行到应用程序中包含的设备。 如上所述，在设备上运行的过程如下：如证书，ProvisioningProfile还分为开发和分发。#include <stdio.h>

#include <stdlib.h>

#include <unistd.h>

#include <string.h>

 

int main(void)

{

    char mac[] = "00:0C:29:54:E2:F4";

    unsigned mac_calc[6] = {0};

    int count;

    for(; ; )

    {

        count = sscanf(mac, "%x:%x:%x:%x:%x:%x", 

                &mac_calc[5], &mac_calc[4], &mac_calc[3], &mac_calc[2], &mac_calc[1], &mac_calc[0]);

        if(count != 6)

        {

            printf("count = %d\n", count);

            printf("read mac error\n");

            return -1;

        }

        /*1.低位自增 2.高位取其进位 3.低位将进位位置0*/

        mac_calc[0]++;

        mac_calc[1] += ((mac_calc[0] & (0x100))  >> 8);

        mac_calc[0] = mac_calc[0] & (0xff);

 将password设为123456abc，将message设为你想设置的内容，保存，然后命令行下进入php源码路径，运行php simplepush.php
如果人品够好，你的设备上马上会咚咚的响一下~三：其他注意事项
1：可以使用如下代码判断开启了那些类型的消息通知：
UIRemoteNotificationType enabledTypes = [[UIApplication sharedApplication] enabledRemoteNotificationTypes];
if (enabledTypes & UIRemoteNotificationTypeBadge) {
//开启badge number
}
if (enabledTypes & UIRemoteNotificationTypeSound) {
//开启声音
}
if (enabledTypes & UIRemoteNotificationTypeAlert) {
//开启alert
}
2: 推送服务端保举使用Javapns, 使用很简洁，注意其使用的证书文件不是pem，而是p12格局，具体生成法子为：
一：生成csr文件（同上）
二：通过csr在苹果网站上生成cert文件(同上)
三：双击导入生成的cert文件，在keychain中同时选中csr的公用秘钥及刚刚导入的ssl证书，右键->导出, 保存为p12
其他过程雷同
3: 如果有把握，可以直接使用distribution版的证书和provision文件，但线上服务器有一定的限定，如果使用不当，会被苹果当ddos ban掉。
}


ps：实际上，每个教程都有它），让我们首先看一下苹果官方对其推送的解释的摘要图。 提供程序是将推送消息发送到您的移动应用程序的服务器。 它是Apple的消息推送服务器。 当您的本地服务器需要向应用程序发送消息时，它首先将消息发送到ApplePush服务器，然后ApplePush服务器将消息发送到安装了该应用程序的手机。 


接下来，让我们看一下描述图：我将根据上图的逻辑向您解释：1.您的IOS应用程序需要注册APNS消息推送功能。 2.当AppleAPNS推送服务器从您的应用程序收到注册消息时，它将返回一串devicetoken（非常重要）。 3.将应用程序收到的deviceToken发送到本地Push服务器。 4.当您需要为应用程序推送消息时，本地推送服务器将打包消息和DeviceToken并将其发送到Apple的APNS服务器。 5. APNS会将消息推送到目标iphone
