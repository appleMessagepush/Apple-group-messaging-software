# 【苹果rcs群发iMessage苹果手机群发短信真机群发】

AppID，这是每个应用程序的独立标识符，配置应用程序的权限，例如存折，游戏机和更常用的推送服务，它可以创建以创建证书，如下所述，所以 在所有和驱动相关配置中的配置中，首先要做的是打开支持服务的AppID; 3，推送证书（分为两种类型的开发和发布，类型是APNSDevelopmentis，APNSDistributions，以及证书在AppID配置中创建结构建筑物，以及像证书的开发人员到计算机的开发;



AppID主要有以下内容：1），ExplicitAppID：唯一的AppID，此AppID用于唯一的身份应用程序，如com.wzc.demo，标识com.wzc.demo的bundleid。 2），WildCardAppID：Wildcard AppID，用于标识一组应用程序。 例如，*可以代表所有应用程序和com.wzc。 *您可以代表以com.wzc开头的所有应用程序。 创建AppID时，我们可以设置AppID使用的AppService。 每个服务都有不同的要求，例如，如果要使用ApplePushnotificationservices，则必须是ExplicitAppID以唯一标识应用程序。 以下是目前目前的可选服务和相应的配置要求。 如果您的应用程序使用上述任何服务，则必须根据需要配置。 1.3，DeviceVices包含可在帐户中开发和测试的所有设备。 每个设备都使用UDID唯一标识。 每个帐户中的设备数量为100. 1.4，

#include<WiFi.h>

 

const char* id="wifi名称";              //常量定义

const char* psw="wifi密码";

 

String transEncryptionType(wifi_auth_mode_t encryptionType){		//对比出该wifi网络加密类型并返回相应的String值   

  switch(encryptionType){

      case (WIFI_AUTH_OPEN):

        return "Open";

      case (WIFI_AUTH_WEP):

        return "WEP";

      case (WIFI_AUTH_WPA_PSK):

        return "WPA_PSK";

      case (WIFI_AUTH_WPA2_PSK):

        return "WPA2_PSK";

      case (WIFI_AUTH_WPA_WPA2_PSK):

        return "WPA_WPA2_PSK";

      case (WIFI_AUTH_WPA2_ENTERPRISE):

        return "WPA2_ENTERPRISE";

      default:

        return("Unkonwn EncryptionType");

  }

}

 

void scanNetworks(){						//扫描周边wifi网络，并显示wifi数量，打印它们的属性（ssid，信号强度，加密方式，mac地址）

  int numberOfNetworks= WiFi.scanNetworks();

  Serial.print("The number of networks found is:");

  Serial.println(numberOfNetworks);

  for(int i=0;i<numberOfNetworks;i++){

    Serial.print("Networkname: ");

    Serial.println(WiFi.SSID(i));

    Serial.print("Signalstrength: ");

    Serial.println(WiFi.RSSI(i));

    Serial.print("MACaddress: ");

    Serial.println(WiFi.BSSIDstr(i));

    Serial.print("Encryptiontype: ");

    String encryptionTypeDescription = transEncryptionType(WiFi.encryptionType(i));

    Serial.println(encryptionTypeDescription);

    Serial.println("-----------------------");

  }

}

 

void connect(){							//连接到指定wifi

  WiFi.begin(id,psw);

   while (WiFi.status()!= WL_CONNECTED) {

    delay(1000);

    Serial.println("正在尝试连接该wifi...");

  }

  Serial.println("连接成功！");

}

 

void setup() {

  Serial.begin(115200);                //初始化配置，波特率115200

  scanNetworks();						//扫描wifi并打印信息

  connect();							//连接到指定wifi

  Serial.println(WiFi.macAddress());		//打印esp32的mac地址

  Serial.println(WiFi.localIP());			//esp32此刻的本地ip地址

  WiFi.disconnect(true);					//断开当前wifi网络的连接

  Serial.println(WiFi.localIP());  			//打印esp32此刻的本地ip地址

}

 

void loop(){

  

}


ProvisioningProfile提供上面的所有文件：证书，AppID和设备。 要在真机上打包或运行应用程序，您需要证书标志以识别此申请是合法的，安全的，完成; 然后，您需要指示其AppID，并验证BundleId是否一致; 同样，如果需要确认设备是否可以运行程序，则是真正的机器调试。 ProvisioningProfile包装在一起，以便在调试和发布过程中使用它，只要在不同的情况下选择不同的配置文件文件。 在包装中，ProvisionProfile文件将被嵌入.IPA。 例如，如下所示，开发的ProvisioningProfile包含与AppID，可用证书和设备对应的新功能。 这条手段使用此提供服务包必须具有相应的证书，并将应用程序运行到应用程序中包含的设备。 如上所述，在设备上运行的进程如下：如证书，ProvisioningProfile还分为开发和分发。


4，ProvisioningProfiles，此事是一个非常苹果字符，我通常会调用PP文件，文件将绑定AppID，开发人员证书，硬件设备，并且可以在配置开发人员中心后添加。 在Xcode上，您还可以直接在Xcode上直接连接到开发人员中心。 调试时，您需要在PP文件中添加一个真实机; 这是一个真正的机器调试器，必须是宝藏; 通常，我们的生产过程通常按下上述顺序，首先使用开发人员帐户登录开发人员中心，创建开发人员证书，AppID，打开AppID的推送服务，在服务选项下创建推送证书（ 请参阅下面的服务器端推送证书），然后绑定所有证书ID，添加试验测试等。具体过程如下

