# Computer Architecture Design Project: DualCore ARM CPU 
## introduction
ARM-CPU is part of 1 year module (Digital Design and Computer Architecture) and then extended to a group project. The CPU was implemented using Issie. [Issie](https://github.com/tomcl/issie) is an application for digital circuit design and simulation, which enable the development of digital circuit at logic gate level.  

The objective of this project was to build an efficient CPU using the ARM architecture, optimized to solve commonly occurring computing problems. As the CPU was designed at logic gate level, the feature had to be chosen carefully to achieve the best performance in the greatest number of applications for the smallest number of transistors.

This README aim to give a high level overview of the cpu implementation, for more details you can access refer to the full report.Bare in mind that this was one of my first report as student (Fortunetely the quality of my reports have improved over time).   


### Specification	
- 16 bits Word CPU
- Support basic operation: add, subtract and multiplication, shifting, XOR, AND, MOV
- 16 and 32-bit Floating point arithmetic 
- Pipelined
- Serial communication using UART for network communication and storage.<br>
- Dual-core 

These were successfully developed and can be seen within the repository.

## UART

The word that is to be received/transmitted needs to include 1 start bit, (of logic 0) 1 stop bit
(of logic 1) and 8 data bits. (Where the LSB of the byte is the first one to be
received/transmitted). 
![Uart-architecture](https://github.com/lou296A/Arm-CPU/blob/master/Pictures/UART_overallarch.png)
Since the UART is built to receive/transmit data sequentialy , for this implementation we
must take into consideration that the rate of transmission will be 1 bit per 4 clock cycles.
In addition, we need to implement a way for the CPU to be able to recognise if:
- a byte has been received since the receive register was last read by the CPU.
- a transmission is in progress.
- there was a receive overflow. (a byte was received before the previous byte was
read by the CPU)
-  there was a transmit overflow. (a byte was written by the CPU before the previous
byte had finished transmission)

-
The advanced portion of this implementation is to add an interrupt function, which is
explained in greater detail later.


### UART interface
The UART was implemented as a memory map. We decided to follow the suggestion, given
by the instruction set, even thought we could have chosen different addresses. 
![UART_memory](https://github.com/lou296A/Arm-CPU/blob/master/Pictures/uart_memorymap.png)

## Dual Core CPU
#overall archicte
![dual_core architecture](https://github.com/lou296A/Arm-CPU/blob/master/Pictures/Dualcore_arch.png)

## Floating-Point Arithmetic
	
	
