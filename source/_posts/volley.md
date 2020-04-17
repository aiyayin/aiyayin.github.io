这是仔细研究的第一个框架了，当时用的是mvp+volley。

面向接口编程，可高度自定义呀，实现Cache，可以管理消息队列；实现HttpStack，可以替换底层的网络请求方式。

但是虽然提供了cancle方法，还是存在内存泄漏呀。
它的cancle()只是修改了Request的mCanceled值，在执行run方法取这个request要执行performRequest之前会看是否是取消的，如果是取消了的，会执行finish，finish时将response的回调置空，不会泄露。在这之后取消，还是可能通过Response.Listener和Response.ErrorListener持有当前activity，导致泄漏。仍记得在Presenter里面网络请求的回调里都要对view进行判空，不然有一大波空指针在等你。

这位大佬也研究过：![Volley与内存泄露](https://www.jianshu.com/p/83fd6efe0703)

附上当时画的不规范的图!

![(类图)](/images/volley.png)