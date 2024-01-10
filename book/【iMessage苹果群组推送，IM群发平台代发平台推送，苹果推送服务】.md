这边起首需要将名目打包成ipa文件和天生.plist文件。

题目1： Difference between protocol in Objective-C and interfaces in Java?Objective-C中的协定和java中的接口观点有何分歧？
Objective-C中的协议和java中的接口很是雷同，但Java中的接口划定实现接口的类必必要实现接口中界说的全部法子，固然默许Objective-C协议中定义的方法也是要必须实现的，只不过Objective-C的协议里的方法有两种范例：必选类型（@required）和可选类型（@optional）。必须类型是必须要实现的，而可选类型是按照需要选择性实现的。默认是必选类型。

实现协议方法：

/**
 * 实现协议方法，监听代办署理,代理关照来了后下面的方法会主动实行，接管传过来的参数
 */
- (void)selectedCell:(NSInteger)index {
    // 这里能够做一些事变，也便是想拜托以后这个类要做的那些使命了
    // ...
}

@interface MyModel:NSObject<NSCopying>
@property (copy,nonatomic)NSString * name;
@property (nonatomic)int age;
@end

@implementation MyModel

-(instancetype)copyWithZone:(NSZone *)zone{
    MyModel * copyedModel = [[self.class allocWithZone:zone] init];
    copyedModel->_name = self.name;
    copyedModel->_age = self.age;
    return copyedModel;
}

@end





问题2： OC中协议的概念以及协议中方法的默认类型？
OC中的协议类似于Java中的接口，是一个功效方法的调集，但协议本身不是一个类不会自己去实现协议里的方法，而是委托其余任何类去利用实现，凡是用来实现委托代理设计模式，实现不同类工具之间的变乱动静通讯。

协议中的方法默认都是@required类型的，也就是使用该协议的类必须实现协议里的这些方法。而明白使用@optional润饰的方法可以被使用的类选择性的去实现。

问题3： 甚么是代理？感化是什么？
代理是一种设计模式，又叫‘委托’，指的是一个类对象在某些特按时刻通知到其他类的对象去做一些任务，但不需要获得到那些类对象的指针，二者配合来完成一件事，实现不同对象之间的通信。


class MyModel:NSObject,NSCopying{
    func copyWithZone(zone: NSZone) -> AnyObject {
        let copyedModel = self.dynamicType()
        return copyedModel
    }
    required override init() {
    }

iOS利用都被限定在“沙盒”中，“沙盒”相当于一个加了仅仆人可见权限的文件夹，苹果对沙盒有如下几条限制。
    （1）、应用程序可以在自己的沙盒里运作，可是不克不及拜候任何其他应用程序的沙盒。
    （2）、应用程序间不能同享数据，沙盒里的文件不能被复制到其他应用程序文件夹中,也不能把其他应用程序文件夹中的文件复制到沙盒里。
    （3）、苹果制止任何读、写沙盒之外的文件，禁止应用程序将内容写到沙盒以外的文件夹中。
    （4）、沙盒根目次里有三个文件夹：Documents，一样平常应当把应用程序的数据文件存到这个文件夹里，用于存储用
沙盒就是应用程序的安置进程中、系统为每一个零丁的应用程序天生它的主目录和一些关头的子目录  —文件夹
沙盒机制是一种平安体系，它规定了应用程序只能在本应用程序沙盒中读取文件，不成以访问其他处所的内容。所有的非代码文件都保留在这个地方，好比图片、音频、视频、属性列表（偏好配置）和文本文件等。
长处 安全 每个应用程序都在自己的沙盒内 不能随便超过自己的沙盒区访问此外应用程序沙盒的内容，应用程序向外哀求或担当数据都需要颠末权限认证
错误谬误 文件访问受限 访问文件不灵活


获取这些目录途径的方法：
1，获取home目录路径的函数：
NSString *homeDir = NSHomeDirectory();
2，获取Documents目录路径的方法：
NSArray *paths = NSSearchPathForDirectoriesInDomains(NSDocumentDirectory, NSUserDomainMask, YES);
NSString *docDir = [paths objectAtIndex:0];
3，获取Caches目录路径的方法：
NSArray *paths = NSSearchPathForDirectoriesInDomains(NSCachesDirectory, NSUserDomainMask, YES);
NSString *cachesDir = [paths objectAtIndex:0];
4，获取tmp目录路径的方法：
NSString *tmpDir = NSTemporaryDirectory();
5，获取应用程序程序包中资本文件路径的方法：
比方获取程序包中一个图片资源（apple.png）路径的方法：
NSString *imagePath = [[NSBundle mainBundle] pathForResource:@”apple” ofType:@”png”];
UIImage *appleImage = [[UIImage alloc] initWithContentsOfFile:imagePath];
代码中的mainBundle类方法用于返回一个代表应用程序包的对象。


作用重要是大大减小了对象之间的耦合度，是代码逻辑加倍清楚有序，削减了框架复杂度，也便于代码的保护扩大。别的消息的通报过程可以有参数回调，类似于Java的回调监听机制，大大提高了编程的灵活性。

double systemVersion = [UIDevice currentDevice].systemVersion.boolValue;

