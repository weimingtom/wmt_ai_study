# wmt_ai_study
My AI study  
```
弃身锋刃端，性命安可怀？父母且不顾，何言子与妻！  
名编壮士籍，不得中顾私。捐躯赴国难，视死忽如归！  
——曹植《白马篇》  
```

## Recorder code work  
see https://github.com/weimingtom/wmt_recorder_study  

## Wireless code work  
see https://github.com/weimingtom/wmt_iot_study  

## TFLite work  
* test_ac5_stm32f411re_vv15_benchmark.rar  
(STM32) with STM32CubeMX, with Keil MDK5 AC5, without C++11, with NUCLEO-F411RE, 84MHz, 1000 times loop, 547 seconds  
(stm32cubemx) Heap_Size==0x13000, Stack_Size==0x6000      
(TODO) inline RuntimeShape GetTensorShape(std::vector<int32_t> data)  
(VC2013 version, Windows, 1000 times loop, 61 seconds) micro_speech_vv14_success.rar  
(origin) https://github.com/boochow/TFLite_Micro_MicroSpeech_M5Stack  
(origin, Arduino IDE) search baidupan, TFLite_Micro_MicroSpeech_M5Stack  
(origin, Linux, Raspberry Pi OS Desktop 2017) search baidupan, Blink_esp32_rpd2017_v2_success.tar.gz  
https://github.com/tensorflow/tensorflow/releases/tag/v2.0.0  
https://github.com/tensorflow/tensorflow/tree/v2.0.0/tensorflow/lite/experimental/micro/examples/micro_speech  
https://github.com/tensorflow/tensorflow/tree/master/tensorflow/lite/micro/examples/micro_speech  
search baidupan, tensorflow-2.0.0.zip  
* (TODO) Port to STM32H743  
(TODO, NOT DONE) microspeech_stm32h743vi_v7_no_crash_with_lib.rar  
(TODO, NOT DONE, inmp441 stm32h743 test) test_ac6_stm32h743vi_v2_dma_bug.rar  
DMA is not working on STM32H7 devices  
https://community.st.com/s/article/FAQ-DMA-is-not-working-on-STM32H7-devices  
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
* (TODO) https://gitee.com/tutuwin/xr872_-audio  
https://gitee.com/tutuwin/xr872_-audio/blob/master/audio_record.c  
model_process  

## TFLite micro esp32, MSM261S4030H0R    
* search baidupan, tflite-micro-esp-examples-master_v2_test_esp32_one_success.rar  
* (TODO) https://github.com/espressif/tflite-micro-esp-examples  
https://github.com/espressif/esp-nn  
https://github.com/dhdhxji/ESP32-LyraT-tf_command-recognition  
* (TODO) https://github.com/tensorflow/tflite-micro-arduino-examples  
* (TODO) https://github.com/tensorflow/tflite-micro  
https://github.com/tensorflow/tflite-micro/tree/main/third_party/xtensa/examples/micro_speech_lstm  
* https://github.com/eloquentarduino/EloquentTinyML  
* https://github.com/tanakamasayuki/Arduino_TensorFlowLite_ESP32  
* https://github.com/edgeimpulse/tflite-micro-esp-examples/tree/master/examples/micro_speech  

## (TODO) TFLite micro ARM, NXP MIMXRT1050-EVKB or Arm虚拟硬件(AVH)    
* https://github.com/ARM-software/AVH-TFLmicrospeech  

## TinyML: 基于TensorFlow Lite在Arduino和超低功耗微控制器上部署机器学习  
* TinyML: Machine Learning with TensorFlow Lite on Arduino and Ultra-Low-Power Microcontrollers  
* https://www.oreilly.com/library/view/tinyml/9781492052036/  
* https://github.com/tensorflow/tflite-micro  

