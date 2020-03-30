# Frequently Asked Questions about HT32SX 

## Questions list:

• [**How do I register a new user on the SigFox Backed?**](#regbackend) <br/>
• [**How do I register a new device on the SigFox Backed?**](#regdevice) <br/>
• [**How or where can I check if my device is sending the massages correctly?**](#msgcorrec) <br/>
• [**How should I set up my new device to operate in my current region?**](#configrc) <br/>
• [**How many messagens can I send daily?**](#dailymsg) <br/>
• [**How long should I wait between sending two messages?**](#delaymsg) <br/>
• [**What is the Keil uVision set up for debug purpose?**](#debugpurpose) <br/>
• [**How to open the examples using STM32CubeIDE?**](#cudeide1) <br/>
• [**What or which peripherals can I change using STM32CubeMX/CubeIDE graphical interface?**](#cudemx) <br/>
• [**Error: Invalid message sequence from Device #XXXXX: expected X, actual X**](#eventmsg) <br/>

## Answered Questions:

<a name="regbackend"></a>
### • How do I register a new user on the SigFox Backed?

<hr>
> **Answer:** 

> • If you do not have an account and just received an Evaluation Board:

> **1 -** Go to [**SigFox Buy**](https://buy.sigfox.com/activate) and select your country. <br/>
> **2 -** If you do not know the device ID and PAC, open a serial terminal and run one of our [**GitHub**](https://github.com/htmicron/ht32sx) examples. That information should be shown as the image below:

<div align="center">
	![id_pac](https://www.googleapis.com/drive/v3/files/1sW1ahpsqRUkARdzv-rliSx3C6Zm96upo?alt=media&key=AIzaSyA3IM3FTM-B4ibyKf1dUPBdbmKgAN9LX-s)
</div>

> **3 -** Fill all the spaces, follow the steps and an account will be created with your device registered.

<hr>

> • On the other hand, if you already have an account: <br/> 

> **1 -** Go to [**SigFox Backend**](https://backend.sigfox.com/), access your account and click _**User**_:

<div align="center">
	![user_newuser](https://www.googleapis.com/drive/v3/files/1C9ppohn34-PME5Q0Li54-l6j_L2UPp52?alt=media&key=AIzaSyA3IM3FTM-B4ibyKf1dUPBdbmKgAN9LX-s)
</div>

> **2 -** Click _**New**_, fill all spaces, select the group which this new user will participate and select the permissions. The following permissions are recommended for admin access:

<div align="center">
	![permissions](https://www.googleapis.com/drive/v3/files/1koGiXAiHDy8k0T2mRYA1Ce60rI99NUrU?alt=media&key=AIzaSyA3IM3FTM-B4ibyKf1dUPBdbmKgAN9LX-s)
</div>

<hr>

<br/>

<a name="regdevice"></a>
### • How do I register a new device on the SigFox Backed?
<hr>

> **Answer:** If you already have an account, check the following steps below, otherwise check the [**Account Registration**](#regbackend) topic.<br/> 

> **1 -** Open the [**SigFox Backend**](https://backend.sigfox.com/) website. <br/>
> **2 -** Click _**Device**_:

<div align="center">
	![devices](https://www.googleapis.com/drive/v3/files/1-u-sz7Adi7hbe048oZzAcpSq2Da_A5fk?alt=media&key=AIzaSyBazifvhYWroBBnEocbFpLG0mOjfUfelE4) <br/> 
</div>

> **3 -** Then click _**New**_ to register a new device:

<div align="center">
	![new](https://www.googleapis.com/drive/v3/files/1p1YuczQEaY9rl7sMq3Bg4l-FvM9OVs5w?alt=media&key=AIzaSyBazifvhYWroBBnEocbFpLG0mOjfUfelE4)  <br/> 
</div>

> **3 -** Select the group which your device will be part of:

<div align="center">
	![group](https://www.googleapis.com/drive/v3/files/1ZaWI1HwtjCZa_cMn_b2HwYKeQ6LvDJ69?alt=media&key=AIzaSyD0vizVRI4gcudGwFjpVAbRKDtjUcs-KDk)
</div>

> **4 -** Fill the underlined fields with your device ID & PAC and choose a name for this new device.

<div align="center">
	![form](https://www.googleapis.com/drive/v3/files/1T6f-IWvKywE9MNkR91_4jx9xSE6CpOZ3?alt=media&key=AIzaSyBazifvhYWroBBnEocbFpLG0mOjfUfelE4) <br/> <br/>
</div>

> **5 -** Finally, click _**Ok**_ and your device will be registered.

<hr>
<br/>

<a name="msgcorrec"></a>
### • How or where can I check if my device is sending the massages correctly?
<hr>

> **Answer:**  If you do not have an account on [**SigFox Backend**](https://backend.sigfox.com/) or haven't registered your device yet, check the [**Account Registration**](#regbackend) topic or the [**Device Registration**](#regdevice) topic. 
> If It's already done, check the following steps: <br/> 

> **1 -** Open the [**SigFox Backend**](https://backend.sigfox.com/) website, where all your messages will be shown. <br/>
> **2 -** Click _**Device**_:

<div align="center">
	![devices](https://www.googleapis.com/drive/v3/files/1-u-sz7Adi7hbe048oZzAcpSq2Da_A5fk?alt=media&key=AIzaSyBazifvhYWroBBnEocbFpLG0mOjfUfelE4) <br/> 
</div>

> **3 -** Look for your device ID and click on it:

<div align="center">
	![deviceselect](https://www.googleapis.com/drive/v3/files/15KFeZQS8hMDV8PTi6fLRsBA-udrvvj5a?alt=media&key=AIzaSyBazifvhYWroBBnEocbFpLG0mOjfUfelE4)
</div>

> **4 -** Then click _**Messages**_ and all messages received from that ID will be shown:

<div align="center">
	![msgtab](https://www.googleapis.com/drive/v3/files/1KWfBygD_fq58IR_YOKTo_jCsC3yM6T65?alt=media&key=AIzaSyBazifvhYWroBBnEocbFpLG0mOjfUfelE4)
</div>

<hr>
<br/>

<a name="configrc"></a>
### • How should I set up my new device to operate in my current region?
<hr>

> **Answer:** <br/> 

> **1 -** Open the [**Generic_Push_Button**](https://github.com/htmicron/ht32sx/tree/master/firmware_applications/Generic_Push_Button) example, provided on our [**GitHub**](https://github.com/htmicron/ht32sx) repository. <br/>
> **2 -** Open the _**main.c**_ file and search for the _**main**_ function. <br/>
> **3 -** Change the _**configRegion**_ parameter and select the region where you are currently working on:

<div align="center">
	![configregion](https://www.googleapis.com/drive/v3/files/1ZtC7WG6ENod6rMT0C7E5UGqXAQTPLlW4?alt=media&key=AIzaSyBazifvhYWroBBnEocbFpLG0mOjfUfelE4)
</div>

<hr>
<br/>

<a name="dailymsg"></a>
### • How many messagens can I send daily?
<hr>

> **Answer:** The SigFox Network allows 140 per day. It's recommended to use the [**SigFox Dongle**](https://build.sigfox.com/sdr-dongle) for messages debbuging purposes (when the user needs to send a lot of messages) and the Backend only to confirm your tests; 

<hr>
<br/>

<a name="delaymsg"></a>
### • How long should I wait between sending two messages?
<hr>

> **Answer:** The SigFox Network recommends to respect a duty cycle of 1% between messages. 
> This means that it is necessary to respect a 10 minutes delay between messages (this is also a rule usually required by your local Regulatory Agency responsible for radio communications), otherwise the cloud might reject the messages and generate that event alert.

<hr>
<br/>

<a name="debugpurpose"></a>
### • What is the Keil uVision set up for debug purpose?

> **1 -** Open Keil uVision and go to _**Project -> Options for target -> Device**_ and select _**STM32LO52T8Yx**_:

<div align="center">
	![keil1](https://www.googleapis.com/drive/v3/files/1CyPrCSclun1YW_VBQcrAM6IYykpqHIce?alt=media&key=AIzaSyA3IM3FTM-B4ibyKf1dUPBdbmKgAN9LX-s)
</div>

> **2 -** Go to _**Debug**_ and select _**ST-Link Debugger**_ option:

<div align="center">
	![keil2](https://www.googleapis.com/drive/v3/files/1YIbnLN35FnBYIa9U2TBVhliwDIrLz-0T?alt=media&key=AIzaSyA3IM3FTM-B4ibyKf1dUPBdbmKgAN9LX-s)
</div>

> **2 -** Click _**Settings**_ and change the _**Connect**_ option to connect _**with Pre-reset**_.

<div align="center">
	![keil3](https://www.googleapis.com/drive/v3/files/1WRr57TvcUAmXhrc9mQv3FFUcGAjK7Hmu?alt=media&key=AIzaSyA3IM3FTM-B4ibyKf1dUPBdbmKgAN9LX-s)
</div>

> **3 -** Click _**Flash Download**_  tab and check if the HT32SX MCU (STM32LO) is already listed.

<div align="center">
	![keil4](https://www.googleapis.com/drive/v3/files/1hzXU6mNMWJryagcFwDXi-TOgRmXiovdD?alt=media&key=AIzaSyA3IM3FTM-B4ibyKf1dUPBdbmKgAN9LX-s)
</div>

 > Otherwise click _**Add**_ and select the right MCU:
 
<div align="center">
	![keil5](https://www.googleapis.com/drive/v3/files/1Hrc5Lf4xckgbvH3_DC69MxJQeOSLOaT5?alt=media&key=AIzaSyA3IM3FTM-B4ibyKf1dUPBdbmKgAN9LX-s)
</div>

<hr>
<br/>


<a name="cudeide1"></a>
### • How to open the examples using STM32CubeIDE?
<hr>

> **Answer:** 

> **1 -** Install [**STM32CubeIDE**](https://www.st.com/en/development-tools/stm32cubeide.html). <br/>
> **2 -** Clone the [**MASTER BRANCH**](https://github.com/htmicron/ht32sx/tree/master) of our [**GitHub Repository**](https://github.com/htmicron/ht32sx). <br/>
> **3 -** Open the directory where you cloned the repository, click _**firmware_applications**_ and select an example which you want to use in your project. <br/>
> **4 -** Open the _**STM32CubeIDE**_ directory and double-click the _**cproject**_ file:

<div align="center">
	![cproject](https://www.googleapis.com/drive/v3/files/1UZJkxDV7iRGEXEl9ZqBIAL0a-mfV9yTL?alt=media&key=AIzaSyA3IM3FTM-B4ibyKf1dUPBdbmKgAN9LX-s) <br/>
</div>

> **5 -** To open the STM32CubeMX graphical interface, double-click the _**ioc**_ file:

<div align="center">
	![iocfile](https://www.googleapis.com/drive/v3/files/14zD8fo-CUjGpl5tLffT9e6Tr93C_1K_w?alt=media&key=AIzaSyA3IM3FTM-B4ibyKf1dUPBdbmKgAN9LX-s) <br/>
</div>

<hr>
<br/>

<a name="cudemx"></a>
### • What or which peripherals can I change using STM32CubeMX/CubeIDE graphical interface?
<hr>

> **Answer:** Looking at STM32CubeMX/CubeIDE .ioc file, you will se which paripherals are being used. You can change **ONLY** the UART set up, selecting another one or even deleting from your project, and the GPIO which the Evaluation Board button (PB0) is using (push button examples). **ANY OTHER CHANGE** will efect the chip functionality.

<hr>
<br/>

<a name="eventmsg"></a>
### • Error: Invalid message sequence from Device #XXXXX: expected X, actual X
<hr>

> **Answer:** This is coused by the message counter. Both sides must to have the same counter, otherwise the message won't be received on SigFox Backed. <br/>
> A simple way to fix it, is disengaging the sequence number. <br/> 

> **1 -** Open the [**SigFox Backend**](https://backend.sigfox.com/) website.. <br/>
> **2 -** Click _**Device**_ tab: 

<div align="center">
	![devices](https://www.googleapis.com/drive/v3/files/1-u-sz7Adi7hbe048oZzAcpSq2Da_A5fk?alt=media&key=AIzaSyBazifvhYWroBBnEocbFpLG0mOjfUfelE4) <br/> 
</div>

> **3 -** Look for your device ID and click on it:

<div align="center">
	![deviceselect](https://www.googleapis.com/drive/v3/files/15KFeZQS8hMDV8PTi6fLRsBA-udrvvj5a?alt=media&key=AIzaSyBazifvhYWroBBnEocbFpLG0mOjfUfelE4)
</div>

> **4 -** Then click _**Disengage sequence number**_ and the counter will be reseted:

<div align="center">
	![discounter](https://www.googleapis.com/drive/v3/files/16l-_Zsxrbaaxs5n-2tsofN4xaHMi5Jjr?alt=media&key=AIzaSyBazifvhYWroBBnEocbFpLG0mOjfUfelE4)
</div>

<hr>
<br/>
