# System Hardware Final Report

The project designed shows the functioning behind computer's.

The topics covered will include:

- Introduction to Binary & Logic Gates
  - Commonly Used Parts
  - Logic Functions
- The Timing Signal Generator
- The Bus, Arithmetic Unit and Program Counter
- Data Registers and the Memory Address Register
- Program Memory
- The Control Signal Generator

The outcome of this project will enable one to build a computer with a CPU (central processing unit) that can do simple
instructions such as moving data from one register to another and performing simple arithmetics.
## Introduction to Binary & Logic Gates


### Breadboard
   The breadboard will be used to setup the components and all circuits. It is divides in 8 parallel coloumns and contains 5 columns that
   provides power. In fact, the breadboard is made up of two important supply connections: the `VCC` for the red
   line and the `GND` for the blue line. The holes are all connected row-by-row in lines of 5. The power supply is of `5V`.

![The breadboard](https://education.ti.com/html/webhelp/EG_Innovator/EN/content/eg_innovsys/_images/m_breadboard/breadboard_front_ti_333x221.png)

### Switches
Switches are used to enalble/disable output to control the circuit. 

### Resistors & Capacitors
Resistors are used to resist electricity. The purpose of its use is to limit flow, therefore, the LED's will not burn out. Also, the resistors are measured in Ohms. Meanwhile, the capacitors' function is to store and discharge electrical charges. There are two types of capacitors: the ceramic type & the electrolytic capacitors. For the purpose of this project experiemnt, a capacitor will only be used when building the Timing Signal Generator.

### LED's
The LED is used throughout the project to project final data and help debug any problems one may face. The brightness of the diode is relative to the amount of current. Therefore, a resistor must be wired in order to ensure the LED does not burn out.

### Lab tool's
Other laboratory tools used include wires, power supply box & wire cutters.

## Reading in Binary
Base 10 | Binary | Base 10 | Binary
:-:|:-:|:-:|:-:|
0 | `0000` | 8 | `1000`
1 | `0001` | 9 | `1001`
2 | `0010` | 10 | `1010`
3 | `0011` | 11 | `1011`
4 | `0100` | 12 | `1100`
5 | `0101` | 13 | `1101`
6 | `0110` | 14 | `1110`
7 | `0111` | 15 | `1111`

## Basic Logic Function
### The 7404 Integrated Circuit
Referred as the NOT-gate, this function's output invert's the input. In other words, it can be written as `F = !X`. Here is a look at the 7404 truth table & pin-out diagram.

![NOT Gate](https://i.gyazo.com/9bad38348da4ea4268e69a8eb076f0e8.png)

A |  F
:-:|:-:
0 | `1`
1 | `0`

Here are the pins of the NOT gate.

![NOT Circuit](https://i.gyazo.com/5559035b523ebf61a2731541c9fc3593.png)

### The 7408 Integrated Circuit
Referred as the AND-gate, this function's output equals a logic `1` if and only if the two inputs are logic 1's. Therefore, each AND-gate contains 2 inputs and 1 output. In other words, it can be written as `F = A.B`. Here is a look at the 7408 truth table & pin out diagram.

![AND](https://i.gyazo.com/948c4b0cd4f0834188206a195506333a.png)

A | B | F
:-:|:-:|:-:
0 | 0 | `0`
0 | 1 | `0`
1 | 0 | `0`
1 | 1 | `1`

Here are the pin's of the AND gate.

![AND Pin](https://i.gyazo.com/6ead1c80c6eb1933a4e1fbfe83d9986f.png)

### The 7432 Integrated Circuit
Referred as the OR-gate, this function's output equals a logic `1` if one of the two inputs are logic 1's. Therefore, each OR-gate contains 2 inputs and 1 output. In other words, it can be written as `F = A+B`. Here is a look at the 7432 truth table & pin out diagram.

![OR](https://i.gyazo.com/6650d55c7f7db3811060f96d8ef5c421.png)

A | B | F
:-:|:-:|:-:
0 | 0 | `0`
0 | 1 | `1`
1 | 0 | `1`
1 | 1 | `1`

Here are the pin's of the AND gate.

![OR Pin](https://i.gyazo.com/55d6f9d2fddf086de4eb43409d3075dc.png)

## The Timing Signal Generator

### Introduction
The timing signal generator for the computer is a clock with a cycle that repeats. It allows the computer the amount of time needed to permorm operations. Moreover, the pace of the timing signal generator allows one to dictate how fast the computer processes.

### The 555 Timer
The 555 chip is the main component used to generate a timing signal generator. It is a much smaller chip as it only has 8 chips. Moreover, the 555 timer is used due to its astable mode. The astable mode provides a signal that constantly shifts between a logic `1` and logic `0`. Here is a look at the chip and its pin-out diagram.

### The 74LS164SIPO Shift Register
The 74LS164SIPO Shift Register is used with purpose to shift contents. In fact, the job of this shift register is mainly to take a single input and shift all the contents by 1 every clock cycle. Moreover, it has 8 outputs noted Qa to Qh.

### Feedback from the Shift Register
The 555 Timer feeds the 74LS164SIPO Shift Register a clock, but, the inputs of the shift register must be determined in order to receive feedback from the timing signal generator. Therefore, in order to produce feedback, it is necessary to use a new chip called the 7420 NAND Gate. Its function is just likes its name, it will have 4 inputs and its output will be fed back to the shift register. Here is how the NAND gate looks alike:

### Assembling the Timing Signal Generator
In order to assemble everthing nicely together, refer to the 555 timer to setup the `GND` & `VCC` properly. Also, your lab technician shall give you the proper resistor and capaciors needed. It is important to mention the task the pin 4 : RST. Its function is to reset the 555 timer which is done by having it at a logic `0`. Therefore, this pin will always be connected to `VCC`. Also, the pin 3 represents the output of the timing signal generator. Hence, a LED will be connected to it. Moving on to the shift register, the outputs of the register, namely QB, QD, QF and QG, will be conected to the 7420 NAND gate. As mentionned earlier, the output of the NAND gate will be fed back to the shift register. Finally, connect the CLK from the 555 timer to the shift register and demonstrate the final output in a LED.

## The Bus, Arithmetic Unit and Program Counter

### The Data Bus
In order to efficiently spread data throughout the breadboard, the data can be spread in a bus. Namely, the bus is a set of wires that have multiple devices connected to it. With this in mind, the bus allows the data to be transfered to other columns in the breadboard. In this computer, a `4-bit` bus is used in order to spread data across the breadbaord named B0 to B3. In order to efficiently spread and control data, the first four pulses T0 to T3 are shared in the bus. Since data will be all over the place, the data registers have tristate outputs in order to avoid data interference. Hence, the output of the bus can be one of the following: logic `0`, logic`1` or `High-Z`. The high impedance insinuates that a device has no output. This is how the bus should look like on a breadboard.






