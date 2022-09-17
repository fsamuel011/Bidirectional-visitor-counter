# Bidirectional-visitor-counter
A bidirectional room visitor counter using schematic capture and AHDL on Intel Quartus Prime using an Altera CPLD

This bidirectional room visitor counter project uses AHDL and schematic capture to determine
the number of people present in a room. It uses IR receiver diodes to track movement and 
7 segment displays and LED bar array to display the number in decimal up to 99 and binary up to 128.

![IMG-2269](https://user-images.githubusercontent.com/93152842/190866955-a8e2e8e3-35f2-4f4e-ba84-285f11c20661.JPG)

*The first version of my bidirectional visitor counter! I initially used an 4 SPDT Grayhill Switch to test my inputs before switching to the IR receiver diodes.*

## Diagrams

![rvc falstad simulation image ](https://user-images.githubusercontent.com/93152842/190582340-0d055351-ac4e-408a-bbf1-7210c309ace9.png)
*A circuit simulation of my project using the [Falstad Circuit Simulator Applet](https://www.falstad.com/circuit/). You can test the simulation [here](https://tinyurl.com/2f6r9hfl).*

Flaws in the falstad simulation:
- JKFFs are used in the simulation for both frequency counters. In reality, master slave JKFFs must be used
  to account for the race around condition and uncontrolled toggling in normal JKFFs.
- The simulation's 7 segment displays automatically use hex digits to count up to FF in hexadecimal 
  (255 in decimal). In reality, the LEDs in each common anode 7-segment display will need to be 
  custom coded to display up to 99 in decimal.
