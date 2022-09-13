## 6502  
* https://github.com/search?q=arch_core_6502&type=code  
* https://github.com/search?q=package+free_6502+is&type=code  
* https://github.com/indianabutts/nes_fpga  
* https://github.com/fspada/nes_on_zedboard  
* DE2 NES:  
https://github.com/chenxiao07/vhdl-nes  
* https://github.com/ntaormina/383_FINAL_PROJECT  
* https://github.com/Aerlinger/EmbeddedSysFinalProject  
* bug fix:  
https://github.com/drdavros/6502  
* https://github.com/aaroncohen73/Free6502  
* search baidupan, Free6502_v07.ZIP  
* Free IP, Free6502  
http://www.pldworld.com/_hdl/4/_ip/Free6502/www/  
* 6502 verilog model  
https://c-scape.nl/arlet/fpga/6502/  
https://github.com/Arlet/verilog-6502  
https://github.com/Arlet/verilog-65C02-microcode  
* 6502 dasm  
https://github.com/dasm-assembler/dasm  

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
OUT B     1001 0000  
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx  
JMP im    1111 xxxx  
JNC im    1110 xxxx  
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx  

## CPU自制入门  
search baidupan, CPU自制入门  
CPU自作入門-HDLによる論理設計・基板製作・プログラミング  
https://www.amazon.co.jp/CPU自作入門-HDLによる論理設計・基板製作・プログラミング-水頭-一壽/dp/4774153389  
https://gihyo.jp/book/2012/978-4-7741-5338-4/support#supportDownload  
https://github.com/sabottenda/llvm-sample-target  

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

## 重庆大学, 单周期(single cycle) mips  
* https://github.com/lvyufeng/step_into_mips  
* https://www.bilibili.com/video/BV1pK4y1C7es  

## 74-gate-computer  
* https://github.com/Left-Hand/74-gate-computer  
* https://www.bilibili.com/video/BV1v741117e1  

## picorv32  
* https://github.com/YosysHQ/picorv32  
* http://www.gowinsemi.com.cn/prodshow_view.aspx?TypeId=70&Id=175&FId=t31:70:31  

## 在 Picorv32 / 蜂鸟 E203 软核上运行 RT-Thread  
* https://github.com/wuhanstudio/picorv32_tang  
* https://github.com/wuhanstudio/hbird_e203_tang  

## mister, de10-nano   
* https://github.com/MiSTer-devel/NES_MiSTer  
* https://github.com/strigeus/fpganes  
* https://github.com/MiSTer-devel/Main_MiSTer/wiki  
* https://baijiahao.baidu.com/s?id=1696993695741175252&wfr=spider&for=pc  

## MCU200T开发板  
开发板介绍  
https://www.nucleisys.com/developboard.php#mcu200t  
教学视频  
https://www.rvmcu.com/video.html#cateid43  
蜂鸟HBirdv2 SoC  
https://github.com/riscv-mcu/e203_hbirdv2  
蜂鸟HBird SDK  
https://github.com/riscv-mcu/hbird-sdk  
蜂鸟demo  
https://github.com/Nuclei-Software/nuclei-board-labs/tree/master/e203_hbirdv2/common  
https://github.com/Nuclei-Software/nuclei-board-labs/tree/master/e203_hbirdv2/mcu200t/pwm_led  
蜂鸟社区讨论  
https://www.rvmcu.com/community-show-id-2.html  

## 6502, VHDL应用开发技术与工程实践  
《VHDL应用开发技术与工程实践》一书中提及的6502代码片段（主要是2个vhd文件，我把书中中文换回去原文注释）  
（1）8位总线控制器，锁存data_in：free6502.vhd的The input registers注释  
（2）8位总线控制器，data_out（dout_op由微内码模块提供）：free6502.vhd的Data output logic注释  
（3）sync输出脚：free6502.vhd的The sync output注释  
（4）alu算术逻辑（运算）单元：free6502.vhd的The ALU itself This is purely combinatorial logic注释  
（5）alu运算单元摘录（微内码模块）： microcode.vhd的ALU_OP_rom_arch模块  
（6）用于波形仿真调试的内部寄存器和内部标志寄存器：free6502.vhd的core_65020_debug模块。  
其中书中微内码microcode，现在一般称为微码或者微指令，用于CISC中把指令拆成更简单的指令。  
6502共有56条指令（汇编指令符），13种寻址，实际有151种指令码。  

## stepfpga  
* 大多数MCU软核都是FPGA厂商定制的，比如Altera的Nios II、Xilinx的MicroBlaze和Lattice的MICO32/MICO8  
* FP51-1T MCU Core: A Mustang in FPGA  
https://www.pulserain.com/fp51  
* https://github.com/PulseRain/Mustang  
* https://www.stepfpga.com/doc/fpga项目_使用arduino玩转fpga  
* https://www.stepfpga.com/doc/fpga_arduino_8051  
* https://www.stepfpga.com/doc/fpga_soft_core  
* https://www.stepfpga.com/doc/reindeer_step  
* https://github.com/PulseRain/PulseRain_RISCV_MCU  

