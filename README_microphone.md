## Ai-Thinker(安信可) NodeMCU-32S, ESP32  
* M5Stack PDM Unit + M5Stack Mini-Proto Unit, M5Stack (明栈)      
(demo) PDM_v1_nodemcu32s_success.rar    
(origin) https://docs.m5stack.com/#/zh_CN/unit/pdm  
(origin) https://github.com/m5stack/M5-ProductExampleCodes/tree/master/Unit/PDM  
PDM<->NodeMCU-32S  
CLK (white) <->GPIO22 (right top 3)  
DAT (yellow)<->GPIO21 (right top 6)  
5V  (red)   <->3V3    (left top 1)  
GND (black) <->GND    (right top 1)  

* ADMP401, 都会明武  
(demo) ADMP401_v1_success_duhui.rar  
(origin, from code for SPW2430) https://esp32.com/viewtopic.php?t=7077#p30450  
(origin, from code for SPW2430) https://forums.adafruit.com/viewtopic.php?f=8&t=140676  
**WARNING: DON'T PUT 5V to ADMP401 VCC PIN**
ADMP401<->NodeMCU-32S  
VCC<->3.3V  (left top 1) 
GND<->GND   (right top 1)  
AUD<->GPIO4 (right bottom 7)  

## Arduino Uno, ATMEGA328P  
* Music Shield, VS1053B, waveshare (微雪)  
(demo) ???  
(origin) https://www.waveshare.net/wiki/Music_Shield  
