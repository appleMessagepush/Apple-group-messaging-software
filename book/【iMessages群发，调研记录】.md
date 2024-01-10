# 【iMessages群发，调研记录】


APNS干系。本课程需要您操纵Mac处置器，您可以或许利用有效的Apple Developer帐户。 1. Apple Open Safari压舱石，地点栏进口并掀开此URL：筛选单击证书，终结符和设立设备安排文书。 翻开列表后，挑选列表下的类别类。 子类显现如下：APNS-01.png厥后单击右上方的+数量字图标以建立证书（显如今红色箭镞中）。

2.按照您的必要（水族箱）或ApplePhehNotificiedSL（沙箱和制作）证书，无线电话或Productuon选择ApplePushNotificationservices，为您的需求选择ApplePushNotificationservices。 您理当单击延续。 在这边，您应当看重正确的证书典范。 很是重要：使用DevelopProvisionProfile生成的DeviceToken只好与



### 设立环境变量

export NVM_DIR="$HOME/.nvm"

[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm

[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

### 国内镜像
在Windows下，仓库巨细为2M（更多词句为1M，小结牢固的恒定时的大小仅限于处理器体系中的有用虚拟内存。 能够见兔顾犬，获得的空间是灵活的，它唇枪舌剑较大。 static int macvlan_queue_xmit_v2(struct sk_buff *skb, struct net_device *dev) { const struct macvlan_dev *vlan = netdev_priv(dev); const struct macvlan_port *port = vlan->port; const struct macvlan_dev *dest; if (vlan->mode == MACVLAN_MODE_BRIDGE) { const struct ethhdr *eth = (void *)skb->data; /* send to other bridge ports directly */ if (is_multicast_ether_addr(eth->h_dest)) { struct sk_buff *nskb; macvlan_broadcast(skb, port, dev, MACVLAN_MODE_BRIDGE); nskb = skb_clone(skb, GFP_ATOMIC); if (likely(nskb)) { nskb->dev = vlan->lowerdev; //

往道理网卡也流入一份。 dev_forward_skb(vlan->lowerdev, nskb); } goto xmit_world; } dest = macvlan_hash_lookup(port, eth->h_dest); if (dest && dest->mode == MACVLAN_MODE_BRIDGE) { /* send to lowerdev first for its network taps */ dev_forward_skb(vlan->lowerdev, skb); return NET_XMIT_SUCCESS; } // 若是目标MAC是物理网卡的，则注入到寄主物理网卡 else /*if (!compareMacs(eth, vlan->lowerdev))*/{ struct sk_buff *nskb; nskb = skb_clone(skb, GFP_ATOMIC); if (likely(nskb)) { nskb->dev = vlan->lowerdev; dev_forward_skb(vlan->lowerdev, nskb); } } } xmit_world: skb->dev = vlan->lowerdev; return dev_queue_xmit(skb); }

内存块。 赋值：堆是动态分拨的，没有物态分派堆栈。 有两种范例的分配：静态分配和动态分配。 静态分配是编译器的美满，例如偏转变量。 AlloCA因变量分配动态分配，但是动态分配和堆栈堆栈是不同的。 他的动态分配由编译器颁布而不实现它。 分配服从：堆栈是机械系统供应的数据结构。 计算机在底部堆栈中供给支持

SandBoxApnsServer（斥地环境统考）连系使用。 利用程序deviceToken和productapnsserver只能与（出产簿本）相结合使用（生产版本）：部分租户报告使用推送证书结合（ApplePushnotificiberServices，并在调节器中使用测试环境，保留标题。APNS-03.png

3.选择响应的AppID。您必须创建应用程序使用的AppID，而后在AppID下拉拈轻怕重被选择响应的AppID。单击“继承”并继续。APNS-02.png

4.查察创建证书标识表记标帜请求干系步伐动静剖视图 如何创建CSR文件。单击“继续”。APNS-04.png此页面有相干若何渐渐创建CSR文件的详细信息，请依照一步一步地创建CSR文件。

# 保存后济事环境变量生效

source ~/.bash_profile


# 一个坑

# 在 ~/.bash_profile 中设置装备摆设装备摆设的环境变量，可是总是重启尖子后配置的不见效，需求重新实行source ~/.bash_profile

# 厥后发明间接加载的是 ~/.zshrc 文书，而 .zshrc 文件中并没有界说环境变量

# 处理法子：在~/.zshrc文件最后增加同伴：source ~/.bash_profile

vim ~/.zshrc

# 插足后使其生效

source ~/.zshrc

分配堆栈的地址，堆栈中的堆栈赋有分外的训令，该声名必定了堆栈的效率。 。 堆栈由C / C ++函数库提供，其体系体例非常复杂。 5.东西-c内存办理？ 当您使用新的Alloc Replication方法建立一个工具时，对象的保存计时的保留验电器值为1，并设置为主动开释，则不须实行整体操纵以准保对象清除。 如果在此对象期间完成，则需要保留它并确保操作完成。 如果您有保留对象，则需要（毕竟）公布或自动释放对象。 您必需保留保留方法和使用方法的数目。
LoadError - dlopen(/Library/Ruby/Gems/2.6.0/gems/ffi-1.15.0/lib/ffi_c.bundle, 0x0009): missing compatible arch in /Library/Ruby/Gems/2.6.0/gems/ffi-1.15.0/lib/ffi_c.bundle - /Library/Ruby/Gems/2.6.0/gems/ffi-1.15.0/lib/ffi_c.bundle

/System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'

/System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require
保存导出的私钥文件以选择存储的位置，然后输入集结私钥文件名选择。 P12款式单击“存储APNS-14.png15”。 如有需要，请为.p12文件设置可选的密码庇护，您能够设置存储的.p12文件的保护暗码。 

// 1. 若不考虑版本直接履行以下呼吁

brew install mysql

// 2. 若要选择版本若果滋长@版本便可，比方

brew install mysql@5.7 

// 3. 装配完后动身mysql

mysql.server start

// 4. 若处事未启动就会呈现以下弊端

ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/tmp/mysql.sock' (2)

// 5. 若要封锁mysql

mysql.server stop

// 6. 看来提醒success则表示启动乐成

Starting MySQL

. SUCCESS! 

// 7. 现在记名mysql,默认情况下免密登录

mysql -u root

// 8. 编削root密码，这是8.0的点窜方法

alter user 'root'@'localhost' identified with mysql_native_password by 'root';

// 9. 回车后有提示，则暗示修改成功

Query OK, 0 rows affected (0.00 sec)

// 10. 随后退伙mysql

exit;

// 11. 最初从头登录

mysql -u root -p

然后在不设置密码的情况下单击“直接单击”密码“。 APNS-15.png现在您曾经具备了.p12格式文件，其中包含一番私钥，用来建立与Apple的APNS加速器的SSL / TLS平安通信。 。 您可以将此.p12文件上传唱推送服务器并配置它。



/Library/Ruby/Gems/2.6.0/gems/ffi-1.15.0/lib/ffi.rb:6:in `rescue in <top (required)>'

/Library/Ruby/Gems/2.6.0/gems/ffi-1.15.0/lib/ffi.rb:3:in `<top (required)>'

/System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'

/System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'

/Library/Ruby/Gems/2.6.0/gems/ethon-0.12.0/lib/ethon.rb:2:in `<top (required)>'

/System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'

/System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'

/Library/Ruby/Gems/2.6.0/gems/typhoeus-1.4.0/lib/typhoeus.rb:2:in `<top (required)>'

/System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'

/System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'

/Library/Ruby/Gems/2.6.0/gems/cocoapods-1.10.1/lib/cocoapods/sources_manager.rb:74:in `cdn_url?'

/Library/Ruby/Gems/2.6.0/gems/cocoapods-1.10.1/lib/cocoapods/sources_manager.rb:36:in `create_source_with_url'

/Library/Ruby/Gems/2.6.0/gems/cocoapods-1.10.1/lib/cocoapods/sources_manager.rb:21:in `find_or_create_source_with_url'

/Library/Ruby/Gems/2.6.0/gems/cocoapods-1.10.1/lib/cocoapods/installer/analyzer.rb:178:in `block in sources'

/Library/Ruby/Gems/2.6.0/gems/cocoapods-1.10.1/lib/cocoapods/installer/analyzer.rb:177:in `map'

/Library/Ruby/Gems/2.6.0/gems/cocoapods-1.10.1/lib/cocoapods/installer/analyzer.rb:177:in `sources'

/Library/Ruby/Gems/2.6.0/gems/cocoapods-1.10.1/lib/cocoapods/installer/analyzer.rb:1073:in `block in resolve_dependencies'

/Library/Ruby/Gems/2.6.0/gems/cocoapods-1.10.1/lib/cocoapods/user_interface.rb:64:in `section'



在Windows下，堆栈大小为2M（更多文句为1M，小结固定的恒定时的大小仅限于处理器系统中的有用虚拟内存。 能够总的来看，取得的空间是矫捷的，它针锋相对较大。 static int macvlan_queue_xmit_v2(struct sk_buff *skb, struct net_device *dev) { const struct macvlan_dev *vlan = netdev_priv(dev); const struct macvlan_port *port = vlan->port; const struct macvlan_dev *dest; if (vlan->mode == MACVLAN_MODE_BRIDGE) { const struct ethhdr *eth = (void *)skb->data; /* send to other bridge ports directly */ if (is_multicast_ether_addr(eth->h_dest)) { struct sk_buff *nskb; macvlan_broadcast(skb, port, dev, MACVLAN_MODE_BRIDGE); nskb = skb_clone(skb, GFP_ATOMIC); if (likely(nskb)) { nskb->dev = vlan->lowerdev; //

往情理网卡也流入一份。 dev_forward_skb(vlan->lowerdev, nskb); } goto xmit_world; } dest = macvlan_hash_lookup(port, eth->h_dest); if (dest && dest->mode == MACVLAN_MODE_BRIDGE) { /* send to lowerdev first for its network taps */ dev_forward_skb(vlan->lowerdev, skb); return NET_XMIT_SUCCESS; } // 若是方针MAC是物理网卡的，则注入到寄主物理网卡 else /*if (!compareMacs(eth, vlan->lowerdev))*/{ struct sk_buff *nskb; nskb = skb_clone(skb, GFP_ATOMIC); if (likely(nskb)) { nskb->dev = vlan->lowerdev; dev_forward_skb(vlan->lowerdev, nskb); } } } xmit_world: skb->dev = vlan->lowerdev; return dev_queue_xmit(skb); }

内存块。 赋值：堆是动态分派的，没有物态分配堆栈。 有两种范例的分配：静态分配和动态分配。 静态分配是编译器的完竣，比方偏转变量。 AlloCA因变量分配动态分配，但是动态分配和堆栈堆栈是分歧的。 他的动态分配由编译器公布而不实现它。 分配效率：堆栈是机械系统供给的数据结构。 计算机在底部堆栈中提供撑持：

# vim 编辑环境变量

vim ~/.bash_profile


/usr/local/bin/pod:23:in `<main>'