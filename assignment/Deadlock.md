### Lab3: Deadlock分析与实例

1. 实验结果截图              
    ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/lab3/result.jpg) 

2. 死锁条件（理论）                
    1. 资源互斥       
    1. 占有并等待资源
    1. 资源不可剥夺
    1. 循环等待

3. 本次实验死锁分析   
    在A、B两个类的声明中，加入了synchronized进行修饰，该关键字的作用是：当它用来修饰一个方法或者一个代码块的时候，能够保证在同一时刻最多只有一个线程执行该段代码；除此之外，当一个线程访问object的一个synchronized同步代码块或同步方法时，其他线程对object中所有其它synchronized同步代码块或同步方法的访问将被阻塞。  
    本次实验代码的主要运行顺序如下图所示：   
    ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/lab3/source1.jpg)   
    我们可以看到，一般情况下程序按照b
    .method(a)，a.last()，a.method(b)和b.last()的程序执行，这样的话就会依次输出Inside A.last()和Inside B.last()，但是某种情况下，当b
    .method(a)执行而且a.last()还没执行，它拿到了b的synchronized关键字，因此，其他线程不能再去调用b的函数，相当于所有与a相关的函数都不能被指系，此时，如果a.methodB(b)，它也拿到了a的synchronized关键字，之后要执行的程序是a.last()和b.last()，但是很明显，a和b的所有程序已经bei锁住，二者互不相让，都没有办法顺利执行，造成了死锁。
