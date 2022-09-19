# Bidirectional-visitor-counter
A bidirectional room visitor counter using schematic capture and AHDL on Intel Quartus Prime using an Altera CPLD

This bidirectional room visitor counter project uses AHDL and schematic capture to determine the number of people present in a room. It uses IR receiver diodes to track movement and 7 segment displays and LED bar array to display the number in decimal up to 99 and binary up to 128.

![IMG-2269](https://user-images.githubusercontent.com/93152842/190866955-a8e2e8e3-35f2-4f4e-ba84-285f11c20661.JPG)

*The first version of my bidirectional visitor counter! I initially used two switches on a 4 SPDT Grayhill Switch to test my inputs before switching to the IR receiver and emitter diodes.*

## Diagrams

![rvc falstad simulation image ](https://user-images.githubusercontent.com/93152842/190582340-0d055351-ac4e-408a-bbf1-7210c309ace9.png)

*A circuit simulation using the [Falstad Circuit Simulator Applet](https://www.falstad.com/circuit/). You can test the simulation [here](https://tinyurl.com/2f6r9hfl).*

Given the constraints of its implementation on Intel Quartus Prime, circuit adjustments were made for the Falstad simulation. 

I directly connected two switches to my D flip flops to test my inputs for both directions. IR receiver and emitter diodes were instead wired and debounced on the breadboard to detect movement and produce clean edges on signals. I also added 8 logic outputs after each D flip flop for the simulation to display the number of people who have passed in either direction separately. This was not done on the breadboard circuit. 

![image](https://user-images.githubusercontent.com/93152842/190941311-48dc8951-626b-4b63-8f83-2717551a8ea5.png)

*Block diagram of second version of project on Intel Quartus Prime*

The simulation's 7 segment displays automatically use hex digits to count up to FF in hexadecimal (255 in decimal). In reality, the LEDs in each common anode 7-segment display had to be custom coded using AHDL on Quartus in order to display up to 99 in decimal. In addition, JK flip flops are used in the simulation for both frequency counters. In the Quartus block diagram, master slave JK flip flops were used to account for the race around condition and uncontrolled toggling in normal JK flip flops.
