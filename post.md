# Lab 4: Light Detector


## Overview and Motivation

This week, we will be building a light detector! To be more specific, we will be using 2 new components, a buzzer and a photoresistor, coupled with our trusty Arduino, to create a device that emits a sound whose pitch correlates with the brightness of the light shined on the photoresistor. By the end of this lab, hopefully you will get to know more about our new components, and be able to build this device yourself.

Activities:
1. Getting to know the buzzer
2. Getting to know the photoresistor
3. Building our light detector

## Materials
1. PB-503 Breadboard

2. Photoresistors

3. Buzzer

4. Arduino

5. 1kΩ resistor

## Project Steps

### 1. Understanding Lab Equipment

Before we start, we should discuss the new equipment we are using this lab, which is the photoresistor and buzzer.
#### a. Buzzer

A buzzer is a basic actuator that induces a physical change in the surrounding environment by generating a controlled sound through a series of pulses sent to the buzzer. The buzzer consists of two input pins, identified as + and -. Inside the buzzer, there is a metallic membrane. In its inactive state, with no voltage applied across the input pins, the membrane is contracted (bubbled in). When a 5-volt difference is applied across the input pins, the metallic membrane transitions to an excited state (bubbled out). The shift between the rest state and the excited state, or vice versa, results in an audible click. By rapidly alternating the voltage, we can make the buzzer to emit a tone, where the frequency of vibration determines the pitch of the tone.

#### b. Photoresistor
Photoresistors measures light brightness. It is a type of resistor that adjusts its resistance based on the level of brightness on its surface.

### 2.Building our light detector

Now that we have had a basic grasps of what our components do, it's time to build the circuit! The first step is to wire our photoresistor. We will wire one end of the photoresistor to a 1kΩ resistor, which then goes to +5V. The other end of the photoresistor will go to ground. You will need to leave a gap between the 1kΩ resistor and our photoresistor, as that is where we will wire the input to our Arduino (in other words, don't wire them into 2 adjacent pins). In this gap, we will plug a wire, which will go to the analog input A0 of our Arduino. The Arduino serves to translate the resistance value to a tone frequency for our buzzer, such that the more brightness we shine on the photoresistor, the higher pitched the buzzer sound is. Next, we will wire the buzzer. To connect the buzzer, we must ensure that the + (positive) pin of the buzzer is in the higher row and the - (negative) pin is in the lower row. Connect the - (negative) pin of the buzzer to the ground (GND) on the breadboard, then connect the other end of the + wire to pin 13 on the Arduino. Finally, make sure that your Arduino's GND is wired to the breadboard's ground.

So how exactly does the Arduino convert brightness into tone frequency? With the code snippet below:

```
#define V_PIN 0
#define BUZZER 13

void setup() {
  Serial.begin(9600);
  pinMode(V_PIN, INPUT);
}

void loop() {
  int val = analogRead(V_PIN);
  Serial.println(val);
  int freq;
  if (val < 100) {
    freq = 880;
  } else if (val < 120) {
    freq = 783;
  } else if (val < 140) {
    freq = 698;
  } else if (val < 180) {
    freq = 659;
  } else if (val < 400) {
    freq = 587;
  } else if (val < 700) {
    freq = 523;
  } else {
    freq = 493;
  }
  tone(BUZZER, freq);
  delay(500);
}

```

This code is actually simpler than the code from our previous labs. It reads the analog signal from the photoresistor, which is a number from 0 to 1023. Then, based on the value read, a specific frequency in Hz (```freq```) will be set. If the number looks odd to you, don't worry: They are frequencies of notes on a major scale, so that our buzzer sounds a bit nicer. After determining the tone frequency, the ```tone()``` functions makes the buzzer emit a sound at that frequency.

## Testing


https://github.com/mlcourses/lab-4-blog-post-csmith2025/assets/112486168/7900f448-1c40-40d7-93df-06eb00df8435


## Conclusion

This Light Detector project successfully utilized a photoresistor and a buzzer with an Arduino to create a system where the emitted sound's pitch correlates with the brightness of the light. The project involved understanding the new lab equipment (the photoresistor and buzzer), building a circuit connecting the photoresistor and buzzer to the Arduino, and implementing code for tone generation based on light levels. We hope that you have learned something new today about sensors and actuators, and please give it a go if you can!


