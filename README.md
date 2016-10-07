### DOL安装笔记
1. 安装必要的环境
    - $ sudo apt-get update
    - $ sudo apt-get install ant
    - $ sudo apt-get install openjdk-7-jdk
    - $ sudo apt-get install unzip
2. 下载文件或者将文件从主机拷贝进虚拟机
3. 解压文件
    - 新建dol的文件夹($ mkdir dol)
    - 将dolethz.zip解压到 dol文件夹中($ unzip dol_ethz.zip -d dol)
    - 解压systemc($ tar -zxvf systemc-2.3.1.tgz)
4. 编译systemc
    - 解压后进入systemc-2.3.1的目录下($	cd systemc-2.3.1)
    - 新建一个临时文件夹objdir($ mkdir objdir)
    - 进入该文件夹objdir($ cd objdir)
    - 运行configure($ ../configure CXX=g++ --disable-async-updates)
     
       运行结果如下

        ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/1.jpg)
    - 编译($ sudo make install)          编译完后目录文件如下($ cd ..$ ls)
    
       ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/2.jpg)
    - 记录当前的工作路径($ pwd)
5. 编译dol
    - 进入刚刚dol的文件夹($ cd ../dol)
    - 修改build_zip.xml文件：找到下面这段话
    <property name="systemc.inc" value="YYY/include"/>
    <property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>
    把YYY改成上页pwd的结果（注意，对于  64位 系统的机器，lib-linux要改成lib-linux64）
    - 编译($ ant -f build_zip.xml all)
    若成功会显示build successful，如图

        ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/3.jpg)
    - 可以试试运行第一个例子，进入build/bin/mian路径下($	cd build/bin/main)，
    然后运行第一个例子($ ant -f runexample.xml -Dnumber=1),结果如图
    
        ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/4.jpg)

### DOL框架描述

    分布式操作层（DOL）是一个框架，使应用程序的（半）自动映射到多处理器SHAPES架构平台。劳工部基本上由三部分组成：
    DOL应用程序编程接口： 劳工部定义了一组计算和通信程序，使对形状分布平台，并行应用程序的编程。使用这些程序，应用程序员可以编写程序，而无需了解底层架构的详细知识。事实上，这些程序都受限于硬件相关的软件（HDS）层进一步完善。
    DOL功能仿真： 提供程序员可能性测试其应用程序，功能仿真框架已经形成。除了应用功能验证，这个框架是用来在应用程序级获得的性能参数。
    DOL映射优化： 在DOL映射优化的目标是计算一组应用程序的最佳映射到形状架构平台。在第一步骤中，基于XML规范格式已定义允许以描述一个抽象级别的应用程序和体系结构。尽管如此，所有必要的，以获得准确的性能估计包含信息。
    
### 实验感想&实验心得
1.实验1&实验2

    这两次实验主要是配置环境以及初步熟悉github和markdown语法，通过这两次实验我对dol的框架以及仓库和Markdown的用法有了初步的了解，为之后的进一步学习打下了基础。