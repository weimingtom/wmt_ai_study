# wmt_ai_study
My AI study  

## TFLite work  
* micro_speech_v7_tf200_single_file.rar  
(ESP32) with Arduino IDE, and Ai-Thinker NodeMCU-32S + INMP441  
(origin) https://github.com/boochow/TFLite_Micro_MicroSpeech_M5Stack  
* micro_speech_v5_tf211_lib.zip  
(ESP32) with Arduino IDE, and Ai-Thinker NodeMCU-32S + INMP441  
(origin) https://github.com/tanakamasayuki/Arduino_TensorFlowLite_ESP32  
(origin) examples/micro_speech_M5StickC/micro_speech_M5StickC.ino  
(origin) with Arduino IDE and M5StickC 2020    
* blink_v2_micro_speech_success.tar.gz  
(ESP32) with esp-idf-v3.3.4, and Ai-Thinker NodeMCU-32S + INMP441  
(origin) from boochow version, TensoFlow Lite Micro 2.0.0, single file compile    
* test_ac5_stm32f411re_vv15_benchmark.rar  
(STM32) with STM32CubeMX, with Keil MDK5 AC5, without C++11, with NUCLEO-F411RE, 84MHz, 1000 times loop, 547 seconds  
(TODO) inline RuntimeShape GetTensorShape(std::vector<int32_t> data)  
(VC2013 version, Windows, 1000 times loop, 61 seconds) micro_speech_vv14_success.rar  
(origin) https://github.com/boochow/TFLite_Micro_MicroSpeech_M5Stack  
(origin, Arduino IDE) search baidupan, TFLite_Micro_MicroSpeech_M5Stack  
(origin, Linux, Raspberry Pi OS Desktop 2017) search baidupan, Blink_esp32_rpd2017_v2_success.tar.gz  
https://github.com/tensorflow/tensorflow/releases/tag/v2.0.0  
search baidupan, tensorflow-2.0.0.zip  
* (TODO) Port to STM32H743  

## ML-KWS work  
* mlkws_stm32f411re_v8_first_success.rar  
(STM32) with STM32CubeMX, Keil MDK5 and NUCLEO-F411RE   
(DONE, SUCCESS, same result as mbed-cli) port to Keil MDK5 AC6 project  
(Dependency, using CMSIS version) search baidupan, CMSIS_5-5.4.0.zip    
https://github.com/ARM-software/CMSIS_5/releases/tag/5.4.0  
small change in CMSIS_5\CMSIS\Core\Include\core_cm4.h  
```
//__FPU_PRESENT=1,
//#warning "Compiler generates FPU instructions for a device without an FPU (check __FPU_PRESENT)"
//#define __FPU_USED       0U
#if !defined(__FPU_PRESENT)
#define __FPU_PRESENT 1
#endif
#define __FPU_USED       1U
```
* simple_test_v3_stm32f411ce_run_success.rar  
(STM32) with mbed-cli and NUCLEO-F411RE   
running output result:    
```
Total time : 164061 us  
Detected right (99%)  
Total time : 164060 us  
Detected right (99%)  
```

## Speech-Recognition Python work  
With Tensorflow 2.x and xubuntu-20.04-desktop-amd64, or with Baidu AIStudio    
Keyword speech recognition   
Speech commands, CNN, 10 words, with xubuntu, run success    
pip3 install tensorflow-cpu (if in AIStudio, use pip and python)  
* (IMP) search baidpan, Speech-Recognition-master_v3_success.tar.gz  
* modified from: https://github.com/iamlekh/Speech-Recognition   
* (TODO, AI Studio) Speech-Recognition-master_v4.tar.gz  

## (TODO, porting difficult) voice_control_led, Maixduino MFCC-DTW + VAD  
* voice_control_led_v9.rar  
(NOT DONE, Many Problems) TODO, with VS2013, windows port, calculate DTW distance get zero, don't know reason    
(TODO, need DOC) about fft, see yinxiangbiji  
* voice_control_led_en_v2_success.rar    
for Maixduino, with Arduino IDE and Sipeed Maix Dock (K210)  
(origin) Maix_Speech_Recognition    
https://github.com/sipeed/Maixduino/blob/master/libraries/Maix_Speech_Recognition  
examples/voice_control_led_en/voice_control_led_en.ino  
examples/get_voice_model/get_voice_model.ino  

## (TODO) migrate to STM32CubeMX MDK5 project, and run      
* https://github.com/gk969/stm32-speech-recognition  
with STM32F103VE and Keil MDK4     

## (TODO, NOT IMP) cortex-m-kws, aid_speech, tengine-lite  
**NOTE**: This demo may be not good,  
because of **lack of training method and model data**，only providing model convert tool    
Details see:   
https://github.com/OAID/cortex-m-kws/blob/master/Documentation/Tengine%20on%20STM32F7%20Setup%20Manual.pdf  
Tengine provides three versions:  
a) https://github.com/OAID/Tengine version (only arm)  
b) http://www.eaidk.com version (EAIDK-310, EAIDK-610)  
c) http://www.tengine.org.cn version (rpi3b, rk3399, hi3516, etc)  
* with STM32F469I-DISCO  
https://github.com/OAID/cortex-m-kws  
https://github.com/OAID/Tengine/tree/tengine-lite  
MCU AI开发者的福音 OPENAILAB发布Tengine-Lite预览版与关键词识别“小智”  
https://zhuanlan.zhihu.com/p/68938575  
https://blog.csdn.net/weixin_43476455/article/details/90401914  
* with NMSIS and RISC-V  
https://gitee.com/Nuclei-Software/NMSIS  
Tengine成功打通RISC-V芯片架构的AI部署与推理，或撼动AI推理格局  
https://zhuanlan.zhihu.com/p/266978046  

## (TODO) KWS_MCU, TC-ResNet8  
https://github.com/Alex-Riviello/KWS_MCU  


## (TODO???) UT2UH/ML-KWS-for-ESP32  
https://github.com/UT2UH/ML-KWS-for-ESP32  
xtensa_copy_q7 ???????where????????  
https://github.com/UT2UH/ML-KWS-for-ESP32/tree/master/Source/XMSIS/NN  

## (TODO) VAD  
* https://github.com/Baidu-AIP/speech-vad-demo  
* https://github.com/LH-YU/SpeechVadDemo  
* https://github.com/wiseman/py-webrtcvad  
* https://github.com/mengsaisi/VAD_campare   


## (TODO) Python GMM Chapter07 speech_recognizer.py  
* origin  
https://github.com/PacktPublishing/Python-Machine-Learning-Cookbook/blob/master/Chapter07/speech_recognizer.py   
* python 2.7 win32 wheel     
search baidupan, Chapter07_win32  
* GMM  
https://github.com/paperrune/GMM/blob/master/main.cpp  
* libMFCC - C library for computing Mel-Frequency Cepstral Coefficients  
https://github.com/jsawruk/libmfcc  
* c_speech_features, A port of python_speech_features to C.  
https://github.com/Cwiiis/c_speech_features  
* cpes, kws_guess  
https://github.com/ruslanbasic/cpes  

