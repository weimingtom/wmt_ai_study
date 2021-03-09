## miniconda (without numpy)    
Miniconda3-latest-Windows-x86_64.exe  
https://docs.conda.io/en/latest/miniconda.html  

## Thonny 3.3.5 (for Windows) (without numpy)      
https://thonny.org  
thonny-3.3.5.exe  
Scripts\pip.bat install numpy==1.14.6 matplotlib==2.2.3  

## 【安富莱——DSP教程】第28章 ST官方汇编FFT库应用  
https://bbs.elecfans.com/jishu_496212_1_1.html  
matlab:  
```
Fs = 1000;                  % 采样率
N  = 1024;           % 采样点数
n  = 0:N-1;           % 采样序列
t  = 0:1/Fs:1-1/Fs;     % 时间序列
f = n * Fs / N;          %真实的频率

%波形是由直流分量，50Hz正弦波和20Hz正弦波组成
x = 1024 + 1024*sin(2*pi*50*t) + 512*sin(2*pi*20*t)  ;
y = fft(x, N);               %对原始信号做FFT变换

subplot(2,1,1);
Mag = abs(y)*2/N;         %求FFT转换结果的模值
plot(f, Mag);               %绘制幅频相应曲线
title('Matlab计算结果');
xlabel('频率');
ylabel('幅度');

subplot(2,1,2);
plot(f, sampledata);   %绘制STM32计算的幅频相应
title('STM32计算结果');
xlabel('频率');
ylabel('幅度');
```
NumPy:  
```
import numpy as np
import matplotlib.pyplot as plt

Fs = 1000
N = 1024
n = np.r_[0 : N]
t = np.r_[0 : 1 : 1 / Fs]
f = n * Fs / N
x = 1024 + 1024 * np.sin(2 * np.pi * 50 * t) + 512 * np.sin(2 * np.pi * 20 * t)
y = np.fft.fft(x, N)
Mag = np.abs(y) * 2 / N
plt.plot(f, Mag)
plt.show()
```