## ML-KWS work  
* mlkws_stm32f411re_v8_first_success.rar  
(STM32) with STM32CubeMX, Keil MDK5 AC6 and NUCLEO-F411RE   
(stm32cubemx) Heap_Size==0x12000, Stack_Size==0x6000      
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
《嵌入式系统案例教程》第3章FPU，硬浮点和__FPU_PRESENT和__FPU_USED，在system_stm32f4xx.c，  
需要全局定义__FPU_PRESENT和__FPU_USED，  
见void SystemInit(void)函数。在stm32f429xx.h中有__FPU_PRESENT=1的宏定义，  
或者在Keil 5的Floating Point Hardware中选择Use Single Precision  
会产生__FPU_USED=1的宏定义    
stm32f429属于Cortex-M4F架构，所以有FPU  
* simple_test_v3_stm32f411ce_run_success.rar  
(STM32) with mbed-cli and NUCLEO-F411RE   
(origin) https://github.com/ARM-software/ML-KWS-for-MCU/tree/master/Deployment  
running output result:    
```
Total time : 164061 us  
Detected right (99%)  
Total time : 164060 us  
Detected right (99%)  
```  
* NEW Keyword spotting for Microcontrollers   
https://github.com/ARM-software/ML-examples  
https://github.com/ARM-software/ML-examples/tree/master/tflu-kws-cortex-m  

## Speech-Recognition Python work  
* https://github.com/weimingtom/Speech-Recognition_mod  
work  
* Speech-Recognition-master_v3_success.tar.gz  
(Python3, TF2) With Tensorflow 2.x and xubuntu-20.04-desktop-amd64  
Keyword speech recognition, Speech commands, CNN, 10 words  
(install tf2) pip3 install tensorflow-cpu (if in xubuntu, use pip3 and python3)  
(origin) https://github.com/iamlekh/Speech-Recognition   
* Speech-Recognition_v7.tar.gz  
(Python3, TF2) with AI Studio, not done    
(install tf2) pip install tensorflow-cpu (if in AIStudio, use pip and python)  

## (TODO, porting difficult) voice_control_led, Maixduino MFCC-DTW + VAD (stm32-speech-recognition like)    
* voice_control_led_v9.rar  
(NOT DONE, Many Problems) TODO, with VS2013, windows port, calculate DTW distance get zero, don't know reason    
(TODO, need DOC) about fft, see yinxiangbiji  
* voice_control_led_en_v2_success.rar    
for Maixduino, with Arduino IDE and Sipeed Maix Dock (K210)  
(origin) Maix_Speech_Recognition    
https://github.com/sipeed/Maixduino/blob/master/libraries/Maix_Speech_Recognition  
examples/voice_control_led_en/voice_control_led_en.ino  
examples/get_voice_model/get_voice_model.ino  

## (TODO) stm32-speech-recognition, STM32 MFCC-DTW + VAD  
* stm32-speech-recognition_v3.rar  
(origin) https://github.com/gk969/stm32-speech-recognition    
(origin) with STM32F103VE and Keil MDK4 
* (TODO) migrate to STM32CubeMX MDK5 project, and run     

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
* https://github.com/jjzhang166/aicontroler/blob/master/aicontroler/src/record.c  
* https://github.com/bekencorp/bk7251_rtt_audio_sdk/blob/master/beken378/func/vad/vad_core.c  

## (TODO) Python GMM Chapter07 speech_recognizer.py  
* origin  
https://github.com/PacktPublishing/Python-Machine-Learning-Cookbook/blob/master/Chapter07/speech_recognizer.py   
* python 2.7 win32 wheel     
(**IMP**) search baidupan, Chapter07_win32  
* GMM  
https://github.com/paperrune/GMM/blob/master/main.cpp  
* libMFCC - C library for computing Mel-Frequency Cepstral Coefficients  
https://github.com/jsawruk/libmfcc  
* c_speech_features, A port of python_speech_features to C.  
https://github.com/Cwiiis/c_speech_features  
* cpes, kws_guess  
https://github.com/ruslanbasic/cpes  

## (TODO) html5, MFCC-DTW    
* speech_v1.rar  
index.html, harker.emit('speaking'), console.log('speaking');  
with USB microphone and Chrome/Opera      
(origin) https://github.com/MimusTriurus/WebExperiments  
(origin) https://github.com/shawkatq/voice-commands-demo  

