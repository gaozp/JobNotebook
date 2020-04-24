#### binder如何精确制导

#### 系统服务与bindService等启动的服务的区别
服务的启动方式
服务的注册与管理
服务的请求使用方式
#### Android APP进程天生支持Binder通信的原理是什么

#### Android APP有多少Binder线程，是固定的么？

#### IntentService作用是什么,AIDL解决了什么问题
生成一个默认的且与主线程互相独立的工作者线程来执行所有传送至onStartCommand() 方法的Intent。
生成一个工作队列来传送Intent对象给你的onHandleIntent()方法，同一时刻只传送一个Intent对象，这样一来，你就不必担心多线程的问题。在所有的请求(Intent)都被执行完以后会自动停止服务，所以，你不需要自己去调用stopSelf()方法来停止。
该服务提供了一个onBind()方法的默认实现，它返回null
提供了一个onStartCommand()方法的默认实现，它将Intent先传送至工作队列，然后从工作队列中每次取出一个传送至onHandleIntent()方法，在该方法中对Intent对相应的处理。
AIDL (Android Interface Definition Language) 是一种IDL 语言，用于生成可以在Android设备上两个进程之间进行进程间通信(interprocess communication, IPC)的代码。如果在一个进程中（例如Activity）要调用另一个进程中（例如Service）对象的操作，就可以使用AIDL生成可序列化的参数。 AIDL IPC机制是面向接口的，像COM或Corba一样，但是更加轻量级。它是使用代理类在客户端和实现端传递数据。

#### LaunchMode应用场景
standard，创建一个新的Activity。

singleTop，栈顶不是该类型的Activity，创建一个新的Activity。否则，onNewIntent。

singleTask，回退栈中没有该类型的Activity，创建Activity，否则，onNewIntent+ClearTop。

singleInstance，回退栈中，只有这一个Activity，没有其他Activity。
##### 应用：
singleTop适合接收通知启动的内容显示页面。
例如，某个新闻客户端的新闻内容页面，如果收到10个新闻推送，每次都打开一个新闻内容页面是很烦人的。
singleTask适合作为程序入口点。
例如浏览器的主界面。不管从多少个应用启动浏览器，只会启动主界面一次，其余情况都会走onNewIntent，并且会清空主界面上面的其他页面。
singleInstance应用场景：
闹铃的响铃界面。 你以前设置了一个闹铃：上午6点。在上午5点58分，你启动了闹铃设置界面，并按 Home 键回桌面；在上午5点59分时，你在微信和朋友聊天；在6点时，闹铃响了，并且弹出了一个对话框形式的 Activity(名为 AlarmAlertActivity) 提示你到6点了(这个 Activity 就是以 SingleInstance 加载模式打开的)，你按返回键，回到的是微信的聊天界面，这是因为 AlarmAlertActivity 所在的 Task 的栈只有他一个元素， 因此退出之后这个 Task 的栈空了。如果是以 SingleTask 打开 AlarmAlertActivity，那么当闹铃响了的时候，按返回键应该进入闹铃设置界面。

#### 什么情况导致内存泄漏
1. 资源对象没关闭造成的内存泄漏
2. 构造Adapter时，没有使用缓存的convertView
3. Bitmap对象不在使用时调用recycle()释放内存
4. 试着使用关于application的context来替代和activity相关的context
5. 注册没取消造成的内存泄漏
6. 集合中对象没清理造成的内存泄漏
#### Android为每个应用程序分配的内存大小是多少

#### Handler是如何实现线程转换的？

#### Fragment的生命周期
onattach->oncreate->oncreateview->onactivitycreate->onstart->onresume->onpause->onstop->ondestoryview->ondestroy->ondetach
![img](https://upload-images.jianshu.io/upload_images/7508328-41e30f8bf75b2d1f.png?imageMogr2/auto-orient/strip|imageView2/2/w/340/format/webp)

#### APP性能优化
https://www.jianshu.com/p/da2a4bfcba68

#### choreographic
https://www.androidperformance.com/2019/10/22/Android-Choreographer/?hmsr=toutiao.io&utm_medium=toutiao.io&utm_source=toutiao.io