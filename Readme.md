﻿[QCopterFC](https://github.com/Hom19910422/QCopterFlightControl)
========
* Author  : [Hom](https://github.com/Hom19910422)
* Version : v2.0
* Update  : 2013/12/26

Description
========
QCopteFC 是一個基於 STM32 的飛行控制器，可以應用於固定翼、旋翼飛行器上面，  
這裡主要應用於四軸飛行器，用來實現濾波、平衡、控制等演算法的平台。

Hardware
========
* 控制器　 : [STM32F405R](http://www.st.com/web/catalog/mmc/FM141/SC1169/SS1577/LN1035/PF252144) 64Pin 168MHz DSP FPU
* 感測器　 : [IMU_10-DOF](https://github.com/Hom19910422/IMU_10-DOF) ( [MPU-9150](http://www.invensense.com/mems/gyro/mpu9150.html) + [MS5611](http://www.meas-spec.com/product/pressure/MS5611-01BA03.aspx) )
* 無線傳輸 : [nRF24L01P](http://www.nordicsemi.com/eng/Products/2.4GHz-RF/nRF24L01P) + PA + LNA
* 儲存紀錄 : micro SD，使用 SDIO 操作
* 外接介面 : 2*ADC、1*USB ( Micro )、1*SPI ( FFC16 )、1*UART、12*PWM
* PCB 尺寸 : 52 * 35mm ( Screws M3: 30 * 30mm )
* 設計軟體 [Altium Designer 13](http://www.altium.com/en/products/altium-designer) ( [PcbLib](https://github.com/CYACAcademic/AltiumDesigner_PcbLibrary) use AD PcbLib v0.? )

**** v2.1 版本預計減少 2 個 PWM 通道，並新增 1 個 CAN Bus ****

<img src="https://lh3.googleusercontent.com/-rm8MVLJdUs4/Uk_NJPWXKSI/AAAAAAAAD48/YXHRJBrHHRs/s800/QCopterFC_System.png" height="685" width="689" /><br>

Related Documents
========
* [Google Drive](https://drive.google.com/folderview?id=0BzL2wwAot6oPS0thRUVrb0VadTQ&usp=sharing)

Program
========
* QcopterFC FlightControl Pre-Alpha ( MDK 5.0, StdPeriph_Lib v1.3 )
* QcopterFC FlightRecorder Pre-Alpha

Test
========
* QCopterFC LED
* QCopterFC UART
* QCopterFC PWM ( TIM8 目前無法輸出 PWM )
* QCopterFC ADC
* QCopterFC FLASH
* QCopterFC CamSPI-Master
* QCopterFC IMU ( Use MPU-9150 + MS5611 )
* QCopterFC NRF ( Use nRF24L01P )
* QCopterFC SDIO ( Use [Fatfs](http://elm-chan.org/fsw/ff/00index_e.html) 0.10 )

View
========
<img src="https://lh5.googleusercontent.com/-ky_2nBrI-qg/UlgWweh37MI/AAAAAAAAEUE/ECMFVCJQzjY/s800/DSC_1526.jpg" height="450" width="800" />
<img src="https://lh5.googleusercontent.com/-luXgDBU_c3I/UlgWwbvD0XI/AAAAAAAAEUM/ZG6JbNtpGjU/s800/DSC_1528.jpg" height="450" width="800" />
<img src="https://lh6.googleusercontent.com/-HOtHMLHlSEc/UlgWwTOwRCI/AAAAAAAAEUI/Z66a-la6Xlg/s800/DSC_1530.jpg" height="450" width="800" />
<img src="https://lh4.googleusercontent.com/-HIt9nbvZP4w/UlgWxkethiI/AAAAAAAAEUQ/X9v4cRj-Pu8/s800/DSC_1532.jpg" height="450" width="800" />
<img src="https://lh3.googleusercontent.com/-kgoXTxh7n2g/UlT08JoieZI/AAAAAAAAESo/rKA-xOCO1C0/s800/DSC_1467.jpg" height="450" width="800" />
<img src="https://lh3.googleusercontent.com/-EY2oXRwO3RQ/UlT08GJyyrI/AAAAAAAAERg/uN4Pzw9CRdk/s800/DSC_1471.jpg" height="450" width="800" />
<br />
更多圖片 [Google+ albums](https://plus.google.com/u/0/photos/+文宏王Hom/albums/5899377395636747681)

Config
========
．Vin 建議輸入 5v ~ 6v
<img src="https://lh5.googleusercontent.com/-o_g3fwO7YZk/Ul_-vnKPpFI/AAAAAAAAEaM/UOzqKk6ZdxY/s800/FC_CONF.png" height="423" width="800" />
<img src="https://lh5.googleusercontent.com/-eOYB9qvfXkA/Uk_NEUlk4UI/AAAAAAAAD48/66StQySN_O0/s800/QCopterFC_Config_PIN.png" height="417" width="800" />
<img src="https://lh3.googleusercontent.com/-htom-WouTZM/Uk_NERTK6dI/AAAAAAAAD48/9TcFCyOX_2s/s1600/QCopterFC_Config_AF.png" width="800" />
<img src="https://lh6.googleusercontent.com/-wvzaurZbA1s/Uk_NEceZAVI/AAAAAAAAD48/Id1RUrmwaUI/s800/QCopterFC_Config_DMA.png" height="436" width="800" />

*** 傳輸資料格式 QFC_TO_QRC
<img src="https://lh3.googleusercontent.com/-eIh5NvuE0aw/UrsPnzmAcZI/AAAAAAAAGDc/mu5YwwC-S1s/s1600/QFC_TO_QRC.png" height="678" width="800" />

Schematic
========
<img src="https://lh3.googleusercontent.com/-HaCAqU9mz2Q/Uk_NG7cQjBI/AAAAAAAAD48/lMp5zNsjtgA/s1600/QCopterFC_Sch_MAIN.png" width="1200" />
<br>＊STM32F405R<br>
<img src="https://lh4.googleusercontent.com/-iKskK9Hvdrc/Uk_NHHoIHHI/AAAAAAAAD48/cQ8JTI_H-sA/s1600/QCopterFC_Sch_MCU.png" width="635" />
<br>＊SW<br>
<img src="https://lh3.googleusercontent.com/-LuZMXexBvv8/Uk_NINTnZ7I/AAAAAAAAD48/LlrjNmVkYVM/s800/QCopterFC_Sch_SW.png" height="156" width="175" />
<br>＊Power<br>
<img src="https://lh4.googleusercontent.com/-_lBw8ulvE7A/Uk_NHVvj9_I/AAAAAAAAD48/Rt2CdnJvy7E/s800/QCopterFC_Sch_POWER.png" height="282" width="355" />
<br>＊LED<br>
<img src="https://lh4.googleusercontent.com/-1kbU71qJiWg/Uk_NGlOS8OI/AAAAAAAAD48/sgGvr6iinOQ/s800/QCopterFC_Sch_LED.png" height="146" width="290" />
<br>＊KEY<br>
<img src="https://lh6.googleusercontent.com/-SaXrFsHTKJU/Uk_NGLQuMII/AAAAAAAAD48/RxLkFVjraIo/s800/QCopterFC_Sch_KEY.png" height="210" width="138" />
<br>＊PWM<br>
<img src="https://lh4.googleusercontent.com/-OGFtXtI_moQ/Uk_NINec1BI/AAAAAAAAD48/TTDNDTRmroE/s800/QCopterFC_Sch_PWM.png" height="247" width="299" />
<br>＊EXTERN<br>
<img src="https://lh3.googleusercontent.com/-bPhWfg_ZFwA/Uk_NGOQnjBI/AAAAAAAAD48/20R0B_-lDKU/s800/QCopterFC_Sch_EXTERN.png" height="147" width="276" />
<br>＊CamSPI<br>
<img src="https://lh6.googleusercontent.com/-6A3St5WT2GY/Uk_NFFWOkhI/AAAAAAAAD48/XzsYK34p6tA/s800/QCopterFC_Sch_CAMERA.png" height="329" width="200" />
<br>＊nRF24L01P<br>
<img src="https://lh3.googleusercontent.com/-SXGxVOg5zlI/Uk_NHU-uC4I/AAAAAAAAD48/NbXYao3fqyY/s800/QCopterFC_Sch_NRF.png" height="194" width="200" />
<br>＊IMU<br>
<img src="https://lh3.googleusercontent.com/-EadurHkURZg/Uk_NGJWfqXI/AAAAAAAAD48/c9lLoBgVZK4/s800/QCopterFC_Sch_IMU.png" height="169" width="192" />
<br>＊SD<br>
<img src="https://lh3.googleusercontent.com/-UodBF51RJiM/Uk_NIq6hAhI/AAAAAAAAD48/VXmWAwvCFYE/s800/QCopterFC_Sch_SDCARD.png" height="241" width="402" />
<br>＊USB<br>
<img src="https://lh3.googleusercontent.com/-tQM04js18v8/Uk_NI4r4GyI/AAAAAAAAD48/Ze4JTXnHF6Y/s800/QCopterFC_Sch_USB.png" height="231" width="315" />
<br />
<br />
<a href="http://www.oshwa.org/">
<img src="https://lh5.googleusercontent.com/-nIBTA3RL8Hk/Ug8wr_ly3-I/AAAAAAAADFY/hAfv5LAzHag/s144/oshw-logo-800-px.png">
<br />
<br />
<a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/tw/deed.zh_TW"><img alt="創用 CC 授權條款" style="border-width:0" src="http://i.creativecommons.org/l/by-sa/3.0/tw/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" property="dct:title"> QCopterFlightControl </span>由<a xmlns:cc="http://creativecommons.org/ns#" href="https://plus.google.com/u/0/112822505513154783828/posts" property="cc:attributionName" rel="cc:attributionURL"> Hom </a>製作，以<a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/tw/deed.zh_TW">創用CC 姓名標示-相同方式分享 3.0 台灣 授權條款</a>釋出。<br />此作品衍生自<a xmlns:dct="http://purl.org/dc/terms/" href="https://github.com/Hom19910422" rel="dct:source"> Hom-GitHub </a>
