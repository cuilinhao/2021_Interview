
## 得物 

KVO  will change value什么时候调用 

CocoPod    install和update有什么区别 
Pod文件干嘛用的  
lock文件是干嘛用的
[造成死锁的四个条件](https://blog.csdn.net/jyy305/article/details/70077042?utm_source=app&app_version=4.14.1)
自旋锁和递归锁的区别
Nslock是什么锁
Nslock里面加Nslock
atomic 安全吗？用的什么锁
信号量里面加信号量有什么问题
监听卡顿怎么监听的，为什么在beforewaiting
为什么在主线程刷新UI 子线程也可以刷新UI   
runloop 是一个循环吗  
在main中 子线程调用不会执行  
FMDB用的什么线程  
weak怎么处理 
weak属性什么时候销毁  
自动释放池原理，自己写auto release和不写autoreleas有什么区别   
并行 串行 信号量是什么锁   
字典用的什么hash表 
hash碰撞怎么解决的，放在减1的位置，
为什么 打包用的ipa是怎么加壳    
一个字典里面存储10000个数据，怎么快速找到  
Nsoperation里面的KVO是怎么监听的，源码看过吗  
Afnet取消是怎么处理的，这个时候可能服务器有响应，或者没响应

2.0和3.0区别  内存怎么分，有堆栈。。。  
实现一个读写锁  runloop 的三个阶段
     
## B站面试   

锁忘了释放，怎么办，怎么处理，比如oc的try cache

 __block 多线程 HTTP2.0加了什么东西

下面代码有什么问题
 #import <Foundation/Foundation.h> int main(int argc, const char * argv[]) { 	 	//变量存在寄存器中 	@autoreleasepool { 		__block NSObject *obj = nil; 		 		dispatch_async(dispatch_get_global_queue(QOS_CLASS_USER_INTERACTIVE, 0), ^{ 			 			while (YES) { 				NSLog(@"%@", [obj description]); 			} 		}); 		while (YES) { 			obj = [NSObject new]; 			NSLog(@"new obj"); 		} 	} 	return 0; }   
 
##阿里
大数据存储
用事物  
国密算法 都有哪些
 
##平安
mutableCopy进行自定义对象拷贝
为分类添加关联属性，怎么添加一个weak的 属性默认的是atomic  
字符串用等号可以判断吗 相同字符串，创建地址相同
计算属性，可以节省资源
当第一次调用的时候，会调，如果属性里面的值一直不变，则计算属性不会再调用
 
##百度 
内存管理，引用计数，什么时候不是0 
一个ip地址，怎么转成int，且，可以变回字符串
AFN和原生的请求有什么区别  内存管理 weak修饰可选型 unown修饰非可选型，有区别的  

##哈罗面试

autorelease 什么时候释放

点击事件扩大范围
 事件响应 
GCD怎么取消 
autorelease和runloop什么关系

Https 是怎么通信的

Block里面什么时候要强引用一下

__weak 和__strong 一定要成对出现吗？ [举个例子](https://www.jianshu.com/p/fe772a3536ca)
   
抓包需要证书吗？ 
怎么抓取微信的包

Https 安全吗？ 不安全怎么办

 
##  哈罗二面

  KVO是多线程的吗，同步还是异步
   大量数据对一个属性观察，有什么问题  怎么实现一个埋点  
    
##    识货
自己实现一个异常的捕获 
html怎么调用oc 底层怎么实现的 
Swift中的RAC 不管是哪个vc怎么获取viewdidload方法 
用方法交换 怎么让父类的initial方法不调用 奔溃有几种方式 
    
## 中通一面：

AFN的缓存 怎么存储的  【AFNetworking的缓存机制】https://mbd.baidu.com/ma/s/cky7ZwnW 
 
 [关于AFNetworking的缓存机制](https://mbd.baidu.com/ma/s/9KDRqHLu)  

LRU缓存和 NSCache怎么存储的


怎么去中断一个线程 https://jingyan.baidu.com/article/d169e18658875a436611d8f4.html 
https://www.jianshu.com/p/cbe3945b7316   coreData 中怎么创建主键
 //https://blog.csdn.net/iCloudEnd/article/details/108089925  coreData 没有主键的概念
  CoreData 多线程
https://www.jianshu.com/p/283e67ba12a3 

读写文件 时，读和写都不安全吗 

## 京东

c语言 const* 和 *const  
当在最前面的时候,表示指针不允许被改变,值可以改变. 
const NSString * nameFir = @"test"; 
当在中间的时候,同上 NSString const * nameSec = @"test"; 
当在最后的时候,表示指针可以被改变,但是值不能改变(最常用) NSString * const nameThi = @"test"; 
经验总结 const右边最近的内容不可以被改变.  
 c语言，结构体和共同体
 bss段 https://www.jianshu.com/p/2d4acf4a53f9 
 内存分为5个区域，分别指的是----->栈区/堆区/BSS段/数据段/代码段        栈：存储局部变量，当其作用域执行完毕之后，就会被系统立即收回        
 堆：存储OC对象，手动申请的字节空间，需要调用free来释放        
 BSS段：未初始化的全局变量和静态变量，一旦初始化就会从BSS段中回收掉，转存到数据段中        
 数据段：存储已经初始化的全局变量和静态变量，以及常量数据，直到结束程序时才会被立即收回        
 常量区：存放常量字符串，程序结束后由系统释放        
 代码段：存放函数的二进制代码，直到结束程序时才会被立即收回
     
  int和NSinteger有什么区别  
  NSInteger会自动识别当前电脑系统是32位还是64位数，然后自动返回最大的类型(int还是NSInteger)。例如，当前电脑为32位系统,你声明的NSInteger自动变为int。当前电脑为64位系统,你声明的NSInteger还是NSInteger。  
  所以32位系统，int的长度等于NSInteger的长度；64位系统，int的长度小于NSInteger的长度；也就是说NSInteger的长度一定是大于等于int的长度的。  
  知道了这个原理，当你不知道电脑的系统是几位，并且你正在声明一个整形变量，你一定要使用NSInteger，不要使用int,你可以当成一种规范。记住：在多数情况下一定尽可能的使用NSInteger。      
重定向码是多少，放在那个字段里面 重定向，300-399,放在location字段 
为什么4次挥手

内存管理，引用计数，什么时候不是0
一个ip地址，怎么转成int，且，可以变回字符串

AFN和原生的请求有什么区别

内存管理
weak修饰可选型
unown修饰非可选型，有区别的

oc调is

要先注册
二 我们在控制器中初始化WKWebView，注册方法.

1.初始化

```objectivec
//创建网页配置对象.
    WKWebViewConfiguration *configuration = [[WKWebViewConfiguration alloc] init];
    //是使用h5的视频播放器在线播放, 还是使用原生播放器全屏播放
    configuration.allowsInlineMediaPlayback = YES;
    //设置视频是否需要用户手动播放  设置为NO则会允许自动播放
    if (@available(iOS 10.0, *)) {
        configuration.mediaTypesRequiringUserActionForPlayback = YES;
    } else {}
    //设置是否允许画中画技术 在特定设备上有效
    configuration.allowsPictureInPictureMediaPlayback = YES;
    //设置请求的User-Agent信息中应用程序名称 iOS9后可用
    configuration.applicationNameForUserAgent = @"ChinaDailyForiPad";

   //自定义的WKScriptMessageHandler 是为了解决内存不释放的问题.
    WeakWebViewScriptMessageDelegate *weakScriptMessageDelegate = [[WeakWebViewScriptMessageDelegate alloc] initWithDelegate:self];
    //这个类主要用来做native与JavaScript的交互管理
    WKUserContentController * wkUController = [[WKUserContentController alloc] init];
    //注册一个name为jsToOcNoPrams的js方法 设置处理接收JS方法的对象
    [wkUController addScriptMessageHandler:weakScriptMessageDelegate  name:@"jsToOcNoPrams"];
    [wkUController addScriptMessageHandler:weakScriptMessageDelegate  name:@"jsToOcWithPrams"];
    configuration.userContentController = wkUController;

   //创建设置对象.
    WKPreferences *preference = [[WKPreferences alloc]init];
    //最小字体大小 当将javaScriptEnabled属性设置为NO时，可以看到明显的效果
    preference.minimumFontSize = 0;
    //设置是否支持javaScript 默认是支持的
    preference.javaScriptEnabled = YES;
    //在iOS上默认为NO，表示是否允许不经过用户交互由javaScript自动打开窗口
    preference.javaScriptCanOpenWindowsAutomatically = YES;
    configuration.preferences = preference;

   self.webView = [[WKWebView alloc] initWithFrame:CGRectMake(0, 0, [UIScreen mainScreen].bounds.size.width, [UIScreen mainScreen].bounds.size.height) configuration:configuration];
    //UI代理.
    self.webView.UIDelegate = self;
    //导航代理.
    self.webView.navigationDelegate = self;
    //是否允许手势左滑返回上一级, 类似导航控制的左滑返回.
    self.webView.allowsBackForwardNavigationGestures = YES;

（滑动显示更多）

autolayout 与frame区别

值类型 属性包装器

怎么判断对钩手势
assign修饰，释放不了，出现野指针

状态机

【iOS开发笔记之七十三——基于状态机的页面构建方案_iOS开发笔记-CSDN博客_ios 状态机】https://blog.csdn.net/lizitao/article/details/81055648

关联库

设计一个app，架构上
点击H5会调原生的方法，原理是因为拦截
要先注册

https://mp.weixin.qq.com/s/iFEfgzU1g9RghFb9rpLHCg


left和leading 区别
在中国 ，left和leading是一样的，但是在阿拉伯，leading相当于right

三等分一个view

Swift

逃逸与非逃逸注意点
MVVM
MVVM的作用就瘦身吗
二进制重拍
线程同步，使用锁
检测存在uiwebview 用逆向
Grep 
block获取的是地址值吗


nsurlsession 和nsurlconnection 区别


设计一个malloc 和release

UIGraphicsBeginImageContextWithOptions(contentSize, NO, [UIScreen mainScreen].scale);
    CGContextRef content = UIGraphicsGetCurrentContext();

    
    UIImage *image = UIGraphicsGetImageFromCurrentImageContext();
    UIGraphicsEndImageContext();
    CFRelease(path);

http 缓存
Cache-control

copy自定义对象？如何拷贝大的数据量
使用归档

如果对象很多或者层级很多，实现起来还是很麻烦的。如果需要实现完全复制同样还有另有一种方法，那就是归档:



UI问题，tableciew有3个半，那一共有几个
copy很多数据
方法不让别人用，报错，怎么写代码

组件化，使用字典会有很多字符串(硬编码)

怎么优化，传递模型？

，Swift
Json转Model

https://juejin.cn/post/7019910939340193805

面试

https://juejin.cn/post/7006273689675120677

lazy遇到的问题

https://juejin.cn/post/6844903571209584653

没故事的桌同学 Swift Collection 中的 lazy 作用


https://juejin.cn/post/6844903566772027406


全局队列有2个枚举 
竞争和非竞争

http 3次握手之前做什么
DNS 转ip


瀑布流

锁怎么工作的
Runloop 有几种不同状态，会退出吗

Hook方法注入是动态库，那系统是如何调用我们的方法的

如何交换c语言的方法
检测FPS 
Socket和HTTP区别
交换oc方法，但是要自己写的方法和交换的方法都执行，怎么处理
imp和sel区别，和Select有什么区别
OC如何实现多继承


给一个数字，怎么判断有没有2个要找的数，


socket和http区别：
HTTP协议：简单对象访问协议，对应于应用层 ，HTTP协议是基于TCP连接的
　　tcp协议： 对应于传输层
　　ip协议： 对应于网络层
　　TCP/IP是传输层协议，主要解决数据如何在网络中传输；而HTTP是应用层协议，主要解决如何包装数据。
　　Socket是对TCP/IP协议的封装，Socket本身并不是协议，而是一个调用接口（API），通过Socket，才能使用TCP/IP协议。
　　http连接：http连接就是所谓的短连接，即客户端向服务器端发送一次请求，服务器端响应后连接即会断掉；
　　socket连接：socket连接就是所谓的长连接，理论上客户端和服务器端一旦建立起连接将不会主动断掉；但是由于各种环境因素可能会是连接断开，比如说：服务器端或客户端主机down了，网络故障，或者两者之间长时间没有数据传输，网络防火墙可能会断开该连接以释放网络资源。


mmap 

熟悉fastlane的工具


点击一个按钮，runloop 怎么走的


Masonry有什么缺点，时间复杂度是多少

网络访问ip
目标ip和源ip会有变化吗



