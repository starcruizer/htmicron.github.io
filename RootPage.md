# HT32SX - HT Micron's Sigfox Monarch SiP

<div align="center">
  <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSesenrhZDRBpVRdUHpQ5ouT6wUTu0t0zaYtSI5GZqXJjGc2tor4Q&s">
</div>

### Introduction
The iMCP is a Multicomponent Integrated Circuit (MCO) built for the Internet of Things, it provides a ready-to-use connectivity solution for the SigFox™ network. 
The system combines an ARM Cortex M0+ 32bit, a S2-LP high performance, ultra-low power RF transceiver and a RF Power Amplifier with all of the advantages, integration and convenience found in a SiP (System In Package), which is one of the most advanced semiconductor packaging technology.
As a SigFox™ Monarch enabled device, it can operate in all regions covered by SigFox™ Network without need of reconfiguration. This is possible because the device can detect the region of operation and rearrange its setup automatically.

### Hardware Setup
The required hardware to perform the steps described in this document consists of: <br/>
•	HT Micron iMPC Evaluation Kit <br/>
•	HT Micron iMPC Evaluation Board <br/>
•	Micro-USB cable for power supply <br/>
•	An antenna covering the RCZ frequency range to be used. <br/>

<div align="center">
  <img src="https://www.googleapis.com/drive/v3/files/1HpKZvwy8FMe-W-e1R-ALtlym8xjseIq9?alt=media&key=AIzaSyCm-djN9v8CYvbkJ1YNUGdKxo0DrotYn74">
</div>

### Software Setup
This section describes all necessary steps needed to use the SigFox™ with the iMCP – HT32SX. <br/>
Also, these programs are recommended: <br/>
•	[**GIT**](https://git-scm.com/downloads). <br/>
•	[**STM32 ST-LINK Utility**](https://www.st.com/en/development-tools/stsw-link004.html). <br/>
•	[**ARM Keil µVision**](https://www.keil.com/demo/eval/arm.htm) for STM32 or [**STM32CubeIDE**](https://www.st.com/en/development-tools/stm32cubeide.html).<br/>
•	[**STM32CubeMX**](https://www.st.com/en/development-tools/stm32cubemx.html) for personalisation of the program using a graphical interface. <br/>
•	RS232 terminal ([**Termite**](https://www.compuphase.com/software_termite.htm) is recommended). <br/>	

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
