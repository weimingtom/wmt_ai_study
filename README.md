# wmt_ai_study
My AI study  

## ESP32, voice recording    
* https://github.com/MhageGH/esp32_SoundRecorder  
* https://github.com/MhageGH/esp32_CloudSpeech  
* https://github.com/lixy123/TTGO_T_Watch_Baidu_Rec  
* https://github.com/atomic14/esp32_audio  

## tensorflow lite micro (tflite) esp32 port  
* ref: https://github.com/tanakamasayuki/Arduino_TensorFlowLite_ESP32/tree/master/examples/micro_speech_M5StickC  
* First NodeMCU-32S and INMP441 breadboard run success  
only use PIN2 (builtin LED) to test YES, no other LED used    
search baidupan, libraries_20201004.rar  
micro_speech_ESP-EYE_v4_success_yes_new_compiler_mianbaoban.rar  
for comparation, micro_speech_M5StickC_v1_compare.rar  
* arduino one file compile: Blink_esp32_v6.rar  
* linux build: Blink_esp32_rpd2017_v2_success.tar.gz  

## tensorflow lite micro (tflite) stm32 / mbed / arm port    
* (TODO) https://github.com/uTensor/tf_microspeech  
* (TODO) https://github.com/COTASPAR/K66F  
* (TODO) https://github.com/ARMmbed/TensorFlow_MIMXRT1064-EVK_Microspeech  
* (TODO) https://github.com/jasonwhwang/tensorflow_micro_speech_mbed/blob/master/micro_speech/audio_provider.cpp  
use A0, MAX9814, see 《Arduino+MAX9814制作简易录音机》  

## TFLite work  
* micro_speech_v7_tf200_single_file.rar  
with Arduino IDE, see https://github.com/boochow/TFLite_Micro_MicroSpeech_M5Stack  
* micro_speech_v5_tf211_lib.zip  
with Arduino IDE, see https://github.com/tanakamasayuki/Arduino_TensorFlowLite_ESP32  
* blink_v2_micro_speech_success.tar.gz  
with esp-idf-v3.3.4  
* freertos_stm32f103rct6_v3_queue.rar  
STM32 CMSIS-FreeRTOS demo    
* freertos_stm32f103rct6_v4_ac6.rar  
STM32 CMSIS-FreeRTOS demo for ac6      
* inmp441_stm32f411re_v2_success_3bit4bit.rar  
stm32f411re inmp441 i2s  
* WM8960_Record_v3_success_inmp441.rar  
stm32f103ze inmp441 i2s  
* WM8960_Record_stm32f103ze_compare.rar  
stm32f103ze inmp441 i2s mod from WM8960_Audio_Board_Code, differences   
* microspeech_stm32f411re_v4_compile.rar  
final stm32 project micro_speech ac6  
* micro_speech_vs2013_success.rar  
win32, vs2013  
* test_ac5_stm32f411re_v6.rar  
ac5, remove C++11  

## ML-KWS work  
* simple_test_v3_stm32f411ce_run_success.rar  
with mbed-cli  
* mlkws_stm32f411re_v4_run_fail.rar  
* mlkws_stm32f411re_v6_fail  
(NOT done) with Keil MDK5, not good    
(TODO) running result is different from mbed version, to be fixed    

## TFLite work TODO    
* (TODO) rpi, SDL2, PortAudio  
* (TODO) port to ESP32 ESP-IDF    
see https://docs.espressif.com/projects/esp-idf/zh_CN/latest/esp32/get-started/index.html  
* (TODO) ADC version (replace i2s, pdm)    
* (TODO) port to other board (STM32, GD32, K210, ...)  
* (TODO) old version of arduino esp32 core  
* (TODO) port to w600: https://docs.w600.fun/?p=product/arduino.md  
* (TODO) port to Wio Terminal  

