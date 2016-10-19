### Lab2 : DOL 实例分析&编程
1. 修改后得到的截图
    1. example 1
    
        ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/lab%202/example1.JPG)
    2. example 2
    
        ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/lab%202/example2.JPG)

2. 修改过程
    1. example1  
        本次实验的目的是要让example1运行之后使其输出3次方，所以我们的重点应该是在如何输出，其中square.c中对输出有定义：  
        ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/lab%202/source/example1.1.JPG)   
        图中显示，原本的代码是将i进行次方操作后输出，所以我们只需要更改i的操作为进行三次方计算即可，如下图所示：  
        ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/lab%202/source/example1.2.JPG)
    
    2. example2  
        本次实验想要实现的是三个square模块变为两个，在example2.xml中对square模块有定义如下：  
        ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/lab%202/source/example2.1.JPG)  
        因此，我们只需要将其中迭代的次数由3变为2即可，也就是将N的value变为2，如下图所示：  
        ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/lab%202/source/example2.2.JPG)

3. 实验感想
    
    通过本次实验，我了解了example文件中各个文件的含义，其中src文件中包含两种文件：.c文件和对应的.h文件表示实现的模块，也就是.dot文件的框框的功能描述；.xml文件定义了模块与模块间的链接方式，其中process表示有哪些框，connection表示线是如何把框之间联系起来的，通过简单的实验，初步学习了如何看懂代码，为之后深一步的学习打下了基础。




