# 【苹果推群发iMessage推真机脚本】

一、打包ipa和天生.plist文件细致步伐：
1、在苹果开发者布景生成签名文件，把持developer profile大要adhoc distribution profile这边过细不克不及利用distribution profile，因为这不是颁布到Appstore。
2、生成archive，点击菜单栏product中的archive选项举办打包
3、在organizer中点击archive举行distribute，公布的过程中细致筛选save for enterprise distribution，不然会败北，完成保存会生成俩文件 .ipa文件和 .plist文件。其中.ipa文件即是应用程序文件， .plist文件是苹果需要经过进程itms-services协议访谒的文件。

下面是.plist文件的款式


if (NSFoundationVersionNumber >= NSFoundationVersionNumber_iOS_7_0) {
    // >= iOS 7.0
} else {
    // < iOS 7.0
}

大概：

if (kCFCoreFoundationVersionNumber >= kCFCoreFoundationVersionNumber_iOS_7_0) {
    // >= iOS 7.0
} else {
    // < iOS 7.0 在顶部，单击要操纵imessage登录的地址。 在MessageAccount弹出风口中，单击签名。 在“动静”流行音乐窗口中，单击“退伙”。 若是它看上去很好，请延续并列复最后几个步调登录任何装备上的iMessage。 如果看起来很好，请继承并重复下属的末了几个步骤登录其余设备上的iMessage。 掀开举措设置装备摆设干扰以查察可以或许大概检察消息成果。 减少操纵设置以剥夺UNN EFESSARY卡通 - 例如，在您的主屏幕上。 部门人翻开它，

返回被开方数; 凝听应用程序中的叫醒应用程序：法子，在GeturlParameterWithurl，启用链接中的通用链接，WSNotification是一种报告方法经由过程您本身的数据包，输导传递参数反应 - Deficien，您能够心想事成您的baiduIOS当地和反响 - 原生 雷同。



（nsurl *）URL {nsmutabledictical * parm = [[nsmutablecticearyalloc] init]; // URL创建了URL零件类nsurlcomponents * urlcomponents = [[nsurlcomponentsalloc] initwithtring：url.absolutring]; //除百科辞典URLComponents的统统参数的递归补充。 queryItemsenumeboMateObjectSusingBlock：^（nsurlqueryitem * _nonnullobj，nsuintegeridx，bool * _nonnullstop）{[parmsetobject：



obj.valueforkey：Orville's Ideas and Interests];}]; 返回参数; 应用程序：应用程序唤醒事件侦听器进程，通常分析GeturlParameterWithurl链接方法的参数，WSNotification是通过传输参数来通报反应生就生物体的关照方法，这可以实现其baiduIOS本地和反应本机通信。 （nsurl *）URL {nsmutabledictical * parm = [[nsmutablecticearyalloc] init]; // URL建立了URL组件类nsurlcomponents * urlcomponents = [[nsurlcomponentsalloc] initwithtring：url.absolutring]; //除字典URLComponents的全部参数的递归

    fun getCost(): Int

    fun getDesc(): String

    fun getProdDate():String

}

class MacBookPro: MacBook{

    override fun getCost(): Int  = 10000

    override fun getDesc(): String = "Mackbook Pro"

    override fun getProdDate(): String  = "Late 2011"

}

class ProcessorUpgradeMacbookPro(val macbook:MacBook): MacBook by macbook{

    override fun getCost(): Int  = macbook.getCost() + 777

    override fun getDesc(): String = macbook.getDesc().plus("  ,1G内存储器")

    override fun getProdDate(): String  = macbook.getProdDate()

}

fun main(args:Array<String>) {

   val macBookPro = MacBookPro()

    val processorUpgradeMacbookPro = ProcessorUpgradeMacbookPro(macBookPro)

    println(processorUpgradeMacbookPro.getCost())

    println(processorUpgradeMacbookPro.getDesc())

    println(processorUpgradeMacbookPro.getProdDate())

    //    入口

//    10777

//    Mackbook Pro  ,1G内存

//    Late 2011

}

// 子视图 @property BOOL arrangesAllSubviews konsy@Konsy-MacBook-Pro ~ % mysql -uroot -p -h 127.0.0.1 Enter password: Welcome to the MySQL monitor. Commands end with ; or \g. Your MySQL connection id is 40 Server version: 8.0.27 MySQL Community Server - GPL Copyright (c) 2000, 2021, Oracle and/or its affiliates. Oracle is a registered trademark of Oracle Corporation and/or its affiliates. Other names may be trademarks of their respective owners. Type 'help;' or '\h' for help. Type '\c' to clear the current input statement. mysql> API_AVAILABLE(macos(10.11)); // 是不是将实足子视图摆列为拆分窗格 @property (readonly, copy) NSArray<__kindof NSView *> *arrangedSubviews API_AVAILABLE(macos(10.11)); // 拆分视图去处拆分暗门罗列的视图数组 - (void)addArrangedSubview:(NSView *)view API_AVAILABLE(macos(10.11));//



二、如今万事俱备只欠东风啦，只需要客户端能够告成拜候到咱们生成的.plist文件便可。
本来感受和ipa文件一样，放在服务器上是，访问一下就OK啦，功效发明，最新版本是不成的，曩昔切当可以通过http的方法进行访问plist文件进行安置，不过现在苹果规定必须以https的方法进行访问。

以https方式访问plist文件的解决方案

1、设置装备安排tomat支撑https方式访问
2、利用dropbox分享外链进行访问原始文件
3、利用开源中国的git&osc分享外链进行访问原始文件

说说三种方式，第一种方式：对于只使用http方式访问来配置的tomcat，自己来改配置代价高，而且没必要。
第二种方式：dropbox是国外的，并且是要翻墙的，也便是存在不稳定情况，不通用。
第三种方式：国内网站，大略，不乱


 
由于那些典范的动画正值扰乱它们，其他动画是为着或帮手迟误电池组寿数。 如果您真真实实使用操纵设置的削减，它会滋扰消息结果，若果必定哪一番对您更重要。 有些人还报告说它可以“减少行动”设置会影响它们以查看消息效果。 如果你有“动作”并且你会干扰你，你可以用它对你来说更紧张。 即使您打开“减少勾当”，标题和消息效果也可以事变。 但这很等闲检查。 如果退出并登录IMESSAGE，您能够会有效。 即便是“减少活动”，很多人也决不会碰到问题，消息效果也很好。 但很轻易查抄。 您的设置，单击“老例”。 在“公共”屏幕中的“设置”应用程序中，单击“可拜候性”。 在“可访问性”屏幕上，单击“可访问性”。 如果它是着花的，请单击“减少智育”。 在帮忙服从设置屏幕上，