## (TODO) micro_speech (TFLM 2.0) train  
* https://github.com/tensorflow/tensorflow/tree/r2.0/tensorflow/lite/experimental/micro/examples/micro_speech#use-your-local-machine  
* https://github.com/tensorflow/docs/blob/master/site/en/r1/tutorials/sequences/audio_recognition.md  
* https://github.com/tensorflow/tensorflow/blob/r2.0/tensorflow/lite/experimental/micro/examples/micro_speech/train_speech_model.ipynb  
* https://github.com/tensorflow/examples/tree/master/lite/examples/speech_commands/ml  
* https://www.cnblogs.com/lijianming180/p/12258774.html  

## (TODO) TensorFlow入门教程(17)语音识别  
search baidupan, 17.speech_recognition.zip  
TensorFlow入门教程(17)语音识别(上)  
https://blog.csdn.net/rookie_wei/article/details/84527839  

## (TODO) diy-alexa, voice-controlled-robot, ESP32    
https://github.com/atomic14/diy-alexa  
Voice-Controlled Robot With the ESP32  
https://github.com/atomic14/voice-controlled-robot  

## (TODO) MACE Micro Examples  
* classifier_mace_v2_xubuntu_host.tar.gz  
(demo) for x86 linux xubuntu  
(origin) MICRO_MODEL_NAME=mnist, MICRO_DATA_NAME=mnist  
https://github.com/XiaoMi/mace/blob/master/micro/examples/classifier/main.cc  
https://github.com/XiaoMi/mace/blob/master/micro/examples/classifier/data.h  
https://github.com/XiaoMi/mace/blob/master/docs/micro-controllers/basic_usage.rst  
see 'Use libraries directly'    
* (TODO) MICRO_MODEL_NAME=kws, MICRO_DATA_NAME=kws  
https://github.com/XiaoMi/mace/blob/master/docs/micro-controllers/deploy.rst  
* classifier_vs2013_v1.rar  
(demo) for vs2013, windows    
* some sites  
https://github.com/weimingtom/wmt_ai_study/blob/master/mace_001.txt  

## (TODO) hyperconnect/TC-ResNet  
https://github.com/hyperconnect/TC-ResNet  
https://github.com/hyperconnect/TC-ResNet/blob/master/tflite_tools/run_benchmark.sh  
https://github.com/tranHieuDev23/TC-ResNet  
https://github.com/jianvora/Continual_Learning_for_KWS    
https://github.com/olimjon-ibragimov/TC-ResNet-TensorFlow-2  

## (TODO) pytorch speech command tutorial  
https://github.com/pytorch/tutorials/blob/master/intermediate_source/speech_command_recognition_with_torchaudio.py  
https://pytorch.org/tutorials/intermediate/speech_command_recognition_with_torchaudio.html  
(TODO) kws_game  
https://github.com/chrisworld/kws_game  

## (TODO) tflite python  
TensorFlow Lite Tutorial Part 3: Speech Recognition on Raspberry Pi  
https://www.digikey.com/en/maker/projects/tensorflow-lite-tutorial-part-3-speech-recognition-on-raspberry-pi/8a2dc7d8a9a947b4a953d37d3b271c71  
TensorFlow Lite Speech Recognition Demo  
https://github.com/ShawnHymel/tflite-speech-recognition  
【TensorFlow】Raspberry Piへのインストール方法3選  
https://www.sejuku.net/blog/47178  
TensorFlow Lite Python  
https://tensorflow.google.cn/lite/guide/python  
How to Run TensorFlow Lite Models on Raspberry Pi  
https://blog.paperspace.com/tensorflow-lite-raspberry-pi/  

## (TODO) pico-wake-word  
https://github.com/henriwoodcock/pico-wake-word  
https://www.adafruit.com/product/1063  
MAX4466 (like MAX9814???)  
search baidupan, pico-wake-word-main.zip  
tensorflow 2.4.1, 2021-03-31  

## (TODO) pytorch CRNN (???)    
https://github.com/isadrtdinov/kws-attention  

