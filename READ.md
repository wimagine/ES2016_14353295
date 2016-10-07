#README
##Description

The distributed operation layer (DOL) is a framework that enables the (semi-) automatic mapping of applications onto the multiprocessor SHAPES architecture platform. The DOL consists of basically three parts:
## How to install DOL（以ubuntu14.0为例）
### 安装虚拟机和ubuntu：
[VMWARE教程](http://jingyan.baidu.com.artucle/0320e2c1ef9f6c1b87507bf6.html)
[ubuntu下载](http://www.ubuntu.com/download/desktop)
### 配置必要的环境

`$ sudo apt-get update`

`$ sudo apt-get install ant`

`$ sudo apt-get install openjdk-7-jdk`

`$ sudo apt-get install unzip`
###下载文件：

`$ sudo wget http://www.accellera.org/images/downloads/stanards/systemc-2.3.1.tgz`

`sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip`
### 解压文件

新建dol文件夹：`$ mkdir dol`

将dolethz.zip解压到dol文件夹中： `$ unzip dol_ethz.zip -d dol`

解压systemc: `$ tar -zxvf systemc-2.3.1.tgz`

###编译systemc:

解压后进入systemc-2.3.1的目录下 `$cd systemc-2.3.1`

新建一个临时文件夹： `$ mkdir objdir`

进入文件夹： `$ cd objdir`

运行configure: `$ ../configure CXX=g++ --disable-async-updates`

效果如图;

![00](C:\Users\wimagine\Desktop\dol\000.png)

编译：`$ sudo make install`

编译后文件目录如下： `$cd .. $ ls`)

![01](C:\Users\wimagine\Desktop\dol\001.png)

记录当前的工作路径： `$ pwd`
### 编译dol:

进入刚刚dol的文件夹： `$ cd ../dol`

修改build_zip.xml文件，找到下面这段说明systemc位置的语句：

`<property name="systemc.inc"value="YYY/include"/>`

`<property name="systemc.lib"value="YYY/lib-linux/libsystemc.a"/>`

把YYY改成上页pwd的结果。

编译：`$ ant -f build_zip.xml all` 编译成功则显示 build successful

接着运行第一个例子，先进入build/bin/main路径，然后运行: `$ ant -f runexample.xml -Dnumber=1`

成功后如图：

![02](C:\Users\wimagine\Desktop\dol\002.png)
##Experimental experience
安装dol和github仓库的实验主要是熟悉了相关的linux语句。刚开始尝试装ubuntu15.0但由于到最后一步测试样例时不成功，所以选择装14.0版本，比较顺畅。
同时学习使用了markpad编写.md文档，好像保存的时候不支持覆盖已有的文档，所以导致我写好的文档就莫名其妙丢失了，保存最好还是新建一个问价。

