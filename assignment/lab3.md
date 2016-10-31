## lab3.DOL实例分析&编程 ##


分析example的代码，了解各模块功能以及进程实现过程

### 任务1.修改example2使得3个模块变成2个 ###

主要就是修改xml文件中的iterator值，也就是value N的值由3改为1
![](http://i.imgur.com/8JpBmld.png)

修改后dot图：
![](http://i.imgur.com/XLKBlR5.png)

可以看到Square模块变成了两个。

执行结果：

![](http://i.imgur.com/tzXC2fX.png)

### 任务2.修改example1使其输出三次平方 ###

思路：将Squre.c文件中计算部分i=i*i改为i=i*i*i即可。
![](http://i.imgur.com/mZJwwdL.png)

实验效果图：
![](http://i.imgur.com/abVKRDz.png)

### 拓展部分 ###

任务2中将其输出值改为了3次方，因此为了代码的可读性；需要将square文件名改为cubic。由于代码函数名和文件名需要格式统一，而且区分大小写，因此需要阅读所有的代码，将相关部分都修正。

实验效果图：
![](http://i.imgur.com/BSomwRh.png)

### 总结 ###

本次实验主要是研究了各个模块以及代码实现的具体内容。
xml文件中主要就是声明了生产者、消费者、执行模块、信道的个数和所在文件等基本信息。

具体到各个对象中就有相应的.c和.h文件进行进程定义，具体实现功能也都在这里实现。