## ML-KWS, nucleo-f411re    
* ref: https://github.com/ARM-software/ML-KWS-for-MCU/tree/master/Deployment  
* ref: https://github.com/ARM-software/ML-KWS-for-MCU/tree/master/Deployment/Examples/simple_test  
* mbed-cli, search baidupan, kws_simple_test_v1.rar, build result: BUILD_v1.rar  
* for NUCLEO-F411RE, SRAM: 34KB，Flash: 204KB  
* compile method: https://github.com/weimingtom/wmt_ai_study/blob/master/kws_build_001.txt  
* (TODO) https://github.com/2524056672/kws-stm32f7disco-cmsisNN  
* (TODO) https://github.com/JeffyCN/ARM-KWS-demo  
* https://os.mbed.com/users/mbed_official/code/mbed/  
* https://os.mbed.com/users/mbed_official/code/mbed-sdk-tools  
* (TODO) **解决mbed-cli绿色版问题**  
* (TODO) **测试stm32f411ce是否兼容**  
* (DONE) st-link virtual serial, only for NUCLEO-F411RE  
kws_simple_test_v1.rar, simple_test_v2_success.rar    
BUILD_v1.rar  
* (DONE) PA9 PA10 serial (USART1), compatible with stm32f411ce  
simple_test_v3_stm32f411ce_run_success.rar  
BUILD_v3_stm32f411ce_run_success.rar  

```
//UART1_TX==PA_9==D8<->FT232.RXD  
//UART1_RX==PA_10==D2<->FT232.TXD  
serial_init(&stdio_uart, PA_9, PA_10);  //redirect to Serial1  
stdio_uart_inited = 1;   
printf("ready\r\n");  
```  
* (TODO) search baidupan, init template project, blink_v1_stm32f411ce_init.rar  

## speech_commands, tensorflow 1.5.0   
**TODO: 待解决，用i5的电脑开虚拟机已经可以正常安装tf 2.x，但旧电脑好像不行**    
* 命令行参照这篇：  
https://www.cnblogs.com/lijianming180/p/12258774.html    
我不是自己编译tensorflow的，我用的方法是用xubuntu安装python2（就是2.7）  
和python2-pip（需要特殊方法安装pip），然后再离线安装tensorflow 1.5  
（不过依赖包还是在线安装），简单说，就是我利用旧版本来绕过CPU指令集的问题  
（直接安装最新cpu版本，运行是会报错的）。除了安装问题，还有一个问题是训练  
模型的时间非常长，我现在没有彻底跑完整个train.py（我估计要跑一天），我在  
想有没有办法缩短训练数据的时间，或者是否存在断点执行的方法  
* search baidupan, tensorflow-1.5.0-cp27-none-linux_x86_64.whl  
* search baidupan, tensorflow-1.5.0.zip  
* search baidupan, speech_commands_v0.01.tar.gz  
* 安装Python 2和pip2:  
see https://www.cnblogs.com/zhuangliu/archive/2016/11/20/6083063.html  
(???) $ sudo apt-get install python2.7    
$ wget https://bootstrap.pypa.io/get-pip.py  
$ sudo python2 get-pip.py  
$ sudo python2 -m pip install tensorflow-1.5.0-cp27-none-linux_x86_64.whl  
$ python2  
* other study project  
(TODO) https://github.com/accraze/keyword-spotter  
search here, keyword-spotter  

## Tensorflow 2.x, keyword speech recognition    
speech commands, CNN, 10 words, with xubuntu, run success    
* (IMP) search baidpan, Speech-Recognition-master_v3_success.tar.gz  
* modified from: https://github.com/iamlekh/Speech-Recognition   

## (TODO, baidupan) stm32 sound record  
* (TODO, in home computer) stm32f103zet6, Open103Z_I2S, WM8960_Record, WM8960_Audio_Board_Code_v1.rar  
* STM32F4-Discovery_FW_V1.1.0, Audio_playback_and_record, en.stsw-stm32068.zip  
* stm32F4_dsp_microphone_fft_rtos.rar  
* (TODO) STM32F4 i2s/adc/pdm recording code  
* ref https://os.mbed.com/code/  

## (TODO, baidupan) stm32 (and other) sound process  
* STM32F407VG, ASR_Project.rar  
* STM32F407VG, Design_Project-Speech_Recognition_on_Embedded_System.rar  
* k210, m5stickv-tensorflow-lite-micro.rar, maixcube-tensorflow-lite-micro.rar  
* esp32, ML-KWS-for-ESP32.rar  
* STM32F746NG, ml-kws-for-mcu_alxkbr.rar  
* STM32F407VGT6_1, SmartPillow.rar  
* STM32F429ZI, Speaker-Recognition-System-in-ARM.rar, SR_stm32f429zi.rar  
* STM32F407VG, Voice-Recognition.rar  
* mic_vad_streaming, DeepSpeech-examples.rar  
* (TODO) STM32f103VE, stm32-speech-recognition_v2.rar  

## (TODO) migrate to STM32CubeMX MDK5 project, and run      
https://github.com/gk969/stm32-speech-recognition  

