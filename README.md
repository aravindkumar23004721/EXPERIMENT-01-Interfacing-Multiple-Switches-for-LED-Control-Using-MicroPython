# EXPERIMENT-01-Interfacing-Multiple-Switches-for-LED-Control-Using-MicroPython


 
## NAME: Aravind Kumar SS

## DEPARTMENT: CSE(IOT)

## ROLL NO: 212223110004

## DATE OF EXPERIMENT: 21-04-2026

## AIM

To interface multiple switches with the Raspberry Pi Pico and control LEDs using MicroPython.

## APPARATUS REQUIRED

1. Raspberry Pi Pico - 1

2. Push Button Switches - 2

3. LEDs (Light Emitting Diodes) -3

4. Buzzer - 1

5. 330Ω Resistors -3

6. Breadboard

7. Jumper Wires

8. USB Cable

## THEORY

<img width="474" height="407" alt="image" src="https://github.com/user-attachments/assets/df0155b7-5b06-4276-aad3-0e114260605d" />

## FIGURE-01: RASPBERRY PI PICO PINOUT DIAGRAM

Raspberry Pi Pico is a microcontroller board based on the RP2040 chip. It supports MicroPython, making it suitable for IoT and embedded applications. The Raspberry Pi Pico is a compact microcontroller board featuring a 40-pin layout, including power, ground, GPIO, and communication interface pins. It operates with a dual-core ARM Cortex-M0+ processor and supports MicroPython and C/C++ programming.

The power pins include VBUS (5V from USB), VSYS (1.8V to 5.5V input), 3V3(OUT) (regulated 3.3V output), and multiple ground (GND) connections. The board offers 26 multi-purpose GPIO pins (GP0 to GP28), which can be used for digital input, output, PWM, and communication interfaces such as I2C, SPI, and UART. It also features three analog-to-digital converter (ADC) pins (GP26, GP27, GP28), used for reading analog sensor values, along with an ADC_VREF pin to set the reference voltage.

For communication, I2C (SDA, SCL), SPI (MOSI, MISO, SCK), and UART (TX, RX) interfaces are mapped across different GPIO pins, allowing seamless connectivity with sensors and peripherals. All GPIO pins support PWM (Pulse Width Modulation), making it useful for motor control, LED brightness adjustment, and sound applications. The BOOTSEL button enables USB mass storage mode for firmware flashing, while the DEBUG pins (SWD interface) provide debugging capabilities. With its low power consumption, flexible GPIO options, and rich interface support, the Raspberry Pi Pico is widely used for IoT, embedded systems, robotics, and automation projects.

## WORKING PRINCIPLE

## Experiment 1A:
1. The LEDs are connected as outputs in any three GPIO pins.

2. The Buzzer connected as output in any one LED connected GPIO pins.

3. A MicroPython script reads the switch states and controls the LEDs accordingly.

## Experiment 1B:

1. The switches are connected as inputs to GPIO pins of the Pico.

2. The LEDs are connected as outputs.

3. A MicroPython script reads the switch states and controls the LEDs accordingly.

### CIRCUIT DIAGRAM
## Experiment 1A

<img width="710" height="507" alt="image" src="https://github.com/user-attachments/assets/6bc88cc6-578c-4c45-a346-17d4804816ae" />

## FIGURE-02:  Circuit Diagram of Digital Output Interface 

1. Connect LED 1 to GPIO 0 via a 330Ω resistor, LED 2 to GPIO 2 via a 330Ω resistor and LED 3 to GPIO 4 via a 330Ω resistor.

2. Connect the Buzzer positive to either one pins GPIO 0 or GPIO 2 or GPIO 4.

3. Connect the other terminals of the LEDs and Buzzer to GND.

## Experiment 1B

<img width="940" height="576" alt="image" src="https://github.com/user-attachments/assets/6fc9a95f-28d4-4793-bf72-f60e34877c33" />

## FIGURE-03:  Circuit Diagram of Digital Input and Output Interface 


