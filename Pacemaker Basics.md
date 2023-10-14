___
Pacemakers are Embedded Systems
- Embedded System- Any hardware that is controlled by software. The system (hardware+software) is "embedded" into the part of the real-world that it controls, and it cannot be removed or altered.
### Diagram of Embedded System

![[Embedded System Block diagram.png]]
- Embedded Computer: in our case it is the pulse generating device [[Pacemaker Shield]]
- Software: The instructions controlling the embedded computer. We implement
	- [[Pacemaker Basics#Operating modes]]
	- Communication protocol between embedded computer and [[DCM]] 
- User Interface: [[DCM]]
- Input Variables: The way that the pulse generator can sense the heartbeat. It is the physical connection between pacemaker leads and the [[Heart Basics#Cardiac Conduction System]]
- Output variables: The way that the pulse generator sends stimulus to the heart. It is also the connection between pacemaker leads and the CCS.
- Link to other systems: NONE

### Microcontroller

We use FRDM-K64F microcontroller for this pacemaker.
![[Internal Block Diagram of K64F.png]]
- PSU: supply power to micro via USB
- Reset: reset signal when power is asserted
- Oscillator: clock
- Program Memory: code to be executed by micro
- Data memory: data gathered and manipulated during execution
- Timer: measures clock cycles/elapsed time
- Serial Comm Ports: interface for serial communication, we will use this to talk to [[DCM]]
- Interrupt Controller: reports when event ("interrupt") occurs.
- Parallel Ports: aka GPIO, see below figure for #Pinout 
![[Pinout of micro.png]]
- System Application Specific Circuit: ???
- Other Peripherals- we will use the onboard accelerometer for activity levels
- IO interface driver circuits: A driver circuit controls other circuits, and is connected to GPIO. in this case, our driver circuit is [[Pacemaker Shield]].
### Operating modes
