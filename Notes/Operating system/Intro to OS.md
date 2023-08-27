## Define
- program that manages the computer hardware , also provides a basis for application program and act as intermediary b/w user and computer hardware
- Type of programs :-system programs do changes to computer hardware and application program which interact with user

## Basic of OS
- modern general purpose comupter system consist of one or more CPU and number of device controller connected through a common buss that provides accesss to shared memory 
- ![[Screenshot 2023-06-07 140558.png]]
- here the horizontal line represent common bus
- eg of usb controller , like usb ports
- memory controller is provided whose function is to synchronise access to the memory 
- Some terms 
	- Bootstrap programs:- inital program that run when a computer is powered or rebooted , it must know how to load the OS and start executing that system. it must locate and load into memory the OS kernel
	- Interrupt:- occurence of an event is usually signalled by interrupt from hardware or sofware
		- hardware may trigger interrupt at any time by sending signal to CPU , usually by system bus
	- System call (monitor call):- if software trigger interrupt
	- When CPU interrupted , it stops what it is doing and immediately transfer execution to fixed location(fixed location usually contains starting address where the service routing of interrupt is located)
	- interrupt service routine execute after that CPU go back to previous work
	- service routine :- what application , hardware usually do

## Operating system services 
- OS provides enviro for execution of program , it provides certain services to program and to users of those program
1. User interface :- CLI and GUI
2. Program execution:- 