# 【苹果相册推】增加家庭协议sendmail postfix MDA指示其AppID

Apple Push Notification service）是苹果供应的推送处事，它允许斥地者将推送动静发送到 iOS 设备上。

例如，一组值为：1E58914B-6EE-50E8-9392（←该数值一样泛泛）我的NIC MAC是：A1：B2：C3：D4：E5：F6，所以这个SMUUID是：1E58914B-6EEA- 此后50E8 -9392 -A1B2C3D4E5F6将SMUUID粘贴到对应于三叶草的位置：查察NIC MAC地点：翻开终端输入IFConfig输入以下图片，以太网的内插器是您的MAC地址格局（A1：B2：C3：D4：E5：F6） ：BoardSerialNumberboardSerialNumber是由设备序列号+任何5个字母或由Clover天生的数字生成的一组参数。 比方，您的Clover生成序列号是C02J8YTODNCT，例如您的第五个字母：ABCDE，那么这个BoardSerialNumber是：C02J8YTodnctabcde填写如下图像，为JSON款式建立文件，苹果将在咱们请求此文件时下载独霸步调应用程序 。

JDK1.5新特征
1.法子的可变参数：数组
    public static int add(int ... arr) {
        int length = arr.length;
        int sum = 0;
        for(int i =0; i < length; i++) {
             sum = sum + arr[i];
        }
        return sum;
    }
在办法中用 … 表示可变参数

可变参数必须放在法子参数的末端一个并且有且只要一个 ；

2.for-eanch语句（再也不详解）
3.动态导入（import）（了解）
import static 导入一个类的全数静态域（法子与属性），
把持导入类的静态域就像是在本类中界说的同样；
操纵静态导入后挪用阿谁包中的方法可不加类名间接调用；

细致：不举荐利用静态导入；

4.泛型（典型守门员）
界说：类或方法在界说时典范不愿定。利用时才一定典范。

alt+insert快速导入（例如getter（）、setter（））

ClassCastException（RuntimeException）：在强转时，两个毫无关连的类产生的很是。

安全隐患：存在于强转，泛型可以或许大要大概防备向下转型的安全隐患；

4.1泛型：在界说时范例不愿定，只有在过细使用时本领肯定类型。
4.2泛型类
class MyClass<T，E> {  //泛型类能够担任多个类型
    private T t;
    private E e;
}

黑色苹果经常显现FaceTime和Imessage，无法一样平常登录。 必要一样平常登录，你需要提到3码，一些帖子甚至复制在真正的赤色苹果机上方。 但实际上，我希望上述办事将一样平常使用，我们需要补充SMUUID，BoardSerialNumber和MLB和ROM的参数。
尔后，您可以在浏览器中输入域名/ Apple-App-site接洽干系或域名/墨水核仪器Known / Apple-App-Site-Ksociation下载。 经过过程配置装备安排装备安排装备放置精巧的链接来调用应用程序，从新下载和安顿应用程序（在Xcode中设置装备摆设的域名），在Safari中输入通例链接，掀开应用程序，如果需要此值或在应用程序中翻开程例如，NIC MAC是：A1-B2-C3-D4-E5-F6，尔后ROM是：A1B2C3D4E5F6MLB，您的BoardSerialNumber。 在BoardSerialNumber中粘贴价格。 




