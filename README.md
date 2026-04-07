# Electronic-engineering-notes

Hello! This is a comprehensive archive of my academic lecture notes and practical engineering implementations. [WIP]

This repo will be frequently updated!

![Static Badge](https://img.shields.io/badge/Updates-LIVE-brightgreen?style=for-the-badge) ![Static Badge](https://img.shields.io/badge/progress-15%25-orange?style=for-the-badge)

![Static Badge](https://img.shields.io/badge/ARDUINO-blue?style=for-the-badge&logo=arduino)

```diff
@@ RECENT UPDATES @@

+ Added recent updates section
+ Added section 3 , 4 , 5(ref 'table of contents')

@@ PENDING PLANNED UPDATES @@

! duty cycle logic
! lcd logic 
! servo logic


@@ PENDING WORKS @@

# complete switch case explanation
# fix error's


```


# Table of contents 

 1. [Embedded hardware systems with Arduino](#HardwareSystemsWithArduino)
 2. [Digital write & Pin setup ](#Digitalwrite&pinsetup)
 3. [Serial Monitor  & input](#serialmonitor&)
 4.  [ Switch Case function example](#switchcase)
 5. [ Analog read and analog write:](#ARAW)
 



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
 

Arduino along with many micro controllers use CMOS logic to operate (CMOS) is the standard technology used to fabricate integrated circuits (ICs), including processors, micro controllers, and memory chips.

>(CMOS) is the standard technology used to fabricate integrated circuits (ICs), including processors, micro controllers, and memory chips. It is used in roughly 99% of modern IC chips, including CPU's (microprocessors).

##### Acceptable CMOS level for High and low signals 
##### high: 5V - 3.5V 
##### low: 1.5V - 0V
These band allows slight variations taking into consideration , different ground levels , floating voltage ,and general noise on input lines.

-  A pin can be set as HIGH or LOW using the following
 ```cpp
 digitalWrite(Pin, HIGH); //sets pin to the 'on'state
 digitalWrite(Pin,LOW); //sets pin to 'off' state 
```

<div id='serialmonitor&'/> 
# Serial Monitor  & input
>The **Serial Monitor** is a built-in tool in the [Arduino IDE](https://www.arduino.cc/en/software) that acts as a virtual terminal, allowing you to send and receive text-based data between your computer and an [Arduino board](https://www.arduino.cc/en/hardware)

#### To initiate a Serial Monitor :
 ```cpp 
 void setup(){
 Serial.begin(9600);
 }
 void loop(){
 Serial.print("hi");
 }
```
> Arduino only send signals in buad 9600 , hence its important to set a Serial monitor at the right buad

#### Printing in serial monitor :
```cpp
Serial.print("Hello"); //prints in same line
Serial.println("wsg"); //prints in the next line
```

#### To get input from Serial Monitor (user input):
```cpp
int fav_number = Serial.read(); 
char inputt = Serial.read(); 
```
- Can be used in a while loop to ask for multiple inputs per loop:
```cpp
void setup(){
  Serial.begin(9600);
  Serial.println("Enter your selection :"); 
}
void loop()
{
  while (Serial.available()){
    
    while (Serial.available()) {
    char inputChar = Serial.read();
    
}
```
 <div id='switchcase'/>
  
 # Switch Case function example
> proper explanation will be added later maybe...
> This code takes a character input from user  and makes it an integer , that way we get the ASCII value

A "switch()" takes a variable input and the "case xx" checks if that variable is matching the case statement , if yes the block below the case runs 
think of it as a fancy if statement of sorts-

```diff
! note: If you forget to add "break;" in a code block, the case below it runs aswell hence we include the break statement after every code block 
```

```cpp
int select;
void setup(){
  Serial.begin(9600);
  Serial.println("Enter your selection :");
 
}

void loop()
{
  while (Serial.available()){
    
    while (Serial.available()) {
    char inputChar = Serial.read();
    int asciiValue = inputChar;
    
    switch(asciiValue){
      case 65:
      Serial.println("1)Coffee");
      break;
      case 66:
      Serial.println("2)Milk");
      break;
      default :
      Serial.println("Invalid selection");
      break;  
  }
    Serial.println("Enter your selection :");
    }}}

```
 <div id='ARAW'/>
# Analog read and analog write

- Arduino can read values from 0 to 1023 , this is because Arduino can reads in 10 bits , well at least in the terms of analog 
- However "Analog write()" can only write values up to 255 , this is because it sends in 7 bits.

```cpp
analogWrite(PIN,VALUE); //outputs onto  the specified pin , value upto 225
//'VALUE' is called "The duty cycle value" -me , more on it later
analogRead(PIN) ; // reads specified pin , accepts value upto 1023 
```
to be continued....