## FPGA开发板  
（1）旧教科书里的EPM7128S，大约128  
（2）微雪EPM1270, 常见，大约1k，大概100多  
（3）VHDL应用开发技术与工程实践的EP20K10E-1（6502架构），大约2k  
（4）CPU自制入门的XC3S250E, 不常见，大约5k，大概100多  
（5）正点原子和野火的EP4CE10, 常见，大约10k，大概600多  
（6）可运行NES的DE0，大约15k  
（7）可运行NES的DE1，大约20k  
（8）可运行MIPS的DE2，不常见，大约35k，大概1000以上  
（9）FPGA入门指南的DE10-lite，两款不常见，大约45k到50k，大概1000以上  
（10）basys2, XC3S100E, 2160LUs  
我发现basys2就是XC3S100E，就是我上次说的那本《CPU自制入门》  
里面提到的那个XC3S250E同系列的。。。可惜这太弱了，  
本来XC3S250E就很勉强，100E就更弱了，似乎没有什么收藏的必要  
（11）basys3  
https://zhuanlan.zhihu.com/p/339014148  
https://item.taobao.com/item.htm?id=536711168514  
从Spartan®-3E系列芯片改为Artix-7级别的芯片，  
Basys 3在硬件性能上取得了卓越的提升。  
新的Artix FPGA逻辑单元数量翻了15倍（从2,160到33,280），  
并且从倍增器更新到了真正的DSP切片。RAM的容量也增加了超过26倍。  

## RetroEmbedded/UniversalPPU  
https://github.com/RetroEmbedded/UniversalPPU  

## Redherring32/TinyTendo  
https://github.com/Redherring32/TinyTendo  

## MCL65  
https://github.com/MicroCoreLabs/Projects  
经典重现！基于Spartan-7/3 FPGA实现MOS Technology 6502克隆版   
https://www.sohu.com/a/205787929_292853  

## free6502 EP4CE10 emu work  
* search baidupan, free6502_v4_success.rar, free6502_v4_success  
* 如果需要模拟6502（例如运行free6502软核），需要知道一些VHDL语法（知道怎么传递ROM数据进去软核中运行代码），  
并且了解6502芯片（例如W65C02）的针脚和6502的汇编生成ROM内容的方法。首先说6502针脚，6502无法像现代的单片机  
那样控制针脚的电平，即GPIO，所以很多例子都是用6522或者锁存器去保存D7到D0的数据。简单来说就是，  
6502软核没有ROM、RAM和外设GPIO，而是提供单一地址空间的16个地址脚（RAM和ROM复用）  
和8个数据脚（ROM输入、RAM输入、RAM输出、外设或协处理器输出复用），  
因此RAM和ROM处于相同的地址空间，ROM的起始地址我这里假设为0x1000
* 关于6502的第二个问题是如何执行汇编后的二进制（我这里假设起始地址是0x1000）。你可能会疑惑，  
6502如果跳到0x0地址，那岂不是运行不了？倘若6502可以执行0地址的指令，那么遇到jmp怎么办  
（因为jmp会跳到0x1000以后的地址）。我想了很久恍然大悟，觉得这里设计得太绝妙了，  
因为6502会由于ROM地址线的高4位缺失，导致jmp 0x1000溢出，所以jmp 0x1000和jmp 0x0是等效的，  
所以无论是bootloader跳转还是jmp跳转，都会映射到0x0这个基地址上（12位地址值溢出）。  
同理，当设计ROM时，只需要把汇编后的二进制写入到0x0基地址上就可以了，  
不需要写到0x1000上（自动溢出为0）
* 总体来说free6502有一定的研究价值，不过也有人不用这份代码，而是用verilog重新实现  
（毕竟非常古老了），而且这份代码有一些问题：（1）有没实现的功能  
（2）微码好像是代码生成的（3）缺乏文档说明（4）需要VHDL基础才能自己拼凑出可运行的VHDL代码  
（虽然有一个测试代码）（5）它提供的测试代码跟W65C02的玩法不同，  
W65C02是通过外接协处理器或者锁存器去点灯，所以需要自己手写VHDL代码去实现类似锁存器的功能  
（保存特定内存地址的写入数据），才能模拟出点灯的效果（有些书的模拟做法则是观察内部寄存器A  
的值而非内存的值）  
* http://www.pldworld.com/_hdl/4/_ip/Free6502/www/opcodes.htm  
* www.pldworld.com/_hdl/4/_ip/Free6502/www/  
* 6502 & 6522 Minimal Computer (with Arduino MEGA) Part 2 : 4 Steps - Instructables  
* https://www.instructables.com/6502-6522-Minimal-Computer-With-Arduino-MEGA/  
* https://www.instructables.com/6502-Minimal-Computer-with-Arduino-MEGA/  
* https://github.com/drdavros/6502  

