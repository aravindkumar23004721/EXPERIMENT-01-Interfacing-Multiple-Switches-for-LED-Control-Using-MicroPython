# EXPERIMENT-01-Interfacing-Multiple-Switches-for-LED-Control-Using-MicroPython


 
## NAME:

## DEPARTMENT:

## ROLL NO:

## DATE OF EXPERIMENT:

## AIM

To interface multiple switches with the Raspberry Pi Pico and control LEDs using MicroPython.

## APPARATUS REQUIRED

Raspberry Pi Pico

2 Push Button Switches

3 LEDs (Light Emitting Diodes)

1 Buzzer

330Ω Resistors

Breadboard

Jumper Wires

USB Cable

## THEORY

<img width="474" height="407" alt="image" src="https://github.com/user-attachments/assets/df0155b7-5b06-4276-aad3-0e114260605d" />

## FIGURE-01: RASPBERRY PI PICO PINOUT DIAGRAM

Raspberry Pi Pico is a microcontroller board based on the RP2040 chip. It supports MicroPython, making it suitable for IoT and embedded applications. The Raspberry Pi Pico is a compact microcontroller board featuring a 40-pin layout, including power, ground, GPIO, and communication interface pins. It operates with a dual-core ARM Cortex-M0+ processor and supports MicroPython and C/C++ programming.

The power pins include VBUS (5V from USB), VSYS (1.8V to 5.5V input), 3V3(OUT) (regulated 3.3V output), and multiple ground (GND) connections. The board offers 26 multi-purpose GPIO pins (GP0 to GP28), which can be used for digital input, output, PWM, and communication interfaces such as I2C, SPI, and UART. It also features three analog-to-digital converter (ADC) pins (GP26, GP27, GP28), used for reading analog sensor values, along with an ADC_VREF pin to set the reference voltage.

For communication, I2C (SDA, SCL), SPI (MOSI, MISO, SCK), and UART (TX, RX) interfaces are mapped across different GPIO pins, allowing seamless connectivity with sensors and peripherals. All GPIO pins support PWM (Pulse Width Modulation), making it useful for motor control, LED brightness adjustment, and sound applications. The BOOTSEL button enables USB mass storage mode for firmware flashing, while the DEBUG pins (SWD interface) provide debugging capabilities. With its low power consumption, flexible GPIO options, and rich interface support, the Raspberry Pi Pico is widely used for IoT, embedded systems, robotics, and automation projects.

## WORKING PRINCIPLE

## Experiment 1A:
The LEDs are connected as outputs in any three GPIO pins.

The Buzzer connected as output in any one LED connected GPIO pins.

A MicroPython script reads the switch states and controls the LEDs accordingly.

## Experiment 1B:

The switches are connected as inputs to GPIO pins of the Pico.

The LEDs are connected as outputs.

A MicroPython script reads the switch states and controls the LEDs accordingly.

### CIRCUIT DIAGRAM
## Experiment 1A

<img width="710" height="507" alt="image" src="https://github.com/user-attachments/assets/6bc88cc6-578c-4c45-a346-17d4804816ae" />
## Figure-02 circuit diagram of digital output interface 

Connect LED 1 to GPIO 0 via a 330Ω resistor, LED 2 to GPIO 2 via a 330Ω resistor and LED 3 to GPIO 4 via a 330Ω resistor.

Connect the Buzzer positive to either one pins GPIO 0 or GPIO 2 or GPIO 4.

Connect the other terminals of the LEDs and Buzzer to GND.

## Experiment 1B

<img width="940" height="576" alt="image" src="https://github.com/user-attachments/assets/6fc9a95f-28d4-4793-bf72-f60e34877c33" />
## Figure-03 circuit diagram of digital input and output interface 


Connect switch 1 to GPIO 2 and switch 2 to GPIO 3.

Connect LED 1 to GPIO 13 via a 330Ω resistor.

Connect LED 2 to GPIO 16 via a 330Ω resistor.

Connect the other terminals of the switches to GND.

## PROGRAM (MicroPython)
''''

## Experiment 1A:





## Experiment 1B:



 

## OUTPUT

## Experiment 1A:



## FIGURE-04: CIRCUIT CONNECTION

## FIGURE-05: CODE EXECUTION OUTPUT

## FIGURE-06: LED AND BUZZER STATUS


## Experiment 1B:


## FIGURE-07: CIRCUIT CONNECTION

## FIGURE-08: CODE EXECUTION OUTPUT

## FIGURE-09: LED STATUS BASED ON SWITCH INPUTS


## RESULTS

The multiple switches connected to the Raspberry Pi Pico successfully controlled the LEDs based on their states, confirming the proper interfacing of digital inputs and outputs.

