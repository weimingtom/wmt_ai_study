# wmt_ai_study
My AI study  

## TFLite work  
* micro_speech_v7_tf200_single_file.rar  
ESP32, with Arduino IDE, see https://github.com/boochow/TFLite_Micro_MicroSpeech_M5Stack  
* micro_speech_v5_tf211_lib.zip  
ESP32, with Arduino IDE, see https://github.com/tanakamasayuki/Arduino_TensorFlowLite_ESP32  
* blink_v2_micro_speech_success.tar.gz  
ESP32, with esp-idf-v3.3.4  
* (NUCLEO-F411RE, 84MHz, 1000 loop, 547 seconds) test_ac5_stm32f411re_vv15_benchmark.rar  
(vs2013 version, 1000 loop, 61 seconds) micro_speech_vv14_success.rar  
ac5, remove C++11  
(TODO) inline RuntimeShape GetTensorShape(std::vector<int32_t> data)  
(origin) https://github.com/boochow/TFLite_Micro_MicroSpeech_M5Stack  
(origin, arduino ide) search baidupan, TFLite_Micro_MicroSpeech_M5Stack  
(origin, linux) search baidupan, Blink_esp32_rpd2017_v2_success.tar.gz  
https://github.com/tensorflow/tensorflow/releases/tag/v2.0.0  
search baidupan, tensorflow-2.0.0.zip  

## ML-KWS work  
* simple_test_v3_stm32f411ce_run_success.rar  
with mbed-cli, running output result:    
```
Total time : 164061 us  
Detected right (99%)  
Total time : 164060 us  
Detected right (99%)  
```
* mlkws_stm32f411re_v8_first_success.rar  
(done, same result as mbed-cli) port to keil mdk5 ac6 project  
* CMSIS version, search baidupan, CMSIS_5-5.4.0.zip    
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

## Speech-Recognition Python work  
With Tensorflow 2.x and xubuntu-20.04-desktop-amd64, or with Baidu AIStudio    
Keyword speech recognition   
Speech commands, CNN, 10 words, with xubuntu, run success    
pip3 install tensorflow-cpu (if in AIStudio, use pip and python)  
* (IMP) search baidpan, Speech-Recognition-master_v3_success.tar.gz  
* modified from: https://github.com/iamlekh/Speech-Recognition   
* (TODO, AI Studio) Speech-Recognition-master_v4.tar.gz  

## (TODO) voice_control_led, Maixduino VAD DTW  
* voice_control_led_en_v2_success.rar    
for Maixduino, with Arduino IDE  
* voice_control_led_v4.rar  
TODO, with VS2013, windows port    
* fft, see yinxiangbiji  

## (TODO) migrate to STM32CubeMX MDK5 project, and run      
* https://github.com/gk969/stm32-speech-recognition  

## (TODO) cortex-m-kws, aid_speech, tengine-lite  
* with STM32F469I-DISCO  
https://github.com/OAID/cortex-m-kws  
https://github.com/robin-ai-ml/cortex-m-kws  
https://github.com/OAID/Tengine/tree/tengine-lite  

## (TODO) KWS_MCU, TC-ResNet8  
https://github.com/Alex-Riviello/KWS_MCU  
