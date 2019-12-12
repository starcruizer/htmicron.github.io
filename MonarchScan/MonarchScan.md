# Monarch Scan Application for HT32SX 

<div align="center">
  <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSesenrhZDRBpVRdUHpQ5ouT6wUTu0t0zaYtSI5GZqXJjGc2tor4Q&s">
</div>

### Introduction
The iMCP is a Multicomponent Integrated Circuit (MCO) built for the Internet of Things, it provides a ready-to-use connectivity solution for the SigFox™ network. 
The system combines an ARM Cortex M0+ 32bit, a S2-LP high performance, ultra-low power RF transceiver and a RF Power Amplifier with all of the advantages, integration and convenience found in a SiP (System In Package), which is one of the most advanced semiconductor packaging technology.
As a SigFox™ Monarch enabled device, it can operate in all regions covered by SigFox™ Network without need of reconfiguration. This is possible because the device can detect the region of operation and rearrange its setup automatically.

### About this document 
The purpose of this document is to assist the engineer and explain how the SigFox™ protocol can be used on the iMCP – HT32SX. The firmware described in this document is version 4.19.50, it has integrated SigFox™ and SigFox™ Monarch driver support, which simplifies the usage of resources and the access to the SigFox™ network. The measurements and analysis included in this application note is based upon HT Micron’s interpretation of both measurements and rules. It is recommended to read this application note in conjunction with HT Micron User’s Guide.
The whole application can be viwed clicking on the "Files" tab on the left hand.

In this application note, we explore the Monarch feature, which is able to recognize a Monarch Beacon in all of regions covered by SigFox™ network.

### Application description
The application starts configuring the MCU peripherals needed for the transceiver operation and the Universal Synchronous Asynchronous Receiver Transmitter (USART1), which is necessary to see and verify the results returned from all of functions used in this software. When everything is ready, the algorithm begins scanning a Monarch Beacon for a period of 10 minutes. If a Beacon is found, the device is going to reconfigure itself and will send a frame to the currently region. The payload to be sent, will load with it a message containing an integer corresponding to the region that was found. 
The user may check the message sent searching for the device ID at the SigFox™ Backend. More information about it can be found reading the Getting Started document.

The user may check the message sent searching for the device ID at the SigFox™ Backend. More information about it can be found reading the Getting Started document.

### Software architecture 
The project was developed at Keil µVision IDE, fallowing the STM32CubeMX patterns. All of the SigFox Libraries are also included.

For organizational purpose, the project was divided by MCU peripherals. The user may see, for example, the RTC implementation looking at the “rtc.c” file. The same was made for GPIO, timers, SPI, and USART.

#### Code description

<div align="center">
	**Table 1. Available Functions**
</div>

| Name | Arguments | Descripton | 
| --- | --- | --- |
| **monarchScan** | **rc_capabilities_bit_mask:**  Bit Mask (Table 2) of the RCx on which the scan has to be executed.<br/> **timer:** Scan duration value (with the unit parameter information). <br/> **unit:** Unit to be considered for the scan time computation | This function executes a scan of the air to detect a SigFox Beacon. It will return 0, if success and the RC enum value corresponding to the beacon found and its RSSI level. The scan is executed during the specific timer/unit time. |
| **configRegion** | None | Configures the device using the RCZ found after Monarch Scan. Call the functions St_Sigfox_Open_RCZ, to execute these configurations and sendFrameRCZ. Both functions will be described below. |
| **St_Sigfox_Open_RCZ** | RCZ: Integer corresponding to the radio zone. |  Opens SigFox Library according to the zone. Returns 0 if ok. |
| **sendFrameRCZ** | None | Send a frame to the SigFox network using the RCZ found after Monarch Scan. Returns 0 if success. |
| **closeSigfoxLib** | None | This function closes the library (Free the allocated memory of SIGFOX_API_open and close RF). Returns 0 if success. |
| **mcuConfig** | None | Starts the MCU peripherals configuration and get credentials from Flash memory. |
| **ST_Init** | None | Configure the MCU peripherals needed for the transceiver operation. |

<br/>

<div align="center">
	**Table 2. SigFox Monarch RC Capabilities bitmask.**
</div>

<div align="center">
	| Bit7 | Bit6 | Bit5 | Bit4 | Bit3 | Bit2 | Bit1 | Bit0 |
	|------|:----:|:----:|:----:|:----:|:----:|:----:|-----:|
	|   -  |   -  | RC6  | RC5  | RC4  | RC3  | RC2  |  RC1 |
</div>

<br/>

### Results
Some results are expected running this application. First, the monarch scan begins, looking for a Monarch Beacon. This process will still go on for 10 minutes, showing the rssi and printing on the RS232 terminal the region which was found. At the end, a frame is sent to the currently region. 
The results can be seen below:

<div align="center">
  <img src="https://www.googleapis.com/drive/v3/files/1Zk3hGocssoDgSSVlAkGDNPV6K7wrB6Dk?alt=media&key=AIzaSyCm-djN9v8CYvbkJ1YNUGdKxo0DrotYn74">
</div>

<div align="center">
  <img src="https://www.googleapis.com/drive/v3/files/1ixfsPEG8xkcZ4hOcd0WZYsEAXSc6SSlp?alt=media&key=AIzaSyCm-djN9v8CYvbkJ1YNUGdKxo0DrotYn74">
</div>

### Extra Documentation 
Datasheets and application notes can be found at the [**HT32SX Repository**](https://github.com/htmicron/ht32sx).

### References
For additional information about SigFox™ libraries designed by ST Microelectronics, please refer to the UM2173 document (note: the function names still the same, but the code was adapted to use in the iMCP design, so it is different from the one distributed by ST).

### Contact Information

Head Office – São Leopoldo, RS 
HT Micron Semiconductors
Unisinos Avenue, 1550
São Leopoldo - RS             
ZIP 93022-750 <br/>
Brazil <br/>
Tel: +55 51 3081-8650 <br/>
E-mail (Support): support_iot@htmicron.com.br <br/>
E-mail (General Enquiries): htmicron@htmicron.com.br
