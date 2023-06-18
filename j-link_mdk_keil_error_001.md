## JLINK 调试报错 JLink Error: Can not read register 解决办法  
* https://blog.csdn.net/langeldep/article/details/78016105  
* https://blog.csdn.net/Yin_w/article/details/130032965  
* 除了这个原因，还可能是stm32cubemx没有设置好jtag/swd, 或者swd的针脚被其他GPIO功能占用了  
* SYS->Debug->Serial Wire  

## 关于DAP-Link在keil中显示RDDI-DAP Error的解决办法以及串口驱动安装及串口下载程序  
* https://blog.csdn.net/SailingNorth/article/details/124899856  

## daplink下载失败，可能是因为接了扩展板接反了，导致某些针脚的电平出问题  

## Invalid ROM Table解决办法 (nucleo??? gd32??? daplink???)  
* https://blog.csdn.net/ninihaoyangde/article/details/126610783  
* because stm32cubemx setup chip clock too high or too low, or setting the clock with code is too high or too low    
```
今天下午在调试程序的时候，下载了一个别人写的程序，忘记修改时钟频率配置，导致STM32F407芯片锁死问题。以下是我解决的办法，亲测很有效，分享给有需要的童鞋们。
原因
出现该现象的原因为板子外部晶振为24M，而程序软件上以8M为输入晶振频率，导致芯片超频锁死，无法连接、下载。
解决方法
在keil里点击魔法棒进入。
Connect选择under Reset.
在Flash Download 中勾选Erase Full  Chip,点击OK，再去重新下载程序，就可以了。
```

