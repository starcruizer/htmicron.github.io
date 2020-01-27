# Frequently Asked Questions about HT32SX 

## Questions list:

• [**How do I register a new user on the SigFox Backed?**](#regbackend) <br/>
• [**How do I register a new device on the SigFox Backed?**](#regdevice) <br/>
• [**How or where can I check if my device is sending the massages correctly?**](#msgcorrec) <br/>
• [**How should I set up my new device to operate in my current region?**](#configrc) <br/>
• [**How many messagens can I send daily?**](#dailymsg) <br/>
• [**How long should I wait between sending two messages?**](#delaymsg) <br/>
• [**Error: Invalid message sequence from Device #XXXXX: expected X, actual X**](#eventmsg) <br/>

## Answered Questions:

<a name="regbackend"></a>
### • How do I register a new user on the SigFox Backed?

<hr>
> **Answer:** It's recommended to contact your local SigFox Provider and ask for an new account. If It did not help you, contact our Support Team sending an email to support_iot@htmicron.com.br.
<hr>

<br/>

<a name="regdevice"></a>
### • How do I register a new device on the SigFox Backed?
<hr>

> **Answer:** If you already have an account, check the following steps below, otherwise check the [**Account Registration**](#regbackend) topic.<br/> 

> **1 -** Open the [**SigFox Backend**](https://backend.sigfox.com/) website. <br/>
> **2 -** Click on _**Device**_:

<div align="center">
	![devices](https://www.googleapis.com/drive/v3/files/1-u-sz7Adi7hbe048oZzAcpSq2Da_A5fk?alt=media&key=AIzaSyBazifvhYWroBBnEocbFpLG0mOjfUfelE4) <br/> 
</div>

> **3 -** Then click on _**New**_ to register a new device:

<div align="center">
	![new](https://www.googleapis.com/drive/v3/files/1p1YuczQEaY9rl7sMq3Bg4l-FvM9OVs5w?alt=media&key=AIzaSyBazifvhYWroBBnEocbFpLG0mOjfUfelE4)  <br/> 
</div>

> **3 -** Select a group.

<div align="center">
	![group](https://www.googleapis.com/drive/v3/files/1ZaWI1HwtjCZa_cMn_b2HwYKeQ6LvDJ69?alt=media&key=AIzaSyD0vizVRI4gcudGwFjpVAbRKDtjUcs-KDk)
</div>

> **4 -** Fill the underlined fields with your device ID & PAC, and choose a name for this new device.

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
> **2 -** Click on _**Device**_:

<div align="center">
	![devices](https://www.googleapis.com/drive/v3/files/1-u-sz7Adi7hbe048oZzAcpSq2Da_A5fk?alt=media&key=AIzaSyBazifvhYWroBBnEocbFpLG0mOjfUfelE4) <br/> 
</div>

> **3 -** Look for your device ID and click on it:

<div align="center">
	![deviceselect](https://www.googleapis.com/drive/v3/files/15KFeZQS8hMDV8PTi6fLRsBA-udrvvj5a?alt=media&key=AIzaSyBazifvhYWroBBnEocbFpLG0mOjfUfelE4)
</div>

> **4 -** Then click on _**Messages**_ and all messages received from that ID will be shown:

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

<a name="eventmsg"></a>
### • Error: Invalid message sequence from Device #XXXXX: expected X, actual X*
<hr>

> **Answer:** This is coused by the message counter. Both sides must to have the same counter, otherwise the message won't be received on SigFox Backed. <br/>
> A simple way to fix it, is disengaging the sequence number. <br/> 

> **1 -** Open the [**SigFox Backend**](https://backend.sigfox.com/) website.. <br/>
> **2 -** Click on _**Device**_ tab:

<div align="center">
	![devices](https://www.googleapis.com/drive/v3/files/1-u-sz7Adi7hbe048oZzAcpSq2Da_A5fk?alt=media&key=AIzaSyBazifvhYWroBBnEocbFpLG0mOjfUfelE4) <br/> 
</div>

> **3 -** Look for your device ID and click on it:

<div align="center">
	![deviceselect](https://www.googleapis.com/drive/v3/files/15KFeZQS8hMDV8PTi6fLRsBA-udrvvj5a?alt=media&key=AIzaSyBazifvhYWroBBnEocbFpLG0mOjfUfelE4)
</div>

> **4 -** Then click on _**Disengage sequence number**_ and the counter will be reseted:

<div align="center">
	![discounter](https://www.googleapis.com/drive/v3/files/16l-_Zsxrbaaxs5n-2tsofN4xaHMi5Jjr?alt=media&key=AIzaSyBazifvhYWroBBnEocbFpLG0mOjfUfelE4)
</div>

<hr>
<br/>
