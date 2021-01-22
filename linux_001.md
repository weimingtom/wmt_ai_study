## ETC  
* search baidupan, GNU_Linux嵌入式快速编程  
* phoneme, https://github.com/weimingtom/Kuuko/blob/master/README2.md#jvmj2me--cldc  

## linux_stm32f7  
* https://github.com/tnishinaga/linux_stm32f7  

## STM32F429I-disco_Buildroot  
* https://github.com/fdu/STM32F429I-disco_Buildroot  

## 嵌入式stm32f429上成功跑通主流Linux 4.13  
* https://blog.csdn.net/farsight1/article/details/79377337  

## linux-0.11-lab  
https://gitee.com/tinylab/linux-0.11-lab  

## 从零使用qemu模拟器搭建arm执行环境  
https://www.cnblogs.com/mfmdaoyou/p/6934098.html

## picore, 树莓派操作系统系统镜像    
http://distro.ibiblio.org/tinycorelinux/ports.html  

## piCore (Tiny Core) Linux on Raspberry Pi  
search 印象笔记  
https://iotbyhvm.ooo/picore-tiny-core-linux-on-raspberry-pi/  
如何扩充树莓派分区  

## 我以前说，研究Linux板（嵌入式Linux）不如研究单片机，  
例如，研究树莓派、v3s、ARM9不如研究rt1052、stm32h750之类。  
那究竟应该怎样研究Linux板才是正道？我思考很很久，我认为有  
这几点，可能是突破这个难题的关键：  
（1）编译问题：完成类似buildroot的目标，但不需要太离谱，  
只要能qemu运行即可
（2）GPIO问题：抽象出操纵GPIO的普遍规律  
（3）framebuffer问题：如何用qemu模拟framebuffer，乃至  
于可以移植嵌入式GUI，乃至于移植游戏，乃至于移植音视频应用  
（4）Android问题：如何简化和编译模拟Android早期版本代码  
库，乃至于添加自定义的功能  
（5）驱动问题：抽象出撰写驱动程序的普遍规律，乃至于操纵  
TFT屏幕与音频输入输出（6）网络和多媒体问题：音视频编解码  
实践
（7）人工智能问题：在qemu中模拟运行人工智能deep learning  
算法
