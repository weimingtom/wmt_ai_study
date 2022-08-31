## 6502  
* https://github.com/search?q=arch_core_6502&type=code  
* https://github.com/search?q=package+free_6502+is&type=code  
* https://github.com/indianabutts/nes_fpga  
* https://github.com/fspada/nes_on_zedboard  
* https://github.com/chenxiao07/vhdl-nes  
* https://github.com/ntaormina/383_FINAL_PROJECT  
* https://github.com/Aerlinger/EmbeddedSysFinalProject  
* https://github.com/drdavros/6502  
* https://github.com/aaroncohen73/Free6502  
* search baidupan, Free6502_v07.ZIP  
* http://www.pldworld.com/_hdl/4/_ip/Free6502/www/  

## Work  
https://github.com/weimingtom/wmt_cpld_study  

## CPU DIY套件TD4 自己动手制作CPU套件(PCB及所有元器件)  
https://github.com/wuxx/TD4-4BIT-CPU  
《自己动手写cpu》和《cpu自制入门》这两本书哪本更通俗易懂？  
https://www.zhihu.com/question/27802570  
《CPU制作法》,渡波 郁著, CPUの創りかた    
https://www.amazon.com/Shi-x304-No-Tsukurikata-Dejitaru/dp/4839909865/ref=sr_1_1?ie=UTF8&qid=1447595397&sr=8-1&keywords=4839909865  
「CPUの創りかた」の4bitCPUをブレッドボードで作りました  
https://qiita.com/y-meguro/items/9ed2a1b772eba4395ea6  
https://github.com/y-meguro/Arduino/tree/master/td4_rom  
https://www.bilibili.com/video/BV1a7411d7uC  
https://hackaday.io/project/26215-td4-cpu  

## TD4, 创元素    
* https://vanya.jp.net/td4/  
* (from taobao, 创元素)  
现在，你看此仿真程序运行图，所需要知道的事情有以下几点：  
红色线代表此时该线上电平为高（5V），蓝色代表电平为低（即0V）  
整个系统由CLOCK脉冲驱动进行，RESET低电平有效，即RESET被拉低后，系统里所有数据清零重启  
如果你已经学过数字电路基础，那么你应该还可以尝试记住并理解以下几点，如果不能或全部理解也没关系，可以全部学完，回来再看看  
四个74HC161分别为寄存器A、B、C、D，分别可用于存储4个比特的数据  
第三个寄存器C的输出，用于输出4位电平，驱动LED  
第四个寄存器D的输出，用作指令的译码，即作为地址总线的A0-A3（Address0-Address3）  
两个74HC153组成了一个4位四路数据选择器，用于选择哪一路的4位数据给后续的四位全加器做加数A。
其中，第三路的4位数据来源于4位拨码开关（即输入），第四路不连接被弃用。  
74HC283是一个四路全加器，它的第一个加数来源于两个74HC153的数据选择通道，  
第二个加数来源于指令数据的低4位（即D3-D0），这种被包含在指令中参与运算的数据又叫立即数immediate。  
全加器的求和结果将输出给4位寄存器A、B、C、D均可，选择其中哪一个寄存器记忆结果，  
完全由每个寄存器输入端的LOAD（~LD）信号决定，请注意LOAD是低电平有效，  
这是后续指令译码结果中控制总线的最重要一部分。
全加器有溢出位输出Carry，但是无法记忆上一次的计算结果是否溢出，  
故需要一个D触发器作为溢出标记位记住上一次的求和结果是否溢出，并送给译码器指令。  
图上所有用门电路表示的组合电路，是一个完整的指令解码器，它由取得指令的高4位（即D7-D4）和  
溢出标记位一起作为译码器的输入，由控制四个寄存器的加载（LD）和两个数据选择器的A、B作为输出，  
这是典型的控制总线。  
* Instruction Set  
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx  
MOV A, im 0011 xxxx  
MOV B, im 0111 xxxx  
MOV A, B  0001 0000  
MOV B, A  0100 0000  
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx  
ADD A, im 0000 xxxx  
ADD B, im 0101 xxxx  
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx  
IN  A,    0010 0000  
IN  B,    0110 0000  
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx  
OUT im    1011 xxxx  
OUT B     1011 0000  
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx  
JMP im    1111 xxxx  
JNC im    1110 xxxx  
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx  

## CPU自制入门  
search baidupan, CPU自制入门  
CPU自作入門-HDLによる論理設計・基板製作・プログラミング  
https://www.amazon.co.jp/CPU自作入門-HDLによる論理設計・基板製作・プログラミング-水頭-一壽/dp/4774153389  

## 自己动手写CPU  
https://github.com/Z-Y00/Examples-in-book-write-your-own-cpu  

## OpenTendo, RP2A03  
https://github.com/Redherring32/OpenTendo  

## mc68020  

## NES on FPGA  
http://pgate1.at-ninja.jp/NES_on_FPGA/index.html  

## TD4 FPGA / Verilog    
* https://github.com/shotamishima/td4fpga  
* https://github.com/myoan/td4  

## td4cpu自制入门, 创元素科技  
知乎讨论与原理教程：  
https://zhuanlan.zhihu.com/p/381501879  
套件焊接视频  
https://www.bilibili.com/video/BV1V341127cf/  
GitHub文档：  
https://github.com/johnsonwust/TD4-4BIT-CPU  

## FreeARM7  
https://github.com/Durant35/Cache-based-on-FreeARM7  
兼容arm9的软核处理器设计：基于fpga(fpga上实现兼容arm9指令集处理器设计的书)  
https://github.com/chsasank/ARM7  
优秀的 Verilog/FPGA开源项目介绍（二十七）-小型CPU  
https://new.qq.com/omn/20220620/20220620A01I0X00.html  

