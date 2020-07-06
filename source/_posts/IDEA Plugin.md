### Swagger Format插件

事情是这样的。

之前一直和C端后台对接，用的是Yapi来管理接口文档。我们拿到gson后用GsonFormat转换成实体类，yapi上工整的表格随时查阅字段含义，重要的自己补上注释。突然有天，对接B端的业务了。业务复杂程度升了一级，自己补充注释不那么愉快了，Swagger UI拿到手的时候，发现这生成的Model和实体类格式好像呀，稍稍转换下就可以直接用了！

#### 效果：

<img src="/images/SwaggerFormat.gif" alt="SwaggerFormat" style="zoom:35%;" />

<img src="/images/YapiFormat.gif" alt="YapiFormat" style="zoom:35%;" />

#### 源码：[SwaggerFormat](https://github.com/aiyayin/SwaggerFormat)

#### 装IDEA，和插件开发的基本教程。

[官网链接](https://www.jetbrains.org/intellij/sdk/docs/basics/basics.html)

这位大佬的注释很清楚！：[插件开发（一）一个简单的表单demo](https://exceting.github.io/2019/12/13/IDEA插件开发（一）一个简单的表单demo/)

这位大佬有完整的教程：[IntelliJ IDEA插件开发指南(一)](https://blog.csdn.net/ExcellentYuXiao/article/details/80273109)

#### 看GsonFormat的源码学习。

源码链接：https://github.com/zzz40500/GsonFormat

这位大佬有对GsonFormat源码分析和二改：[GsonFormat源码分析和二改](https://juejin.im/post/5becde6af265da61524cf62f#heading-8)

### 记录期间遇到的问题：

一直下载idea： [build.gradle里写死version](https://github.com/JetBrains/gradle-intellij-plugin/issues/323)

找不到PsiClass：[build.gradle里引入java插件](https://www.jetbrains.org/intellij/sdk/docs/basics/plugin_structure/plugin_dependencies.html)

生成的包引入android  studio的时候报" plugin 'XXX' is incompatible with this installation"：

查看你studio的版本，降低plugin.xml中since-build到studio的版本，在build.gradle的intellij中加入updateSinceUntilBuild false [配置插件](https://kana112233.github.io/intellij-sdk-docs-cn/tutorials/build_system/deployment.html)