## (TODO???) Edge Impulse, Recognize sounds from audio  
https://docs.edgeimpulse.com/docs/audio-classification  
http://www.elecfans.com/d/1532483.html  
seeedstudio wio terminal tinyml  
https://wiki.seeedstudio.com/Wio-Terminal-TinyML-EI-1/  
https://wiki.seeedstudio.com/Wio-Terminal-TinyML-EI-3/  

## pico-microphone, Raspberry Pi Pico  
* https://github.com/sandeepmistry/pico-microphone  
https://github.com/raspberrypi/pico-sdk  
https://github.com/raspberrypi/pico-examples  
* hello_analog_microphone, ADC麦克风, using max4466（带直流分量, 512附近）和max9814（过滤直流，0附近, Gain接VCC最小增益）  
* hello_pdm_microphone, PDM麦克风, using M5stack PDM mini Unit (SPM1423HM4H-B)    
https://docs.m5stack.com/zh_CN/unit/pdm  
```
while (1) {
	// store and clear the samples read from the callback
	int sample_count = samples_read;
	samples_read = 0;

	// loop through any new collected samples
	int maxValue = 0;
	for (int i = 0; i < sample_count; i++) { //or min(sample_count, 5)
		int value = sample_buffer[i];
		if (fabs(value) > fabs(maxValue)) {
			maxValue = value;
		}
	}
	//if M5stack PDM  
	printf("%d,%d,%d\n", maxValue / 128, -256, 256);
	//if max9814
	//printf("%d,%d,%d\n", maxValue, -512, 512);
	sleep_ms(50);
}
```
* hello_pdm_microphone, using MP34DT01 PDM MEMS Microphone<->Rpi Pico, why this ok? see below:   
(self) 3V<-> (self) SEL  
GND<-> GND  
* hello_analog_microphone, use MAX9814, for 3.3V and 5V  
* hello_analog_microphone, use MAX9813H, for 5V only  
* hello_analog_microphone, use MAX9812L, for 3.3V only, not good, go stable slowly  

## (IMP, TODO) **Edge Impulse, tensorflow 2.3**    
* linux, xubuntu200464    
example-standalone-inferencing-master_v1.tar.gz  
* windows, vs2013  
helloei_v3_success.rar  

## 画了个V3S，慢更语音助手（LUCKY）
https://whycan.com/t_7000.html  
记录自制linux的过程（基于全志V3s）  
https://blog.csdn.net/qq_46604211/article/details/116024970  
https://github.com/dakun-create/voice-assistant-byV3S  

## (???) NVIDIA NeMo  
https://docs.nvidia.com/deeplearning/nemo/user-guide/docs/en/stable/starthere/tutorials.html  

## (TODO) Speech commands recognition with PyTorch | Kaggle 10th place solution in TensorFlow Speech Recognition Challenge  
https://github.com/tugstugi/pytorch-speech-commands  

## (TODO) [深度学习进阶 - 实操笔记] 语音识别基础  
https://blog.csdn.net/weixin_41809530/article/details/106585116  
[深度学习进阶 - 实操笔记] 语音识别SPEECH_COMMANDS数据集  
https://www.freesion.com/article/5523850245/  
https://blog.csdn.net/weixin_41809530/article/details/106585116  
https://blog.csdn.net/weixin_41809530/article/details/106669728  

## (TODO) Offline Speech Recognition on Raspberry Pi 4 with Respeaker  
https://github.com/AIWintermuteAI/DeepSpeech_RaspberryPi4_Hotword  
https://www.hackster.io/dmitrywat/offline-speech-recognition-on-raspberry-pi-4-with-respeaker-c537e7  

## (IMP) esp32 dsp (with asm)  
https://github.com/espressif/esp-dsp  

## (???) Python, sipeed MaixPy, maix-asr, (speech_recognizer)    
https://blog.csdn.net/xuguoliang757/article/details/118462079  
https://github.com/sipeed/MaixPy_scripts/blob/master/multimedia/speech_recognizer/maix_asr_2900k_0x500000.kmodel  
https://bbs.sipeed.com/thread/988  

