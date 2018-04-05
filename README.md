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
Base 10 | Binary | Base 10 | Binary |
:-:|:-:|:-:|:-:|
0 | `0000` | 8 | `1000` |
1 | `0001` | 9 | `1001` |
2 | `0010` | 10 | `1010` |
3 | `0011` | 11 | `1011` |
4 | `0100` | 12 | `1100` |
5 | `0101` | 13 | `1101` |
6 | `0110` | 14 | `1110` |
7 | `0111` | 15 | `1111` |

## Basic Logic Function
### The 7404 Integrated Circuit
Referred as the NOT-gate, this function's output invert's the input. In other words, it can be written as `F = !X`. Here is a look at the 7404 truth table & pin-out diagram.

![NOT Gate](https://i.gyazo.com/9bad38348da4ea4268e69a8eb076f0e8.png)

X | F |
:-:|:-:
0 | `1`| 
1 | `0` |

Here are the pins of the NOT gate.

![NOT Circuit](https://i.gyazo.com/5559035b523ebf61a2731541c9fc3593.png)

### The 7408 Integrated Circuit
Referred as the AND-gate, this function's output equals a logic `1` if and only if the two inputs are logic 1's. Therefore, each AND-gate contains 2 inputs and 1 output. In other words, it can be written as `F = A.B`. Here is a look at the 7408 truth table & pin out diagram.

![AND](https://i.gyazo.com/948c4b0cd4f0834188206a195506333a.png)

A | B | F 
:-:|:-:|:-:
0 | 0 | `0` |
0 | 1 | `0` |
1 | 0 | `0` |
1 | 1 | `1` |

Here are the pin's of the AND gate.

![AND Pin](https://i.gyazo.com/6ead1c80c6eb1933a4e1fbfe83d9986f.png)

### The 7432 Integrated Circuit
Referred as the OR-gate, this function's output equals a logic `1` if one of the two inputs are logic 1's. Therefore, each OR-gate contains 2 inputs and 1 output. In other words, it can be written as `F = A+B`. Here is a look at the 7432 truth table & pin out diagram.

![OR](https://i.gyazo.com/6650d55c7f7db3811060f96d8ef5c421.png)

A | B | F 
:-:|:-:|:-:
0 | 0 | `0` |
0 | 1 | `1` |
1 | 0 | `1` |
1 | 1 | `1` |

Here are the pin's of the AND gate.

![OR Pin](https://i.gyazo.com/55d6f9d2fddf086de4eb43409d3075dc.png)

## The Timing Signal Generator