1. Connect switch 1 to GPIO 2 and switch 2 to GPIO 3.

2. Connect LED 1 to GPIO 13 via a 330Ω resistor.

3. Connect LED 2 to GPIO 16 via a 330Ω resistor.

4. Connect the other terminals of the switches to GND.

## PROGRAM (MicroPython)
''''

## Experiment 1A:

from machine import Pin
import time
print("Pi Pico")
led1 = Pin(0, Pin.OUT)
led2 = Pin(2, Pin.OUT)
led3 = Pin(4, Pin.OUT)
buzzer=Pin(4,Pin.OUT)
while True:
    led1.value(1) 
    print("LED is ON")
    time.sleep(1) 
    led1.value(0)  
    print("LED is OFF")
    time.sleep(1)
    led2.value(1) 
    print("LED is ON")
    time.sleep(1) 
    led2.value(0)  
    print("LED is OFF")
    time.sleep(1)
    led3.value(1) 
    print("LED is ON")
    time.sleep(1) 
    led3.value(0)  
    print("LED is OFF")
    time.sleep(1)
    buzzer.value(1) 
    print("Buzzer is ON")
    time.sleep(1) 
    buzzer.value(0)  
    print("Buzzer is OFF")
    time.sleep(1)




## Experiment 1B:


from machine import Pin
import time import sleep 
switch1=Pin(2,Pin.IN)
switch2=Pin(3,Pin.IN)
led1=Pin(13,Pin.OUT)
led2=Pin(16,Pin.OUT)
while True:
    sw1_state=switch1.value()
    sw2_state=switch2.value()
    print("Switch 1 State", sw1_state)
    print("Switch 2 State", sw2_state)
    led1.value(0)
    if sw1_state==1 and sw2_state==1:
        led1.value(0)
        led2.value(0)
    elif sw1_state==1:
        led1.value(1)
        sleep(0.5)
        led1.value(0)
        led2.value(0)
    elif sw2_state==1:
        led1.value(0)
        led2.value(1)
        sleep(0.5)
        led2.value(0)
    sleep(0.5)

 

## OUTPUT
## Experiment 1A:
## FIGURE-04: CIRCUIT CONNECTION

<img width="768" height="583" alt="image" src="https://github.com/user-attachments/assets/b9a4f658-6231-417f-8c3e-9632a9115616" />

## FIGURE-05: CODE EXECUTION OUTPUT

<img width="1918" height="968" alt="exp-2" src="https://github.com/user-attachments/assets/94c352f6-8b82-4d7b-9e5b-25a604c0d978" />
<img width="1918" height="968" alt="3" src="https://github.com/user-attachments/assets/b5ee573d-f186-4e89-a924-add3516dacd9" />
<img width="1918" height="972" alt="4" src="https://github.com/user-attachments/assets/1ed2abb6-bdc5-49e9-a62d-597937109c68" />

## FIGURE-06: LED AND BUZZER STATUS

<img width="1918" height="968" alt="5" src="https://github.com/user-attachments/assets/4ecec7bb-25b7-4874-98e7-0ecf962306db" />

## Experiment 1B:
## FIGURE-07: CIRCUIT CONNECTION

<img width="713" height="522" alt="8" src="https://github.com/user-attachments/assets/90a4ddf4-0bfd-46e5-bbee-84c093623f2c" />


## FIGURE-08: CODE EXECUTION OUTPUT

<img width="1918" height="972" alt="image" src="https://github.com/user-attachments/assets/b317afc2-a5d3-4181-a60a-458335faeed7" />

## FIGURE-09: LED STATUS BASED ON SWITCH INPUTS

<img width="1911" height="970" alt="7" src="https://github.com/user-attachments/assets/2eb52abb-e888-489d-a15b-008841218868" />

## RESULTS

The multiple switches connected to the Raspberry Pi Pico successfully controlled the LEDs based on their states, confirming the proper interfacing of digital inputs and outputs.

