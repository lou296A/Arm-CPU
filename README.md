####  ARM-CPU
The ARM-CPU is implemented using an open-source software called Issie. Issie is an application for digital circuit design and simulation, which enable the development of digital circuit at logic gate level.  
the processing unit was developed as a university project for the 1st year Electronic and Electrical/Electronic and Information Engineering course at Imperial College London.

The objective of this project was to build an efficient CPU using the ARM architecture, optimized to solve commonly occurring computing problems. As the CPU was designed at logic gate level, the feature had to be chosen carefully to achieve the best performance in the greatest number of applications for the smallest number of transistors.


It needed the following capabilities:https://github.com/lou296A/Arm-CPU/blob/master/README.md

The CPU should be working with 16-bit <br>
The ALU should support all the basic operations such as add, subtract and multiplication, shifting, XOR, AND, MOV<br>
support Floating point arithmetic using the 32-bit IEEE 754 single precision  <br>
The CPU should also support pipelining<br>
Serial communication using UART for network communication and storage.<br>
Dual-core to perform faster computation.<br>

These were successfully developed and can be seen within the repository.

# UART

The word that is to be received/transmitted needs to include 1 start bit, (of logic 0) 1 stop bit
(of logic 1) and 8 data bits. (Where the LSB of the byte is the first one to be
received/transmitted). 

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

# Dual Core CPU


# Floating-Point Arithmetic
	
	
