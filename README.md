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

![555](https://i.gyazo.com/3063dc572aaa4130fe10cbf26a5e0828.png)

### The 74LS164SIPO Shift Register
The 74LS164SIPO Shift Register is used with purpose to shift contents. In fact, the job of this shift register is mainly to take a single input and shift all the contents by 1 every clock cycle. Moreover, it has 8 outputs noted Qa to Qh.

![74LS164SIPO](https://i.gyazo.com/d38c21f464b0e5afd6607fea2b0bc9f9.png)

### Feedback from the Shift Register
The 555 Timer feeds the 74LS164SIPO Shift Register a clock, but, the inputs of the shift register must be determined in order to receive feedback from the timing signal generator. Therefore, in order to produce feedback, it is necessary to use a new chip called the 7420 NAND Gate. Its function is just likes its name, it will have 4 inputs and its output will be fed back to the shift register. Here is how the NAND gate looks alike:

![Feedback](https://i.gyazo.com/0cd59f5379bff14faafaa528467aeef6.png)

### Assembling the Timing Signal Generator
In order to assemble everthing nicely together, refer to the 555 timer to setup the `GND` & `VCC` properly. Also, your lab technician shall give you the proper resistor and capaciors needed. It is important to mention the task the pin 4 : RST. Its function is to reset the 555 timer which is done by having it at a logic `0`. Therefore, this pin will always be connected to `VCC`. Also, the pin 3 represents the output of the timing signal generator. Hence, a LED will be connected to it. Moving on to the shift register, the outputs of the register, namely QB, QD, QF and QG, will be conected to the 7420 NAND gate. As mentionned earlier, the output of the NAND gate will be fed back to the shift register. Finally, connect the CLK from the 555 timer to the shift register and demonstrate the final output in a LED.

![Assembling](https://i.gyazo.com/63005e33b435dffd019c53bbead673c5.png)
![Schematic](https://i.gyazo.com/ce6e1e0e15d34b58db1404764cf4b827.png)

## The Bus, Arithmetic Unit and Program Counter

### The Data Bus
In order to efficiently spread data throughout the breadboard, the data can be spread in a bus. Namely, the bus is a set of wires that have multiple devices connected to it. With this in mind, the bus allows the data to be transfered to other columns in the breadboard. In this computer, a `4-bit` bus is used in order to spread data across the breadbaord named B0 to B3. In order to efficiently spread and control data, the first four pulses T0 to T3 are shared in the bus. Since data will be all over the place, the data registers have tristate outputs in order to avoid data interference. Hence, the output of the bus can be one of the following: logic `0`, logic`1` or `High-Z`. The high impedance insinuates that a device has no output. This is how the bus should look like on a breadboard.

![Bus](https://i.gyazo.com/e66e9075d62bfb58974507398342177c.png)

### Program Counter & Shift Register
The program counter of a computer holds the location of an execution to be executed. When a command executes, the Program Counter will increment by `+1` value by the data bus. This is done so the program counter can read the next instruction. In order to succefully increment the program counter, an arithmetic unit is used to do two jobs: add and shift. Primarily, a 4-bit adder (74LS283) will collect data from the data bus and increment its value by 1. In essence, PC = PC+1. Afterwards the output of the 74LS283 will proceed to a 4-bit shift register (74LS395) that will output the value back to the data bus. Have a look at the Adder & Register's pin-out diagram.

![Adder](https://i.gyazo.com/45284d2554f70e0c4cb169db8c092bab.png)
![Shift](https://i.gyazo.com/d71933199f802018a7910b8f51238109.png)

### Assembling everything together
The timing signal generator has four pulses, namely T0 to T3 used to control the two shift registers. Each have a specific function that ensure only one shift register is used at any given time. In depth, T0 is labelled as PCout, when active, the program counter can store data in the bus. T1 is labelled as SUMin, when active, the data is stored in the SUM register. T2 is labelled as SUMout, when active, the SUM register's data output is shifted to the data bus. Finally, T3 is labelled as PCin, when active, the program counter has a new incremented value. 

## Data Registers and the Memory Address Register

### Data Registers
Data registers' main purpose is to hold data in order to ease manipulation and flow of data. There are three 74LS173 4-bit registers used due to its tristate outputs. In fact, when the register's (OE) ̅ is set to a logic 1, the outputs are disconnected from the data bus setting it in high-impedance Hi-Z. When the register's (OE) ̅ is set to a logic 0, the data is sent to the bus. The first two registers, namely register A and B are used as data registers. Meanwhile, the last register is used as a MAR.

### MAR
The MAR is a Memory Address Register which provides the address of the RAM for instructions. Hence, the register obtains its data from the bus when the PC outputs its data. 

### Setting up the data registers
For now, the data register A and B's (OE) ̅  and CLK will be wired to ground. Furthermore, the CLK of the MAR will be wired to T1 from the Timing Signal Generator and its outputs will temporarily be connected to an LED for testing. The MAR's wiring will of course change but the use of LED helps keep track of data flow. The following is the pin-out diagram of the 74LS173

![Register](https://i.gyazo.com/72013c791cda526da124e95fec75763a.png)


## Program Memory

### ATTiny2313A

### 7442Binary Coded Decimal to Decimal Decoder

### Setting everything up together


