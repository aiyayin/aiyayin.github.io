View 绘制

过度绘制

硬件加速

https://tech.meituan.com/2017/01/19/hardware-accelerate.html

CPU 中央处理器 控制器复杂，ALU较少，逻辑运算

GPU 图像处理器 控制器简单，大量ALU，数学运算

DisplayList：基本绘制元素，绘制命令缓存区

https://blog.csdn.net/luoshengyang/article/details/45943255

RenderNode

invalidate

脏区

不透明view

clipChildren



onMeasure: 自顶向下，每个视图在递归时往下推送尺寸规格。

 ->onLayouet：自动向下

->onDraw



Matrix ：本质上是一个矩阵，用于坐标转换映射。可以缩放，平移，错切，旋转。对矩阵进行操作。

PathMeasure：Path测量工具  https://www.jianshu.com/p/82afb9c2e959