## (IMP, TODO) TensorFlow语音识别实战      
* search book_TensorFlow语音识别实战  
* search baidupan, TensorFlow语音识别实战-源代码.7z    
* 第十章——基于MFCC和CTC的语音汉字转换  
* 第一章——语音识别之路, 1.7 实战——基于特征词的语音唤醒  
* 这本书的原创代码较多，可以研究  
* tensorflow-gpu==2.1.0  

## (TODO) 以前用树莓派3b运行deepspeech和vosk的备份  
* 除了Sphinx外，在树莓派上可以运行的较完整的离线语音识别引擎有deepspeech和vosk  
search work_deepspeech_vosk_raspberry_pi_upload  
search deepspeech_readme.txt    
* （可能）新的选择：openai-whisper  
我试过可以在python 3.7下运行（openai-whisper最旧版本），需要ffmpeg，  
但仅限于PC，没有在树莓派上测试，模型文件较小，但识别英文单词时间可能需要30秒以上      
* 较快的whisper推理版：whisper.cpp  
https://github.com/ggerganov/whisper.cpp  
比较容易编译（在ubuntu和aistudio），可以tiny-en model，可以识别句子，但识别单词似乎有问题（不知道为啥），待考  

## micro_speech  
* https://github.com/eliberis/microbit-speech  
by mbed, micro:bit  
* https://github.com/edgeimpulse/voice-activated-microbit  
by mbed, micro:bit  
* https://github.com/ARM-software/VHT-TFLmicrospeech  
* https://github.com/MatthiasHertel80/VHT-TFLmicrospeech  

## Facebook flashlight and wav2letter, in C++  
* https://github.com/flashlight/flashlight/tree/main/flashlight/app/asr  
* https://github.com/flashlight/wav2letter  

## Swift机器学习：面向iOS的人工智能实战  
* TLSphinx和OpenEars，它们都是cmu sphinx或pocketsphinx的ios移植版  
* https://github.com/tryolabs/TLSphinx    
* OpenEars, https://www.politepix.com/openears/tutorial/  

## TensorFlow Model  
* https://github.com/tensorflow/models/tree/master/research/deep_speech  
* VGGish and YAMNet  
* https://github.com/tensorflow/models/tree/master/research/audioset  
* https://github.com/SensingClues/OpenEars  

## PaddleSpeech  
* https://github.com/PaddlePaddle/PaddleSpeech  

## (TODO?) TinyMaix, KWS example  
* https://github.com/sipeed/TinyMaix/tree/main/examples/kws  
* Although **sipeed/Maix-Speech** is closed source, but TinyMaix is open source  
* https://github.com/YuzukiHD/TinyMaix-RP2040/tree/master/examples/kws  
* pc build: TinyMaix-RP2040-master_v1_ubuntu140432.tar.gz  
* ***No training method for kws ???***  
* see https://github.com/sipeed/TinyMaix/tree/main/tools/tmdl  
* https://github.com/Ai-Thinker-Open/aithinker_Ai-M6X_SDK  

## (TODO, IMP) Demonstrator project for speech recognition featuring several technologies, with tensorflow.js  
* https://goepfert.github.io/audio_features/  
* https://github.com/goepfert/audio_features  
* tfjs, TensorFlow.js  
* https://github.com/tensorflow/tfjs  

## (TODO) 基于DNN和DTW算法配合VAD截取的微语音识别框架, some sources lost, keil    
* https://github.com/jerenhu/MiniSpeech  
* (TODO, IMP) https://github.com/jerenhu/MiniSpeech/blob/master/MATLAB/dtw.m  

