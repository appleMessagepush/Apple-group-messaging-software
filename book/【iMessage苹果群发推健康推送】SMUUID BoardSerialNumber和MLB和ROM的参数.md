# 【iMessage苹果群发推健康推送】SMUUID BoardSerialNumber和MLB和ROM的参数

如Mamshareinc，公司账户，允许多种斥地职员如Mamshareinc，公司账户合作开辟，设置装备摆设设备安排多于一些开发人员 推送证书（分为开发和颁布两种，范例别离为APNs Development ios,APNs Distribution ios）,该证书在appID配置中创建生成，和开发者证书同样，安置到开发电脑上；
为PP文件，该文件将appID,开发者证书，硬件Device绑定到一起，在开发者中间配置好后能够增加到Xcode上，也可以间接在Xcode上毗连开发者中心生成，真机调试时需要在PP文件中添加真机的udid；是真机调试和必架必备之珍品；

泛泛咱们的建造流程一般都是按以上序列举行，先操纵开发者帐号登岸开发者中心，创建开发者证书，appID,在appID中开明推送办事，在开通推送服务的选项上面创建推送证书（服务器端的推送证书见下文），以后在PP文件中绑定全部的证书id,添加调试真机等；
package zlicense.de.schlichtherle.utils;

圈存的key

考据tac的key

 该流程进行两次，分别创建开发测试用PP文件和发布PP文件，前者用于真机测试，后者用于提交发布；Ad Hoc格局一般用于企业帐号，此处我们疏忽；

筛选后提交

会主动检测立室appID,别的下拉项中还可以选择wildCard格式，该格式为自动生成，使用*通配符，合用于批量的，没有推送，PassCard等服务的应用；我们选择我们方才创建的appID,之后下一步选择证书；

创建发布证书解释查抄帖子证书，如图12所示，应用上述四个证书，2描写文件，证书文件下载描述文件 可以生成p12文件。 下载图中的图形。 四个证书，下载证书，双击进入应用程序“keychain”是导出的开发证书，三个证书的导出操纵与下面的入口类似，没有屏幕截图描述。




13.只需使用第一个开发测试开发证书和开发证书描述文档（不需要推送证书），但请记取在开发工具上选择Pushnotification函数。



14.发布后，您只需使用证书并发布证书描述文件（无需发布）。



15若是使用第三方邮件推送服务，您通常需要上传PEM类型文件。





此文件需要使用“开发推送证书”和“推送推送送货书”。操作以下：a，开发开发促销P12文件的推行证书，发布了P12文件 证书，可以直接放在桌面上。B.掀开应用程序“终端”，输入CDDESKTOP，运转指令：


8编纂按钮将显现，以下所示：单击“编辑”输入以下图片：如果您在拜托证书（开发，发行版）中创建了以下图片 举措，你 将与上图雷同，尔后你会回去。 单击1,2两个按钮。

10.创建开发证书说明文件挑选您的应用程序，过细弊端：

11。创建公布证书表明检查帖子证书，如图12所示，应用上述四个证书，2描述文件，证书文件下载描述文件 可以或许天生p12文件。 下载图中的图形。 四个证书，下载证书，双击进入应用程序“keychain”是导出的开发证书，三个证书的导出把持与下面的进口相同，没有屏幕截图描述。

import java.util.Locale;

 

public class CardCenter

{

    public static void main(String[] args)

    {

 

        // 圈存的key

        String loadKey = "3F013F013F013F013F013F013F013F01";

        System.out.println("圈存的key:" + loadKey);

        // 考证tac的key

        String tacKey = "34343434343434343434343434343434";

        System.out.println("考证tac的key:" + tacKey);

 

        System.out.println();

 

        // posid

        String posid = "112233445566";

        System.out.println("终端ID:" + posid);

        // 买卖金额

        String tradeAmount = "00000001";

        System.out.println("交易金额:" + tradeAmount);

        // 交易金额十进制

        int ta = 1;

        // 交易典范

        String tradeType = "02";

        System.out.println("交易类型:" + tradeType);

 

        System.out.println();

        // 预充值指令

        System.out.println("组装预充值指令:805000020b0100000001112233445566");

        // 预损耗指令805000020b0100000001112233445566的指令回复

        String preTopup = "0000001a0017000106b825d7684c81ce9000";

        System.out.println("得到预充值响应:" + preTopup);

        byte[] recvByte = ByteUtil.hexStr2Byte(preTopup);

 

        // 卡余额

        String balance = ByteUtil.hexToStr(recvByte, 0, 4);

        int bal = ByteUtil.hexToInt(recvByte, 0, 4);

        System.out.println("卡余额:" + balance);

 

        // 联机计数器

        String cardCnt = ByteUtil.hexToStr(recvByte, 4, 2);

        System.out.println("联机计数器:" + cardCnt);

 

        // 密钥版本

        String keyVersion = ByteUtil.hexToStr(recvByte, 6, 1);

        System.out.println("密钥版本:" + keyVersion);

 

        // 算法标识

        String alglndMark = ByteUtil.hexToStr(recvByte, 7, 1);

        System.out.println("算法标识:" + alglndMark);

颠末测试，我发明前段时间苹果网站下线时代更新了证书生成机制。曩昔，利用钥匙串生成一个CSR文件，可以不停用。可是，如今每当你要生成证书，做generate的时辰都需要提早从新生成一个CSR文件，不然你生成的证书都是无效的，假证书，特别是PUSH的，服务端使用这类证书根本无法和APNS建立连接，这种诡异的问题超难跟踪的！但愿看到这段话的人都能防止走弯路，不用谢了！

在用PushMeBaby中也碰到各类问题。首先，固然工程中曾经使用了.cer的公钥证书，但是当地钥匙串中必需有带私钥的证书，否则连接无法乐成建立。并且需要细致的是，证书最佳放在“登录”分组中，否则程序也是找不到私钥的。其次，原始的工程中在scanString的时候会死循环

    }

}
13.只需使用第一个开发测试开发证书和开发证书描述文档（不需要推送证书），但请记着在开发工具上选择Pushnotification函数。

14.发布后，您只需使用证书并发布证书描述文件（无需发布）。

15如果使用第三方邮件推送处事，您凡是需要上传PEM类型文件。


此文件需要使用“开发推送证书”和“推送推送送货书”。操作如下：a，开发开发促销P12文件的推广证书，发布了P12文件 证书，可以直接放在桌面上。B.翻开应用程序“终端”，输入CDDESKTOP，运行指令：


OpenSSLPKCS12-CLCERTS-NOKEY-OUT将生成证书文件。PEM-I开发证书或发布推送证书 文件.p12，输入输入总线后输入暗码（当导出输入P12文件时输入的密码），当输入输入密码时，表示输入，输入完成后，输入汽车。