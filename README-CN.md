# 底层编程大学

## 这是什么?

这个项目为初学者提供一种学习路径,告诉初学者如何成为底层程序员.

作者是受[Google面试大学](https://github.com/jwasham/google-interview-university)的启发,作者会分享一些自己的经验,并提供一个学习的路径图(Roadmap),因为作者发现,随着技术的进步,成为一个底层程序员已经不像之前那么简单了.另外,很多学生和初学者都会反复的问我,如何成为底层程序员和Linux内核工程师.

作为底层程序员,我拥有10年的经验:
* 80x86 汇编
* 硬件设备与Atmel芯片和固件
* Unix系统下的C语言编程
* Linux设备驱动程序
* Linux内核:页面分配
* Linux内核:块设备驱动和md模块


## 什么是底层编程?

我将底层编程定义为,使用底层编程语言,例如C语言或汇编进行更加靠近机器的编程.这个是与高级别编程语言对比而言的,通常是用户层面的应用程序,也一般会采用高级别的编程语言,比喻说,Python,Java.

* [Wikipedia: 底层编程语言](https://en.wikipedia.org/wiki/Low-level_programming_language)

同时注意到,系统编程与底层编程语言很相似,该页面包括系统编程中未包含的硬件设计和固件开发。

* [Wikipedia: 系统编程](https://en.wikipedia.org/wiki/System_programming)

最后，此页面包括从硬件组件到Linux内核的主题。 这是一个非常大的范围,一页文档永远不会覆盖所有层的细节，因此本文档的目的是作为低级编程的起点。

## 理论基础

底层编程需要2个基础的背景知识:

* 计算机体系结构
* 操作系统

你可以在很多的在线大学找到很多好的学习课程,下面是一个可以参考的列表,Coursera.org,edx.org.
理论归理论.我并不喜欢在你在课程中获得A+,但是理解这个课程的大框是有意义的,在实际的项目中做一些东西,你会变得越来越好的.

## 语言

### 汇编

* [8086汇编编程与emu8086](https://github.com/gurugio/book_assembly_8086)
  * CPU和计算机体系结构的基本概念
  * C编程语言的基本概念
* [64bit汇编编程(translation in progress)](https://github.com/gurugio/book_assembly_64bit)
  * 现代CPU和计算机架构的基本概念
  * C代码的拆解和调试的基本概念
  * _need help for translation_

### C语言

没有捷径。 只需阅读整本书并解决所有的练习

* [C Programming: A Modern Approach, 2nd Edition](https://www.amazon.com/C-Programming-Modern-Approach-2nd/dp/0393979504)
* [The C Programming Language 2nd Edition](https://www.amazon.com/Programming-Language-Brian-W-Kernighan/dp/0131103628/ref=pd_sbs_14_t_0?_encoding=UTF8&psc=1&refRID=60R1D2CHBA8DHYT6JNMN)
* [Modern C](http://icube-icps.unistra.fr/img_auth.php/d/db/ModernC.pdf)
  * 对于C的新标准
* [Is Parallel Programming Hard, And, If So, What Can You Do About It?](https://www.kernel.org/pub/linux/kernel/people/paulmck/perfbook/perfbook.html)
  * 原始实现与C同步
  * 大规模C编程（特别是内核编程）的基本要素
* [C programming challenge?](https://github.com/gurugio/lowlevelprogramming-university/blob/master/c-language-challenge.md)
  * 计划做成类似 [The Eudyptula Challenge](http://eudyptula-challenge.org/)
  * 目前还仅仅是个想法..
  * 如果您可以在该页面中进行所有小项目，那么您将很乐意启动大型项目。

## 应用程序

### 硬件＆固件

如果你想成为一名嵌入式系统工程师,最好是从一个简单的硬件开始,而不是从一个最新的ARM硬件.

* [Arduino Start Kit](https://www.arduino.cc/)
  * 有各种系列的Arduino，但“Arduino Start Kit”具有最简单的处理器（Atmega328P）和指导书  
  * Atmega328P具有8位内核，是开始“数字电路设计”和“Firware开发”的好选择。
  * 您不需要知道如何绘制原理图和布局，并组装芯片。
  * 但是您需要知道如何阅读原理图并了解芯片的连接方式。
  * 固件开发人员应该能够阅读原理图，并找出如何将数据发送到目标设备。
  * 按照指导书！
   
* [8086 manual](https://edge.edx.org/c4x/BITSPilani/EEE231/asset/8086_family_Users_Manual_1_.pdf)
  * 如果您是x86架构的初学者，8086也是处理器架构和80x86程序集的非常好的指南
* [80386 manual](http://css.csail.mit.edu/6.858/2015/readings/i386.pdf)
  * 80x86处理器的保护模式和分页机制的最佳指南
  * Web版本: https://pdos.csail.mit.edu/6.828/2011/readings/i386/toc.htm

完成以上的这些,您应该很乐意启动最新的ARM或x86处理器了

* https://www.raspberrypi.org/
* https://beagleboard.org/
* https://www.arduino.cc/en/ArduinoCertified/IntelEdison

例如，Raspberry Pi板具有支持64位指令集的Cortex-A53处理器。
这允许您体验具有rPi的现代处理器架构。
是的，你可以买它，但是你要怎么做？
如果您没有目标项目，您可能会将该板放入抽屉中，并将其忘记为您之前购买过的其他小工具。

所以，我为你推荐一个项目。
* [制作自己的内核](http://wiki.osdev.org/Getting_Started)
  * 参考案例: https://www.reddit.com/r/osdev/

我制作了一个支持64位长模式，分页和非常简单的上下文切换的[玩具内核]（https://github.com/gurugio/caos）。 制作玩具内核是了解现代计算机架构和硬件控制的好方法。

实际上，您已经有最新的处理器和最新的硬件设备。
你的笔记本电脑！ 你的桌面！ 你已经有了所有的开始！
你不需要买任何东西。
qemu仿真器可以模拟最新的ARM处理器和Intel处理器。
所以你需要的一切已经在手。
有很多玩具内核和文件可以参考。
只需安装qemu模拟器，并制作一个小型内核，只需启动并打开分页，并打印一些消息。

其他的玩具内核:
* https://littleosbook.github.io/
* https://tuhdo.github.io/os01/

### Linux内核和设备驱动

您不需要制作完整的操作系统。
加入Linux社区并参与开发。

#### 仔细阅读

* 参考资料: 请按顺序阅读
  * [The Design of the Unix Operating System](https://www.amazon.com/Design-UNIX-Operating-System/dp/0132017997)
    * Unix的基本概念适用于所有操作系统.
    * 这本书很好的得到了操作系统的概念.
  * [Linux Device Drivers](https://www.amazon.com/Linux-Device-Drivers-Jonathan-Corbet/dp/0596005903/ref=sr_1_4?ie=UTF8&qid=1483650712&sr=8-4&keywords=understanding+linux+kernel)
    * Make all examples for yourself
  * [Linux Kernel Development](https://www.amazon.com/Linux-Kernel-Development-Robert-Love/dp/0672329468/ref=sr_1_2?ie=UTF8&qid=1483650712&sr=8-2&keywords=understanding+linux+kernel)
    * 了解Linux内核的设计
  * [Understanding the Linux Kernel](https://www.amazon.com/Understanding-Linux-Kernel-Third-Daniel/dp/0596005652/ref=sr_1_1?ie=UTF8&qid=1483650712&sr=8-1&keywords=understanding+linux+kernel)
    * 同时阅读本书和内核源码v2.6
    * 不要从最新版本开始，v2.6就够了！
    * 使用qemu和gdb逐行运行内核源代码
      * http://stackoverflow.com/questions/11408041/how-to-debug-the-linux-kernel-with-gdb-and-qemu
      * https://gurugio.kldp.net/wiki/wiki.php/howto_debug_kernel
    * 使用busybox来做最简单的文件系统，只需要1秒钟即可引导
      * https://gurugio.kldp.net/wiki/wiki.php/qemu_kernel
* [The Eudyptula Challenge](http://eudyptula-challenge.org/)
  * 这就像一个非常棒的私人老师，指导你做什么。
  * 如果你不知道该怎么做，那就开始吧。
* [Block layer and device driver(translation in progress)](https://github.com/gurugio/book_linuxkernel_blockdrv)
  * 从具有多队列模式的简单块设备驱动程序示例（Ramdisk）开始
  * 前进到阻止(block)层
  * _need help for translation_
* [md driver of Linux kernel(in progress)](https://github.com/gurugio/book_linuxkernel_md)
  * mdadm工具如何工作以及如何调用md驱动程序
  * md驱动程序的工作原理
  * _need help for translation_

#### 参考文献

如果你需要一些支持的时候,你可以查阅下面的资料

* [Free-electrons homepage](http://free-electrons.com/docs/)
  * 许多幻灯片文件引入了很好的话题，特别是ARM-linux
* [Julia Evans's posting: You can be a kernel hacker!](http://jvns.ca/blog/2014/09/18/you-can-be-a-kernel-hacker/)
  * 指导启动内核编程

## 未来的底层编程

我不知道未来，但我注意到了RUST.
* https://hacks.mozilla.org/2016/11/rust-and-the-future-of-systems-programming/

如果我有一个星期的时间可以独自一人，我会学习RUST.
这是因为RUST是我可以开发Linux设备驱动程序的最新语言.

IoT是新的趋势，所以值得检查什么操作系统支持IoT.
ARM，三星和一些公司都有自己的实时操作系统，但很遗憾，其中很多都是闭源.
但Linux基金会也有一个解决方案: Zephyr
* https://www.zephyrproject.org/

典型的云服务器有很多层次，例如主机操作系统，kvm驱动程序，qemu进程，客户操作系统和服务应用程序。 因此，容器已经开发出来提供轻型虚拟化。 在不久的将来，一个新的操作系统概念，即所谓的库OS或Unikernel，将替代典型的SW虚拟堆栈.
* http://unikernel.org/