## StepFPGA M10, Mustang, FP51-1T  
* https://github.com/PulseRain/FP51_fast_core  
* https://github.com/PulseRain/PulseRain_FP51_MCU  
* https://www.pulserain.com/m10  
* https://www.stepfpga.com/doc/fpga项目_使用arduino玩转fpga  
* http://sdcc.sourceforge.net  
* git clone -b stepfpga https://github.com/PulseRain/Mustang.git stepfpga  
cd step_fpga  
git submodule update --init --recursive  
* https://www.stepfpga.com/doc/play_fpga_like_arduino_step_test_app  
* 参考资料 (stepfpga）：  
https://www.stepfpga.com/doc/_media/step_fpga_m10_user_guide_cn.pdf  
https://www.stepfpga.com/doc/_media/datasheet_fp8051_1t.pdf  
https://www.stepfpga.com/doc/_media/pulserain_8_bit_mcu_trm.pdf  
https://github.com/PulseRain/Mustang/tree/step_fpga  
https://github.com/PulseRain/Arduino_M10_IDE/tree/step_fpga  
https://github.com/PulseRain/M10_high_speed_config_rtl  
https://github.com/PulseRain  

## TD4 EP4CE10 emu work    
* search baidupan, td4verilog_v1.rar    
* search baidupan, td4vhdl_v1.rar  

## 51单片机的FPGA实现, light52  
https://github.com/jaruiz/light52  
https://www.bilibili.com/video/BV1KJ411C7QX/  
https://github.com/cjhonlyone/light52-ise  
https://github.com/cjhonlyone/picorv32_Xilinx  

## TD4的汇编方法：  
（1）生成二进制的方法：在网页上vanya.jp.net/td4/，  
只支持单指令汇编。另一个命令行版本：  
wuxx/TD4-4BIT-CPU/software/td4as.exe。  
（2）示例代码：（TD-4GP02A）vanya.jp.net/td4/，  
或者参考wuxx/TD4-4BIT-CPU/software/test/test_0_output.s  

## 6502的汇编方法：
（1）生成二进制的方法：用cc65，方法是ca65 test.asm和ld65 -t none test.o  
（如果需要列表文件，可能要da65反汇编或者在ca65中生成，但可能缺少跳转地址）。  
或者用dasm，可能会在头部两字节添加偏移，需要自己去掉，或者生成list文件。  
注意cc65和dasm的伪指令可能不兼容  
（2）示例代码：参考  
www.instructables.com/6502-6522-Minimal-Computer-With-Arduino-MEGA  
和它的前篇（可以把jmp后面的常量改成标号）。  
或者参考free6502的测试汇编  

## 51单片机（8051）的汇编方法：
（1）生成二进制的方法：用Keil C51 uvision2（或者keil 4），A51和L51，待考；  
或者用as31和sdcc（在www.pjrc.com/tech/8051），  
方法是as31 -l -Fbin test.asm。  
或者sdas8051 -l test.asm（需要改成0x表示十六进制常量，但输出二进制可能不正确）。  
asx8051似乎编译失败  
（2）示例代码：stc-isp有IO的汇编示例（不过太长了）；  
或者找《8051 单片机P1口实验》MOV P1；  
或者找这个《Blinking LED using 8051》  
用CPL P1.0取反（只支持P1的位取反，似乎不支持整个P1字节取反）：  
www.circuitstoday.com/blinking-led-using-8051  

## mips的汇编方法（准确说是mips32el）：
（1）生成二进制的方法：用mars生成汇编二进制（参数参考schoolmips）；  
或者用gcc工具链Codescape生成，例如：  
mips-img-elf-as.exe -O0 -EL test.s  
mips-img-elf-objdump -S a.out  
mips-img-elf-objcopy -O binary -j .text a.out a.bin  
（2）示例代码：流水灯代码待考；参考mars的例子（只有一个）；  
参考schoolmips的例子（汇编或者用GCC生成的汇编）  

## mipsfpga sword  
* mips模型机在Sword板子部署在FPGA  
https://www.jianshu.com/p/86e0889755ca  
* https://github.com/FlyGinger/MIPSfpga-on-SWORD  
* http://www.sword.org.cn/courses/digital_logic  
* https://gitee.com/SWORDfpga/ComputerArchitecture/tree/master  

## f32c, risc-v or mips implementation    
* https://github.com/f32c/f32c  
* RISC-V助力SWORD生态系统演进   
* 近日，基于RISC-V指令集的软核CPU在SWORD4.0上顺利移植，给予用户对SWORD4.0的新体验，用户甚至可以通过Arduino IDE开发RISC-V应用。  
在SWORD4.0上移植的是基于RISC-V指令集的F32C开源CPU。CPU通过配置既可以支持RISC-V指令集也可以支持MIPS指令集。  
用户通过对Arduino IDE简单升级，可以使Arduino IDE支持SWORD4.0的RISC-V编译工作。图形化编程环境和大量Arduino范例都有利于用户进行应用开发。  
* https://www.sohu.com/a/272536883_652907  

## mrisc32  
* https://github.com/mrisc32/mrisc32  

## SuperH, J-core  
* https://j-core.org/#get_hardware  
* https://github.com/j-core/jcore-cpu  
