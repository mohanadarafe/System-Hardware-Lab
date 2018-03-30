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

## Basic Logic Function
### The 7404 Integrated Circuit
Referred as the NOT-gate, this function's output invert's the input. In other words, `F = !X`. Here is a look at the 7404 truth table & pin-out diagram.

![NOT Gate](https://i.gyazo.com/9bad38348da4ea4268e69a8eb076f0e8.png)

X | F |
:-:|:-:|
0 | `1` |
1 | `0` |




