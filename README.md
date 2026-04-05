# Electronic-engineering-notes

Hello! This is a comprehensive archive of my academic lecture notes and practical engineering implementations. [WIP]

This repo will be frequently updated!

![Static Badge](https://img.shields.io/badge/Updates-active-brightgreen?style=for-the-badge) ![Static Badge](https://img.shields.io/badge/progress-5%25-orange?style=for-the-badge)

![Static Badge](https://img.shields.io/badge/ARDUINO-blue?style=for-the-badge&logo=arduino)





# Table of contents 

 1. [Embedded hardware systems with Arduino](#HardwareSystemsWithArduino)
 2. [Digital write & Pin setup ](#Digitalwrite&pinsetup)
 



  <div id='HardwareSystemsWithArduino'/>  
  
## Embedded hardware systems with Arduino
#### *The Arduino Uno R3 has:* 
-  6 Analog Input pins , labeled A0 through A5 .

- 14 Digital pins , labeled 0 to 13 , can be used as GPIO pins
 (general purpose input output).

-  6 PWM pins(Pulse Width Modulation) , Also known as Analog output , labeled 3,5,6,9,10 ,11 often characterized by the squiggly line in front of their pin number.

- 3 GND pins .
- 2 power pins, one 3.3V and the other 5V.
- One SCL and SDA pins , Serial clock  line and Serial data line. 

**Some key features:**
> - Pin 13 is connected to the built-in led.
> - 32KB of flash memory
> - max frequency of 20MHZ
<div id='Digitalwrite&pinsetup'/> 

##  Digital write & Pin setup 
Pin modes can be set inside the setup part of the code , this section runs once at the start of the code.
```cpp 
void setup(){
}
```
few ways you can set up your pin with different modes are as follows,
```cpp 
pinMode(Pin_number,OUTPUT); //set the  pin to output
pinMode(Pin_number,INPUT); //set the pin to output
pinMode(Pin_number,INPUT_PULLUP); //set the pin to act as a pull up resistor , more on it later
```
> The pin number  need not be a numerical value , it could be a variable which is an integer , same can be done with 
> ```cpp
> const int Led_pin = 10;
> pinMode(Led_pin,OUTPUT);
> //This can be done with the "digitalWrite() ;" function too
>```
 

Arduino along with many micro controllers use CMOS logic to operate (CMOS) is the standard technology used to fabricate integrated circuits (ICs), including processors, microcontrollers, and memory chips.

>(CMOS) is the standard technology used to fabricate integrated circuits (ICs), including processors, microcontrollers, and memory chips. It is used in roughly 99% of modern IC chips, including CPUs (microprocessors).

##### Acceptable CMOS level for High and low signals 
##### high: 5V - 3.5V 
##### low: 1.5V - 0V
These band allows slight variations taking into consideration , different ground levels , floating voltage ,and general noise on input lines.

-  A pin can be set as HIGH or LOW using the following
 ```cpp
 digitalWrite(Pin, HIGH); //sets pin to the 'on'state
 digitalWrite(Pin,LOW); //sets pin to 'off' state 
```