/**************************myMacAddress.c************************************* 


 * 实现了C语言获取本机的mac地址

 * 备注：

 * 网上相关的实现有很多，比如有调用API的、通过访问网卡获取的，等等。并且问过了老师，直接调shell的命令不行，也就意味着system(“ipconfig”)这样的代码不允许出现

 * 但我不想访问网卡什么的，那么应该怎么办呢？

 * 受到ping命令的启发，我的想法是通过一次网络连接请求，获取本机mac地址

 * 在构思结束后我上网查相关资料，才发现我的想法对应的是一个叫ARP协议的东西



 ****************************************************************************/  

 

#include <stdio.h>

#include <pcap/pcap.h>

#include <netinet/if_ether.h>

 

int main(){

    pcap_t *sniffer_des;

    char errbuf[PCAP_ERRBUF_SIZE];// PCAP_ERRBUF_SIZE is in {/usr/include/pcap/pcap.h}

                                  // the Defination is {#define PCAP_ERRBUF_SIZE 256}

    char *net_dev;

    bpf_u_int32 net, mask;

    struct bpf_program fp;          // 可理解为结构体实例化(Copyri

    const u_char *packet;

    struct pcap_pkthdr hdr;         // 可理解为结构体实例化

    struct ether_header *eth_header;// 可理解为结构体实例化

    u_char *ptr;

 

 

    net_dev = "en7";//此处为我的网卡编号，一般的机子此处应为eth0

    if(pcap_lookupnet(net_dev, &net, &mask, errbuf) == -1){

        printf("get net error:%s\n", errbuf);

        return 1;

    }

 

    sniffer_des = pcap_open_live(net_dev, 1024, 1, 5000, errbuf);// 调用PCAP_API中的pcap_open_live

    // sniffer_des = pcap_open_live(net_dev, 65535, 1, 5000, errbuf);// 调用PCAP_API中的pcap_open_live

    //
    // 看了pcap的pcap_open_live函数也没有看明白什么原因，我怀疑时内部处理分配内存的时候，每一个包分配65535大小肯定比分配处理1024包大小的内存耗时，所以导致丢包。

    // 请各位用pcap的时候牢记这个东东吧，我可吃过苦了。。。。

    if(sniffer_des == NULL){

        printf("pcap_open_live%s\n", errbuf);

        return 1;

    }

 

 

    if(pcap_setfilter(sniffer_des, &fp) == -1){

        printf("pcap_setfilter() error\n");

        return 1;

    }

 

    packet = pcap_next(sniffer_des, &hdr);

    if(packet == NULL){

        printf("pacap_next() failed\n");

        return 1;

    }

 

 

    eth_header = (struct ether_header*)packet;

    if(ntohs(eth_header->ether_type) != ETHERTYPE_IP){// ETHERTYPE_IP is in {/usr/include/net/ethernet.h}, 

                                                      // the Defination is {#define ETHERTYPE_IP 0x0800}==>IP数据报的以太网帧类型也是0x0800(IPv4: 0x0800)

        printf("not ethernet packet\n");              // 若ether_type（类型）不是ip数据报，则报错(Copyrightov. All Rights Reserved)

        return 1;

    }

 

 

 

    ptr = eth_header->ether_shost;

    int i = 0;

    printf("\nMy Physical Adress(MAC):");

    while(i < ETHER_ADDR_LEN){                          // The number of bytes in an ethernet (MAC) address.

                                                        // #define  ETHER_ADDR_LEN      6

        printf(" %x:", *ptr++);

        i++;

    }

 

    printf("\n");

    return 0;

 

}


：1。生成开发人员证书，首先登录开发人员中心，查找已配置的证书 ，然后带它，然后单击“证书”。 将出现以下接口，单击下面显示的右上角的加号，并重复操作两次，并创建开发测试证书和证书。 开发真实机器调试的测试证书，证书用于提交给AppStore，我们的开发测试证书是一个示例，选择第一个红色框中的内容; 然后，将提示CSR文件，即证书标记请求文件，将有一个详细的方式，如果英语不是很好，可以参考地图; 然后将CSR文件保存到一个; 注意：CSR文件尽可能多地使每个证书区分开，因为用户的名称是证书名称中的键; 然后在社交中心提交CSR文件; 如果提交，将生成CER证书，如图所示，有效期为一年; 使用相同的方法配置已发布的证书，下载保存，双击安装; 在校准登录证书中，您可以查看私钥的名称。 CSR请求文件的名称;




2.已完成开发人员证书的配置，让我们配置APPID并推送证书; 选择左列中的AppID，选中“正确”选项，为应用程序的应用程序添加一个按钮，将看到创建的按钮，即证书和发布证书，以下过程与上述1中的证书相同 ，首先建立证书请求文件。 然后，提交它，有必要注意，尽管您可以直接在左列证书栏中创建推送证书，但建议在此创建推送服务以避免忘记。 打开推送服务时不可用。 创建证书后，您将保存下载，双击安装;





3，我们将完成PP文件两次，创建开发测试PP文件并释放PP文件，对于真正的机器测试，后者用于提交释放; 通常在公司帐户中使用的adhoc格式，我们在这里被忽略; 选定的提交自动检测匹配AppID，除了通配符格式，此格式除外，此格式将自动生成，使用*通配符，适用于批量，无推送，密集卡等。
