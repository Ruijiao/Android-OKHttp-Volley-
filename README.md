# Android-OKHttp-Volley-
### 主要是总结当前网络框架的优缺点，方便在需要的时候找到合适的

原文 链接：https://www.zhihu.com/question/35189851/answer/82992547

volley是一个简单的异步http库，仅此而已。
  缺点是不支持同步，这点会限制开发模式；不能post大数据，所以不适合用来上传文件。
android-async-http。
  与volley一样是异步网络库，但volley是封装的httpUrlConnection，它是封装的httpClient，而android平台不推荐用HttpClient了，所以这     个库已经不适合android平台了。
okhttp是高性能的http库，
  支持同步、异步，而且实现了spdy、http2、websocket协议，api很简洁易用，和volley一样实现了http协议的缓存。
  picasso就是利用okhttp的缓存机制实现其文件缓存，实现的很优雅，很正确，反例就是UIL（universal image                                loader），自己做的文件缓存，而且不遵守http缓存机制。
retrofit与picasso一样都是在okhttp基础之上做的封装，项目中可以直接用了。
另外
  AndroidAsync这个网络库使用了nio的方式实现的。okhttp没有提供nio的方式，不过nio更适合大量连接的情况，对于移动平台有点杀鸡用牛刀的味道。
  picasso、uil都不支持inbitmap，项目中有用到picasso的富图片应用需要注意这点。

