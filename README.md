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


Finally, this page includes topics ranging from hardware components to the Linux kernel. That is a huge range of layers. A one page document can never cover the details of all the layers, so the aim of this document is to serve as a starting point for low-level programming.

## Theory

There are two background theories to low-level programming:
* Computer Architecture
* Operating Systems

You can find many good classes on online universities, for instance, Coursera.org and edx.org.
Theory is theory. I don't think you should get A+ in the class, just understand the big picture in the class.
You'll get better and better with experience.

## Languages

### Assembly

* [8086 assembly programming with emu8086](https://github.com/gurugio/book_assembly_8086)
  * basic concepts of CPU and computer architecture
  * basic concepts of C programming language
* [64bit assembly programming(translation in progress)](https://github.com/gurugio/book_assembly_64bit)
  * basic concepts of modern CPU and computer architecture
  * basic concepts of disassembling and debugging of C code
  * _need help for translation_

### C language

There is no short-cut. Just read the entire book and solve all the exercises.

* [C Programming: A Modern Approach, 2nd Edition](https://www.amazon.com/C-Programming-Modern-Approach-2nd/dp/0393979504)
* [The C Programming Language 2nd Edition](https://www.amazon.com/Programming-Language-Brian-W-Kernighan/dp/0131103628/ref=pd_sbs_14_t_0?_encoding=UTF8&psc=1&refRID=60R1D2CHBA8DHYT6JNMN)
* [Modern C](http://icube-icps.unistra.fr/img_auth.php/d/db/ModernC.pdf)
  * For new standard of C
* [Is Parallel Programming Hard, And, If So, What Can You Do About It?](https://www.kernel.org/pub/linux/kernel/people/paulmck/perfbook/perfbook.html)
  * raw implementation of synchronization with C
  * Essential for large scale C programming (especially for kernel programming)
* [C programming challenge?](https://github.com/gurugio/lowlevelprogramming-university/blob/master/c-language-challenge.md)
  * plan for service like [The Eudyptula Challenge](http://eudyptula-challenge.org/)
  * Just an idea at the moment..
  * If you can make all tiny projects in that page, you would be good to start big projects.

## Applications

### Hardware && Firmware

If you want to be an embedded systems engineer, it would be best to start from a simple hardware kit, rather than starting with the latest ARM chipset.

* [Arduino Start Kit](https://www.arduino.cc/)
  * There are various series of Arduino but "Arduino Start Kit" has the most simple processor(Atmega328P) and guide book
  * Atmega328P has 8bit core that is the good to start "Digital circuit design" and "Firware development".
  * You don't need to know how to draw schematics and layout, and assemble the chips.
  * But you need to know how to read schematics and understand how the chips are connected.
  * Firmware developers should be able to read the schematics and figure out how to send data to the target device.
  * Follow the guide book!
* [8086 manual](https://edge.edx.org/c4x/BITSPilani/EEE231/asset/8086_family_Users_Manual_1_.pdf)
  * If you're a beginner to x86 architecture, 8086 is also very good guide for processor architecture and 80x86 assembly
* [80386 manual](http://css.csail.mit.edu/6.858/2015/readings/i386.pdf)
  * Best guide for protected mode and paging machanism of 80x86 processor
  * Web version: https://pdos.csail.mit.edu/6.828/2011/readings/i386/toc.htm

At this point, you should be good to start the latest ARM or x86 processor.
* https://www.raspberrypi.org/
* https://beagleboard.org/
* https://www.arduino.cc/en/ArduinoCertified/IntelEdison

For example, the Raspberry Pi board has a Cortex-A53 Processor that supports a 64-bit instruction set.
This allows you to experience a modern processor architecture with rPi.
Yes, you can buy it... but... what are you going to do with it?
If you have no target project, you would be likely to throw the board into a drawer and forget it like other gadgets you may have bought before.

So, I recommend one project for you.
* [Making your own kernel](http://wiki.osdev.org/Getting_Started)
  * Good references: https://www.reddit.com/r/osdev/

I've made [a toy kernel](https://github.com/gurugio/caos) that supports 64bit long mode, paging and very simple context switching. Making a toy kernel is good way to understand modern computer architecture and hardware control.

In fact, you have already the latest processor and the latest hardware devices.
Your laptop! Your desktop! You already have all to start!
You don't need to buy anything.
The qemu emulator can emulate the latest ARM processors and Intel processors.
So everything you need is already on hand.
There are so many toy kernel and documents you can refer to.
Just install qemu emulator and make a tiny kernel that just boots and turns on paging, and prints some messages.

Other toy kernels:
* https://littleosbook.github.io/
* https://tuhdo.github.io/os01/

### Linux kernel and device driver

You don't need to make a complete operating system.
Join the Linux community and participate in development.

#### Read carefully

* Books: Read followings in order
  * [The Design of the Unix Operating System](https://www.amazon.com/Design-UNIX-Operating-System/dp/0132017997)
    * The basic concepts of Unix are applied into all operating system.
    * This book is very good to get the concepts of operating system.
  * [Linux Device Drivers](https://www.amazon.com/Linux-Device-Drivers-Jonathan-Corbet/dp/0596005903/ref=sr_1_4?ie=UTF8&qid=1483650712&sr=8-4&keywords=understanding+linux+kernel)
    * Make all examples for yourself
  * [Linux Kernel Development](https://www.amazon.com/Linux-Kernel-Development-Robert-Love/dp/0672329468/ref=sr_1_2?ie=UTF8&qid=1483650712&sr=8-2&keywords=understanding+linux+kernel)
    * Understand the design of Linux Kernel
  * [Understanding the Linux Kernel](https://www.amazon.com/Understanding-Linux-Kernel-Third-Daniel/dp/0596005652/ref=sr_1_1?ie=UTF8&qid=1483650712&sr=8-1&keywords=understanding+linux+kernel)
    * Read this book and the kernel source v2.6 at the same time
    * Never start with the latest version, v2.6 is enough!
    * Use qemu and gdb to run the kernel source line by line
      * http://stackoverflow.com/questions/11408041/how-to-debug-the-linux-kernel-with-gdb-and-qemu
      * https://gurugio.kldp.net/wiki/wiki.php/howto_debug_kernel
    * Use busybox to make the simplest filesystem that takes only 1-second to boot
      * https://gurugio.kldp.net/wiki/wiki.php/qemu_kernel
* [The Eudyptula Challenge](http://eudyptula-challenge.org/)
  * This is like an awesome private teacher who guide you what to do.
  * If you don't know what to do, just start this.
* [Block layer and device driver(translation in progress)](https://github.com/gurugio/book_linuxkernel_blockdrv)
  * start from a simple block device driver example (Ramdisk) with multi-queue mode
  * go forward to block layer
  * _need help for translation_
* [md driver of Linux kernel(in progress)](https://github.com/gurugio/book_linuxkernel_md)
  * how mdadm tool works and how it calls md driver
  * how md driver works
  * _need help for translation_

#### References

Check when you need something

* [Free-electrons homepage](http://free-electrons.com/docs/)
  * many slide files introducing good topics, specially ARM-linux
* [Julia Evans's posting: You can be a kernel hacker!](http://jvns.ca/blog/2014/09/18/you-can-be-a-kernel-hacker/)
  * guide to start kernel programming

## Future of low-level programming

I do not know the future, but I keep my eye on RUST.
* https://hacks.mozilla.org/2016/11/rust-and-the-future-of-systems-programming/

If I could have one week free and alone, I would learn RUST.
That is because RUST is the latest language with which I can develop Linux device driver.

IoT is new trend, so it's worth to check what OSs are for IoT.
ARM, Samsung and some companies has their own realtime OS but sadly many of them are close source.
But Linux Foundation also has a solution: Zephyr
* https://www.zephyrproject.org/

Typical cloud server has so many layers, for instance, host OS, kvm driver, qemu process, guest OS and service application. So container has been developed to provide light virtualization. In near future, a new concept of OS, so-called library OS or Unikernel, would be replace the typical stack of SW for virtualization.
* http://unikernel.org/
