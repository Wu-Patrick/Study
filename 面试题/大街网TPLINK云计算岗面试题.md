笔试专业课，前面的选择题感觉不是很好做，但是基础的也很多。编程题目：  
1.从一个数变为另一个数需要修改的2进制位数  
2.最大子段和  

1面:自我介绍，介绍完项目经验就叫停，然后开始，技术面：  
###1. 归并排序的模拟 ：   
归并排序的核心在于切分和合并，首先将序列不断切分（二分）直到一组只有一个元素，这里使用到递归，
切分完之后再将元素合并，这里就是收递归的过程，最终将切分的序列再次合并成一个有序的序列。
...
###2.   哪些常用的进程调度算法       
（1）FIFO:先进先出  
（2）最短作业优先调度算法(SCBF--Shortest CPU Burst First)--占用CPU时间片最小（最短任务）的先调度  
（3）时间片轮询调度：按固定时间片公平分给每个进程  
（4）优先级调度：按进程的优先级来调度，这个优先级可以是根据实际需求动态变化的（以免某些进程被饿死的现象）  


###3.  TCP   UDP的区别      滑动窗口   
TCP是基于连接的协议，UDP是非连接性的，TCP是可靠的传输，它提供冲突检测、字节流排序、包重传、滑动窗口、流量控制、拥塞控制等机制，但是相对来说所需的资源成本也比UDP高很多。而默认的UDP是将包发出去就一了百了的  
  
QQ使用的是TCP还是UDP（这个问题自己面过的一个游戏开发被问到过），其实这个问题在网上众说纷纭，我之前也在网上了解过这方面的争论。大部分的观点是说QQ的好友间发送消息的这一功能是使用UDP，毕竟对于QQ这种体量的应用，使用TCP的成本实在负担不起，但QQ采用的是改进版的UDP，也就是在上层应用给这个所谓的UDP添加了一些TCP的功能，比如说丢包检测机制，例如我们用QQ给好友发送消息发送失败时，我们是可以看到QQ上的提示说发送失败的，说明我们的QQ消息有经过腾讯服务器的处理，虽然只是丢包检测并没有自动重传。  

滑动窗口：滑动窗口是TCP传输时的一个缓冲区机制，用来解决传输控制和流量控制的问题，TCP在发送端和接收端都有一个滑动窗口，当接收端成功接收了某段数据并移动了接收窗口的时候，发送端的窗口也会随之移动到缓冲区后面的数据段中。  

###4. 说说哈希的时间复杂度    还有常见的哈希策略     冲突检测策略  
哈希的查找的复杂度为O(1)，也就是常数级别的。因为它使用了数组索引，可快速计算出索引所在的数组下表，进而查找到相应的数据。  
最常见的哈希函数：DJB  
哈希表冲突检测策略：开放寻址发（厕所找位置的比喻）、拉链法（数组链接一条链表）  
###5. 如果CPU时间片过小或者过大会产生什么问题  
CPU时间片过小会导致一些长任务需要很多个周期才能执行完成，也就是需要经过频繁的多次调度，而对于任务的频繁调度室需要耗费资源的。时间片过大又会导致一些小任务本来不需要这么多的时间片，但它也被强制分配到了这么多时间，所以就造成了CPU浪费。所以挑选一个适中的时间片很重要。  

###6.两个数    如何从一个到另一个修改最小的二进制位数         


###7. c语言中static    extern关键字   
static表示静态的意思，static的变量是存放在全局数据区/静态数据区，每次对该变量值得修改都会保留结果，直到程序结束，并且static的变量没有被初始化的话会被自动初始化为0（int），并且只能初始化一遍。同时，static的变量屏蔽了外部链接性，其他文件不被允许访问该static变量。	而普通全局变量（const int i = 10)是具有外部链接性的，其他文件可以通过extern关键字来使用该文件下的这个全局变量。  
参考我的博客：  
[C++ static与extern关键字解析](http://blog.csdn.net/Lv_Victor/article/details/51161698?locationNum=1)
###8.  linux是什么文件系统   
  ext2文件系统