## CPU设计实践教程——从数字电路到计算机组成, minisys-1    
* https://github.com/Ironprop-Stone/Minisys-1_CPU  
* search baidupan, CPU设计实践教程  
* 31条MIPS指令的单周期和多周期Minisys-1 CPU  

## 数字逻辑与组成原理实践教程, cpu31    
* search baidupan, 数字逻辑与组成原理实践教程  
* MIPS CPU 31    

## Digilent, 数字逻辑设计  
* https://github.com/DigilentChina/Digital_Logic_Design_Src  
* https://space.bilibili.com/511019924  

## 自己设计制作CPU与单片机  
* PMC110  
* PMC362  

## MIPS, Digital Design and Computer Architecture  
* 数字设计和计算机体系结构 原书第2版  
* https://textbooks.elsevier.com/web/product_details.aspx?isbn=9780123944245  
* https://booksite.elsevier.com/9780123944245/?ISBN=9780123944245  
* DDCA_Labs_companion.zip, mipsmulti.sv (SystemVerilog)  
* DDCA2e_HDL_03-11-2015.zip, 07-mipssingle, 07-mipsmulti (VHDL and SystemVerilog, .vhd and .sv)    
* mipsfpga  
* https://github.com/MIPSfpga/digital-design-lab-manual  

## MIPSfpga  
* https://github.com/MIPSfpga/schoolMIPS  

## apple2fpga, DE2  
* http://www.cs.columbia.edu/~sedwards/apple2fpga/  

## ben eater  
* https://eater.net  
* benblue6502  
* http://www.benblue.cn  

## 搭建你的数字积木——数字电路与逻辑设计（Verilog HDL&Vivado版）  
* https://github.com/xupsh/Digital-Design-Lab  
* http://www.tup.tsinghua.edu.cn/booksCenter/book_07172301.html  

## XUP官方指定的入门级FPGA教学板卡-Basys3  
* https://www.sytek.ltd/productinfo/1532427.html  

## Risc-v, see digilentchina.taobao.com, Cmod A7-15T      
* SiFive E310  
https://github.com/adafruit/Feather-RISC-V-PCB  
https://sifive.cdn.prismic.io/sifive%2Ffeb6f967-ff96-418f-9af4-a7f3b7fd1dfc_fe310-g000-ds.pdf  
* 蜂鸟 E200  
https://github.com/SI-RISCV/e200_opensource  
https://github.com/riscv-mcu/e203_hbirdv2  
* LowRisc  
https://github.com/lowRISC/lowrisc-chip  
* OpenTitan (Google)  
https://github.com/lowRISC/opentitan  
* Rocket  
https://github.com/lowRISC/rocket  
* Arlane  
https://github.com/lowRISC/ariane  

## 单周期mips, 搭建你的数字积木——数字电路与逻辑设计  
* https://github.com/xupsh/Digital-Design-Lab/tree/master/Chapter_14/RISC  

## OpenHW, XUP (Xilinx University Program)    
* https://openhw.org  
* Resources:  
Xilinx GitHub：http://www.github.com/xilinx  
xupsh GitHub：http://www.github.com/xupsh  
Xilinx Wiki：http://forums.xilinx.com/  
Developer Forum：http://forums.xilinx.com/  
* PYNQ社区  
PYNQ.io：http://pynq.io/  
PYNQ GitHub：http://www.github.com/xilinx/pynq  
PYNQ documentation：http://www.github.com/xilinx/pynq  
PYNQ support forum：https://discuss.pynq.io/  
* Linux Related:  
Xilinx Linux Wiki：http://www.wiki.xilinx.com/  
Xilinx Linux Technical Articles：http://www.wiki.xilinx.com/Technical+Articles  
Zybo Linux Tutorial：http://www.instructables.com/id/Embedded-Linux-Tutorial-Zybo/?ALLSTEPS  
* Xilinx University Program Website :  
http://www.xilinx.com/university  

## openhwgroup, core-v  
* https://github.com/openhwgroup/core-v-verif  
* https://blog.csdn.net/qq_39815222/article/details/109235591  
* core-v RISCV核功能验证工程：https://github.com/openhwgroup/core-v-verif  
core-v 验证策略：https://core-v-docs-verif-strat.readthedocs.io/en/latest/#  
core-v系列核cva6工程：https://github.com/openhwgroup/cva6  
core-v系列核cv32e40p工程：https://github.com/openhwgroup/cv32e40p  
LowRISCV Ibex核工程：https://github.com/lowRISC/ibex  
core-v RISCV核相关说明文档：https://github.com/openhwgroup/core-v-docs  
RISCV ISA指令流（instruction stream）生成器：https://github.com/openhwgroup/force-riscv  
core-v系列指令流（instruction stream）生成器：https://github.com/openhwgroup/core-v-isg  
sail语言介绍：https://www.cl.cam.ac.uk/~pes20/sail/  
REMS的sail RISCV开源项目：https://github.com/rems-project/sail-riscv  

## vivado软核microblaze  
* 用Verilog设计FPGA样机实例解析 Xilinx Spartan-3版  

## basys3  
* https://digilent.com/reference/programmable-logic/basys-3/start  
* https://www.xilinx.com/products/boards-and-kits/1-54wqge.html  
* https://www.sytek.ltd/productinfo/1532427.html  
* https://zhuanlan.zhihu.com/p/339014148?ivk_sa=1024320u  
* https://digilentchina.taobao.com  
* https://github.com/xupgit/Basys3  

## DE0 book  
* 数字电路与EDA实验  

## DE2-115 book  
* FPGA与SOPC设计教程--DE2-115实践  
* DE2-115 实战宝典  

## EP4CE10 book  
* FPGA Verilog开发实战指南：基于Intel Cyclone IV（基础篇)  
