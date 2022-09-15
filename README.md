# Bidirectional-visitor-counter
A bidirectional room visitor counter using schematic capture and AHDL on Intel Quartus Prime using an Altera CPLD

Thank you for going over this project!

This bidirectional room visitor counter project uses AHDL and schematic capture to determine
the number of people present in a room. It uses IR receiver diodes to track movement and 
7 segment displays and LED bar array to display the number in decimal up to 99 and binary up to 128.

There are 3 project folders in the zip file:
- addition: my custom 8-bit adder block to add two 8-bit numbers 
- ms jk ff: my master slave jk flip flop to build both frequency counters
- room visitor counter: the main project folder. Open the project file RVC.qpf on Intel Quartus Prime.

The files inside the zip file are:
- rvc falstad simulation: The text file is for my project simulation using the online Falstad Circuit Simulator Applet 
  Open the simulation using the link: https://www.falstad.com/circuit/
- READ ME: What you're reading right now.

Flaws in the falstad simulation:
- JKFFs are used in the simulation for both frequency counters. In reality, master slave JKFFs must be used
  to account for the race around condition and uncontrolled toggling in normal JKFFs.
- the simulation's 7 segment displays automatically use hex digits to count up to FF in hexadecimal 
  (255 in decimal). In reality, the LEDs in each common anode 7-segment display will need to be 
  custom coded to display up to 99 in decimal