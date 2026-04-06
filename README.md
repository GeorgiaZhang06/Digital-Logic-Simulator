# Digital-Logic-Simulator
Interactive digital logic circuit simulator for the DE1-SoC FPGA board.
*Note: In compliance with university academic integrity policies, the source code for this project is not public.*

## Project Description

This ECE243 project consists of a digital logic simulator implemented on the NIOS-Vg processor running on the DE1-SoC development board. The simulator supports both combinational and sequential logic by allowing the user to describe a circuit in a file, compile it, and load it into memory. The simulator will build the circuit, and allow the user to modify the circuit inputs by using the PS/2 keyboard. The circuit is displayed on the VGA monitor, with the wire states indicated by drawing them as red or green, and smaller combinational circuits can automatically produce a truth table.

## Project Instructions

### Circuit Description & Compilation
The circuit must be designed and described in a <NAME>.log file using the format set out below. Each gate entry must occupy its own line. 

[GATE TYPE] [INPUT 1 ID] [INPUT 2 ID] [OUTPUT ID] [X COORDINATE] [Y COORDINATE]
** When defining a MUX gate, the wire at index (INPUT 2 ID + 1) must be free. This is assigned to the select input of the multiplexer.
Drag the .log file into the Logipile.exe compiler to generate a file that converts the file to binary (as <NAME>.bin). Move the binary files to your working directory and write the file into memory location 0x40000000 using the ‘restore’ command in your GDB terminal. (e.x. restore <NAME>.bin binary 0x40000000).

### Input & Controls		
The PS2 keyboard is used to control which screen is being displayed, navigating between input wires and changing their values.

UP/DOWN KEY: Navigate selection between input wires (wire is highlighted in purple and bolded when selected).
0/1 KEY: Change value of input wire to 0/1.
ENTER KEY: Toggle the homescreen/instruction page.
T KEY: Show truth table when available. The truth table is not available for circuits sequential with latches.
KEY0: Read memory location 0x40000000 and load your new circuit onto the VGA.

### Output Displays
The VGA monitor displays the instruction page on reset or by hitting ‘ENTER,’ the circuit during normal operation, or the truth table by hitting ‘T.’
The HEX display shows “notbl” when the truth table is not available (i.e. for circuits with excessive inputs/outputs, and sequential circuits).
The LEDs show the state of the output wires based on the index of each wire.

## Video Demonstration
https://drive.google.com/file/d/1ESTE1uyXQqCyuRl-hJ5bMK6XDj0uhNtL/view?usp=sharing