## (TODO) LSTM + CTC (?), TensorFlow 2深度学习实战, 人民邮电出版社  
* 57590_TensorFlow2深度学习实战_正文数据和代码.zip  
* 第5章, 基于LSTM网络的语音识别  
* LSTM + CTC (with TensorFlow 2.2 ?)    
* https://www.ryjiaoyu.com/book/details/44052  
* https://m.ryjiaoyu.com/resource/29440  
* ref: 神经网络与深度学习实战：Python+Keras+TensorFlow  
* ref: LSTM, sparse_categorical_crossentropy, mfcc  
* https://github.com/search?q=sparse_categorical_crossentropy+mfcc&type=code  
* ref: (run failed, see my aistudio) 
```
我试过用aistudio跑《TensorFlow 2深度学习实战里面》那个LSTM例子代码，
的确是可以跑得通的（我用的是TensorFlow 2.3）。
不过我以前还试过另一个LSTM的语音识别，结果失败了，是这个：
《Python+TensorFlow机器学习实战》第9.2章
（可能这里已经改好了：llSourcell/tensorflow_speech_recognition_demo）。
有时间可以对照改一下。
```
* ref: https://github.com/llSourcell/tensorflow_speech_recognition_demo  
* search tf2lstm5_v1.tar.gz  

## (TODO) LSTM + CTC (???), Python自然语言处理实战
* Hands-On Natural Language Processing with Python  
* https://www.ituring.com.cn/book/2679  
* 《Python自然语言处理实战》链接表  
https://www.ituring.com.cn/article/510382  
* Hands-On Natural Language Processing with Python  
https://www.packtpub.com/free-ebook/hands-on-natural-language-processing-with-python/9781789139495  
* (IMP) 第11章, 使用DeepSpeech进行语音识别  
https://github.com/PacktPublishing/Hands-On-Natural-Language-Processing-with-Python/blob/master/Chapter11/01_example.ipynb  
tflearn, librosa mfcc, tflearn.lstm categorical_crossentropy  
search baidupan, Python自然语言处理实战  
* https://github.com/Jakobovski/free-spoken-digit-dataset  
speech_dset  

## TFLearn LSTM, tensorflow_speech_recognition_demo, and 《Python+TensorFlow机器学习实战》第9.2章  
* (my work) https://github.com/weimingtom/tensorflow_speech_recognition_demo_mod  
* (origin) https://github.com/llSourcell/tensorflow_speech_recognition_demo  
* mod ref to https://github.com/PacktPublishing/Hands-On-Natural-Language-Processing-with-Python/blob/master/Chapter11/01_example.ipynb  
* see https://github.com/tflearn/tflearn/blob/master/tutorials/intro/quickstart.md  
* search spoken_numbers_pcm.tar  
* search tensorflow_speech_recognition_demo-master_min_v2_success.zip  
* search tf_02.tar.gz  
* data set from https://github.com/pannous/tensorflow-speech-recognition  
* data set from https://github.com/pannous/caffe-speech-recognition  
* https://github.com/hcchengithub/tensorflow_speech_recognition_demo/blob/master/lstm-tflearn.py  
* https://github.com/llSourcell/tensorflow_speech_recognition_demo/issues/29  
* https://github.com/Chancing0/EZ-LSTM-Speech-Recognition-Project  
* https://github.com/pannous/tensorflow-speech-recognition/blob/master/lstm-tflearn.py  

## (TODO, IMP, not exists now) ESP8266 Baidu ASR Demo (AT command)  
* https://github.com/achinwoo/BAIDU_ASR_ESP8266/blob/master/app/user/user_main.c  
* https://github.com/achinwoo/BAIDU_ASR_ESP8266/blob/master/lib/librest.a  
* https://github.com/achinwoo/BAIDU_ASR_ESP8266  
* https://github.com/MhageGH/esp32_CloudSpeech  
* https://github.com/MhageGH/esp32_SoundRecorder  
```
app/include/rest.h, lib/librest.a, vop.baidu.com/pro_api    
int send_baidu(int sta_socket);
```
* 百度大脑, AI开放平台, 语音识别极速版API  
* (IMP) https://github.com/Baidu-AIP/speech-demo  
* https://ai.baidu.com/ai-doc/SPEECH/jkhq0ohzz  
* https://ai.baidu.com/ai-doc/  
* (old, not used) https://ai.baidu.com/docs#/ASR-API-PRO/top  
* https://blog.csdn.net/weixin_40973138/article/details/103106608  
* https://ai.baidu.com/forum/topic/show/957508  
* https://blog.csdn.net/weixin_43271060/article/details/90318840  
* https://github.com/lixy123/TTGO_T_Watch_Baidu_Rec  
* https://github.com/lixy123/ESP32-AUDIO-REC  