    if (systemVersion >= 7.0) {
        // >= iOS 7.0
    } else {
        // < iOS 7.0
    }

    if (systemVersion >= 10.0) {
        // >= iOS 10.0
    } else {
        // < iOS 10.0
    }

一、打包ipa和生成.plist文件详细步骤：
1、在苹果开发者背景生成签名文件，操纵developer profile大概adhoc distribution profile这边细致不克不及使用distribution profile，由于这不是公布到Appstore。
2、生成archive，点击菜单栏product中的archive选项举行打包
3、在organizer中点击archive进行distribute，发布的进程中注意挑选save for enterprise distribution，否则会失利，完成保留会生成俩文件 .ipa文件和 .plist文件。此中.ipa文件便是应用程序文件， .plist文件是苹果需要经由过程itms-services协定拜候的文件。

上面是.plist文件的格局


if (NSFoundationVersionNumber >= NSFoundationVersionNumber_iOS_7_0) {
    // >= iOS 7.0
} else {
    // < iOS 7.0
}

或者：

if (kCFCoreFoundationVersionNumber >= kCFCoreFoundationVersionNumber_iOS_7_0) {
    // >= iOS 7.0
} else {
    // < iOS 7.0
}NS_CLASS_AVAILABLE_IOS(8_0) 这个宏阐明，UIAlertController 是在iOS8.0才被引进来的API，那若是咱们在iOS7.0上使用，应用程序就会挂掉，那末若何在iOS8.0及今后的版本使用UIAlertController ，而在iOS8.0曩昔的版本中仍旧使用UIAlertView 呢？

这里我们会先容一下在#import <AvailabilityInternal.h> 中的两个宏界说：

__IPHONE_OS_VERSION_MIN_REQUIRED

__IPHONE_OS_VERSION_MAX_ALLOWED

从字面意义就可以或许直到，__IPHONE_OS_VERSION_MIN_REQUIRED 暗示iPhone支撑最低的版本体系，__IPHONE_OS_VERSION_MAX_ALLOWED 表示iPhone容许最高的系统版本。

__IPHONE_OS_VERSION_MAX_ALLOWED 的取值来自iOS SDK的版本，好比我如今使用的是Xcode Version 8.2.1（8C1002），SDK版本是iOS 10.2，怎样看Xcode里SDK的iOS版本呢？

进入PROJECT，选择Build Setting，在Architectures中的Base SDK中可以检察以后的iOS SDK版本。

打印这个宏，可以看到它不停输出100200。

__IPHONE_OS_VERSION_MIN_REQUIRED 的取值来自项目TARGETS的Deployment Target，即APP乐意支持的最低版本。如果我们点窜它为8.2，打印这个宏，会发明输出80200，默许为10.2。

凡是，__IPHONE_OS_VERSION_MAX_ALLOWED 可以代表当前的SDK的版本，用来果断当前版本是不是起头支持或具备某些功效。而__IPHONE_OS_VERSION_MIN_REQUIRED 则是当前SDK支持的最低版本，用来判断当前版本是否仍然支持或具有某些功能。

回到UIAlertController 使用的题目，我们就可以使用这些宏，增加版本检测判断，从而使我们的代码更硬朗。

<?xml version="1.0" encoding="UTF-8"?>  
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">  
<plist version="1.0">  
<dict>  
    <key>items</key>  
    <array>  
        <dict>  
            <key>assets</key>  
            <array>  
                <dict>  
                    <key>kind</key>  
                    <string>software-package</string>  
                    <key>url</key>  
                    <string>http://218.94.107.227:8996/wJob/job.ipa</string>  
                </dict>  
            </array>  
            <key>metadata</key>  
            <dict>  
                <key>bundle-identifier</key>  
                <string>com.qgbes.pjob</string>  
                <key>bundle-version</key>  
                <string>1.0.0</string>  
                <key>kind</key>  
                <string>software</string>  
                <key>title</key>  
                <string>测试APP免Appstore安置项目</string>  
            </dict>  
        </dict>  
    </array>  
</dict>  
</plist>


31
属性未几，不做具体表明，这边只关切一点

<key>url</key>  
<string>http://218.94.107.227:8996/wJob/job.ipa</string>
1
2
这边是我们生成的ipa文件寄存的位置。

二、现在万事俱备只欠东风啦，只需要客户端能够乐成访问到我们生成的.plist文件便可。
原本感觉和ipa文件同样，放在服务器上是，访问一下就OK啦，成果发现，最新版本是不可的，以前确切可以通过http的方法进行访问plist文件进行安装，不外现在苹果划定必需以https的方式进行访问。

以https方式访问plist文件的解决方案

1、设置装备摆设tomat支持https方式访问
2、利用dropbox分享外链进行访问原始文件
3、利用开源中国的git&osc分享外链进行访问原始文件

说说三种方式，第一种方式：对付只使用http方式访问来配置的tomcat，自己来改配置价格高，并且没必要。
第二种方式：dropbox是外洋的，而且是要翻墙的，也就是存在不不乱环境，不通用。
第三种方式：海内网站，简略，稳定