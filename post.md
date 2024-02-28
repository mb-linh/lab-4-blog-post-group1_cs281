# Lab 4: Light Detector


## Overview and Motivation
This week we'll explore the way an Arduino and an embedded computer can comunicate and interact with an external eviroment including a buzzer and photoresistor to create a Light Detector that emits a sound whose pitch correlates with the brightness of the light. 

## Materials
1.PB-503



2.Photoresistors



3.Buzzer



4.Arduino


5.Computer


6.Wires



7.1kΩ resistor
## Project Steps
## 1.Understanding Lab Equipment
Before we start, we should discuss the new equipment we are using this lab which is the photoresistor and buzzer. Photoresistors measures light brightness. It is a type of resistor that adjusts its resitace based on the level of brightness on its surface. A buzzer is a basic actuator that induces a physical change in the surrounding environment by generating a controlled sound through a series of pulses sent to the buzzer.
The buzzer consists of two input pins identified as + and -. Inside the buzzer, there is a metallic membrane. In its inactive state, with no voltage applied across the input pins, the membrane is contracted (bubbled in). When a 5-volt difference is applied across the input pins, the metallic membrane transitions to an excited state (bubbled out). The shift between the rest state and the excited state, or vice versa, results in an audible click. By rapidly alternating the voltage, we can make the buzzer to emit a tone, where the frequency of vibration determines the pitch of the tone.

## 2.Building Circuit
To build this circuit we need to connect the photoresistor in series with a 1kΩ resistor and connect the other end of resistor to +5V. We also need to connect other end of photoresistor to GND. We also have to connect the photoresistor to the Arduino. We must connect the positive side of the photoresistor to analog input 0 of the Arduino.Next, we have to add the Buzzer. To connect the Buzzer, we must ensure that the + (positive) pin of the buzzer is in the higher row and the - (negative) pin is in the lower row.Connect the - (negative) pin of the buzzer to the ground (GND) on the breadboard. Connect the other end of the + wire alternately to pin 13 on the Arduino. Lastly make sure the Arduino is connected to GND. You should have three wires connected to the Aruduino.

Now lets get into the Code

```

```
## Testing


https://github.com/mlcourses/lab-4-blog-post-csmith2025/assets/112486168/7900f448-1c40-40d7-93df-06eb00df8435


## Conclusion