## 基于百度语音的识别语音，转文字  
* https://gitee.com/rx-ted/baidu-asr  

## ESP32 语音唤醒+离线识别+百度在线识别  
* https://github.com/HoGC/esp_speech_recognition  
* search github, esp32 speech, esp8266 speech  

## (TODO) DTW, 用“芯”探核：龙芯派开发实战  
* https://max.book118.com/html/2021/0507/6035234121003144.shtm  
* 第十二章，语音关键词检索  
* CSpeechRecognitionCore::DTWCal  
* search 龙芯派开发实战_第12章语音识别  

## (TODO) TinyML Cookbook  
* Chapter 4: Voice Controlling LEDs with Edge Impulse  
* https://www.packtpub.com/product/tinyml-cookbook/9781801814973  
* https://github.com/PacktPublishing/TinyML-Cookbook  
* (TODO) https://github.com/PacktPublishing/TinyML-Cookbook/blob/main/Chapter04/ArduinoSketches/09_kws_raspberrypi_pico.ino  
* (TODO) https://github.com/PacktPublishing/TinyML-Cookbook/blob/main/Chapter04/ArduinoSketches/07_kws_arduino_nano_ble33_sense.ino  

## Deep Learning for NLP and Speech Recognition  
* https://github.com/SpringerNLP   
* Chapter 8: Automatic Speech Recognition, with Kaldi and Sphinx  
https://github.com/SpringerNLP/Chapter8  
CMUSphinx (sphinxbase+sphinxtrain+pocketsphinx+cmuclmtk), with GMM/HMM  
* Chapter 12: End-to-end Speech Recognition, with deepspeech2 pytorch  
https://github.com/SpringerNLP/Chapter12  
https://github.com/SeanNaren/deepspeech.pytorch  
* Chapter 7: Recurrent Neural Networks, with LSTM  
https://github.com/SpringerNLP/Chapter7  

## Voiceprint-Recognition  
* https://github.com/SunYanCN/Voiceprint-Recognition  
* https://github.com/microsoft/nni  
* https://github.com/majianjia/nnom  
* https://github.com/rjagiasi/SpeakerRecognition  

## sherpa-ncnn  
* https://github.com/k2-fsa/sherpa-ncnn  
* http://speechhome.com/blogs/kaldi/1632583916625989632  
* RV1126  
https://www.zhihu.com/zvideo/1615111252941922304  
* https://k2-fsa.github.io/sherpa/ncnn/android/build-sherpa-ncnn.html#download-pre-trained-models  
* https://huggingface.co/PingfengLuo/icefall-asr-conv-emformer-transducer-stateless2-zh  
* apk file see 'Files and versions' of this page :  
https://huggingface.co/csukuangfj/sherpa-ncnn-apk

## ThatProject, ESP32_MICROPHONE  
* https://github.com/0015/ThatProject/tree/master/ESP32_MICROPHONE  

## (TODO) Keras 2D CNN+RNN+CTC  
* Automatic Speech Recognition using CTC  
https://keras.io/examples/audio/ctc_asr/
https://huggingface.co/keras-io/ctc_asr
https://huggingface.co/spaces/keras-io/ctc_asr  

## (TODO) NLP  
* 中文语料库, 中文语料   
* 知识图谱, 知网, csdn, wordnet   
* search baidupan, 语料，Corpus  

## (TODO) TODO list, keep putting here at last    
* https://github.com/edgeimpulse/voice-activated-microbit  
* https://github.com/ggerganov/whisper.cpp  
* https://github.com/k2-fsa/sherpa-ncnn/blob/master/android/SherpaNcnn/app/src/main/java/com/k2fsa/sherpa/ncnn/MainActivity.kt
* https://github.com/houaohui/ChatGPT-Assistant  
