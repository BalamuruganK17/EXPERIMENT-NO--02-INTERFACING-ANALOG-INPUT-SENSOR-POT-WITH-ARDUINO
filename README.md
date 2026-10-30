# EXPERIMENT-NO--02-INTERFACING-ANALOG-INPUT-SENSOR-POT-WITH-ARDUINO
# AIM:  To interface a Analog  input (angular displacement sensor POT) and scale the values up on change in the input.

# NAME: BALAMURUGAN.K
# REG NO: 212225040042
# DEPARTMENT: BE.CSE

# COMPONENTS REQUIRED:

1.      10 KΩPOT

2.      1 KΩ resistor

3.      Arduino Uno

4.      USB Interfacing cable

5.      Connecting wires

6.      LED of choice
   
# Procedure:
 Open Tinkercad → Circuits and create a new circuit.
 Drag an Arduino Uno R3 into the workspace.
 Add a breadboard.
 Add a potentiometer to the breadboard.
 Connect one outer pin of the potentiometer to 5V of Arduino.
 Connect the other outer pin to GND of Arduino.
 Connect the middle pin of the potentiometer to A0 of Arduino.
 Click Code and select Text mode.
 Enter the Arduino program to read the analog value.
 Start the simulation by clicking Start Simulation.
 Rotate the potentiometer knob.
 Observe the analog value in the Serial Monitor.
 The value should change approximately from 0 to 1023 as you rotate the potentiometer

# Algorithm:
Start
Connect the potentiometer to Arduino.
Connect the potentiometer's wiper pin to analog pin A0.
Initialize serial communication.
Read the analog voltage from A0 using analogRead().
Store the value in a variable.
Display the value on the Serial Monitor.
Rotate the potentiometer and observe the change in value.
Repeat steps 5–8 continuously.

# PROGRAM:
```C++
const int sensorPin=A0;
const int ledPin=9;
void setup(){
  pinMode(ledPin, OUTPUT);
    Serial.begin(9600);
}

  void loop() {
   int sensorValue = analogRead(sensorPin);
  
  
  int brightness = map(sensorValue, 0, 1023, 0, 255);
  
  analogWrite(ledPin, brightness);
  
  
  Serial.print("Sensor: ");
  Serial.print(sensorValue);
  Serial.print(" -> LED Brightness: ");
  Serial.println(brightness);
  
  delay(10);
}
```
# OUTPUT:
LED OFF:
<img width="1377" height="906" alt="image" src="https://github.com/user-attachments/assets/68e4ee3a-9320-451b-b00c-bdde30376b4a" />
LED ON:
<img width="1367" height="903" alt="image" src="https://github.com/user-attachments/assets/68f08ebb-a274-4dec-a1d5-1af2d1146073" />