(void)removeAllNotification { if (@available(iOS 10.0, *)) { UNUserNotificationCenter *center = [UNUserNotificationCenter currentNotificationCenter]; [center removeAllPendingNotificationRequests]; }else { [[UIApplication sharedApplication] cancelAllLocalNotifications]; } } 检查受权情况 - (void)checkUserNotificationEnable { // 断定用户是不是是是容许接收看护 if (@available(iOS 10.0, *)) { __block BOOL isOn = NO; UNUserNotificationCenter *center = [UNUserNotificationCenter currentNotificationCenter]; [center getNotificationSettingsWithCompletionHandler:^(UNNotificationSettings * _Nonnull settings) { if (settings.notificationCenterSetting == UNNotificationSettingEnabled) { isOn = YES; NSLog(@"翻开了关照"); }else { isOn = NO; NSLog(@"封锁了关照");




 [self showAlertView]; } }]; }else { if ([[UIApplication sharedApplication] currentUserNotificationSettings].types == UIUserNotificationTypeNone){ NSLog(@"封闭了通知"); [self showAlertView]; }else { NSLog(@"打开了通知"); } } } - (void)showAlertView { UIAlertController *alert = [UIAlertController alertControllerWithTitle:@"通知" message:@"未得到通知权位，请前去设立" preferredStyle:UIAlertControllerStyleAlert]; [alert addAction:[UIAlertAction actionWithTitle:@"撤除" style:UIAlertActionStyleCancel handler:nil]]; [alert addAction:[UIAlertAction actionWithTitle:@"配置" style:UIAlertActionStyleDefault handler:^(UIAlertAction * _Nonnull action) { [self goToAppSystemSetting]; }]]; [self presentViewController:alert animated:YES completion:nil]; } // 若是用户封闭了接管通知服从，该方法可以跳转到APP设置页面遏制编削 - (void)goToAppSystemSetting { dispatch_async(dispatch_get_main_queue(), ^{ UIApplication *application = [UIApplication sharedApplication]; NSURL *url = [NSURL URLWithString:UIApplicationOpenSettingsURLString]; if ([application canOpenURL:url]) { if (@available(iOS 10.0, *))



注册开辟者账号和创建推送证书：您需要注册苹果开发者账号，并创建用于推送办事的开发者证书。这些证书用于身份验证和授权。

配置应用程序推送设置：在苹果开发者帐户中，您需要配置应用程序的推送设置，包含启用推送服务、配置证书和设置推送通知的内容和活动。


在使用的进程中呈现了在iOS9此后调理呈现弊端信息：This application is modifying the autolayout engine from a background thread, which can lead to engine corruption and weird crashes. This will cause an exception in a future release. AFSessionManager *mgr = [AFHTTPSessionManager manager]; [mgr.responseSerializer setAcceptableContentTypes: [NSSet setWithObjects:@"application/json", @"text/json", @"text/javascript",@"text/html", nil]]; NSMutableDictionary *dict = [NSMutableDictionary dictionary]; dict[@"id"] = @"123456789";// 



候是空的 NSDictionary *dict = array[0]; if ([dict[@"version"] floatValue] > [subVersion floatValue]) { //如果有本版本 这里要细致下如果你版本号写得是1.1.1大概1.1.1.1这样的格局，就不克不及直接转floatValue，自己想法子比力果断。 UIWindow *alertWindow = [[UIWindow alloc] initWithFrame:[UIScreen mainScreen].bounds]; alertWindow.rootViewController = [[UIViewController alloc] init]; alertWindow.windowLevel = UIWindowLevelAlert + 1; [alertWindow makeKeyAndVisible]; UIAlertController *alert = [UIAlertController alertControllerWithTitle:@"更新提示" message:@"发现新版本。为保证各条功效一般使用，请您抢先更新。" 


获得设备令牌：每一个 iOS 设备都有一个唯一的设备令牌，用于标识设备。您需要在应用程序中实现远程通知注册流程，以获得设备令牌，并将其发送给您的服务器。

创建与 APNs 的连接：在您的服务器端，您需要使用 APNs 的通讯协定与 APNs 建立毗连。APNs 供给了基于 HTTP/2 大概较旧的二进制通信协议。

创建推送哀求：一旦与 APNs 建立连接，您可以创建推送请求，并将推送消息的干系信息发送给 APNs。推送请求包括设备令牌、推送标题、内容、声音等信息。

处置推送相应：APNs 会对您的推送请求举办处理，并返回推送响应。您需要在服务器端处理这些响应，以领会推送是否告成，以及如何处理大概的毛病或败北环境。

需要细致的是，与 APNs 举行通信需要特定的开发技术和编程知识。您可以使用 Apple 提供的开发工具（如 Xcode）和相干的开发措辞（如 Swift 或 Objective-C）来实现与 APNs 的通信和推送成果。

苹果提供了细致的开发文档和教程，介绍了与 APNs 的交互和推送服务的实现方法。建议您参考苹果的开发者文档，以获取更细致的指导和指南。