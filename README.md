# -CMOS-Differential-Amplifier-Circuit
The CMOS Differential Amplifier is designed using 28nm CMOS technology by using Synopsys Custom Compiler
 





## Contents

* [Abstract](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead#abstract)
* [Tools Used](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead#tools-used)
* [Working](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead#working)
* [SRAM Cell Design](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead#sram-cell-design)
* [Sense Amplifier Design](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead#sense-amplifier-design)![Schematic](https://user-images.githubusercontent.com/100422485/156122845-cd1fb6bc-053b-4f3f-87d5-98d3cc7863dd.png)

* [Netlist](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead#netlist)
* [Author](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead#author)
* [Acknowledgements](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead#acknowledgements)
* [References](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead#references)






## Abstract

This report presents a CMOS differential amplifier design with its corresponding A.C, D.C and Transient response. The advantage of differential operation over single ended operation is higher immunity to noise. The other advantage of differential amplifier is the increase in voltage swings. 


## INTRODUCTION

Differential amplifier is one of the fundamental building blocks of analog circuit. It is generally used as the input part of an operational amplifier. It is used to provide high voltage gain and high common mode rejection ratio. It has other characteristics such as very high input impedance, very low offset voltage and very low input bias current. Differential amplifier can operate in two modes namely common mode and differential mode. Common mode type would result zero output and differential mode type would result high output. This shall mean the amplifier has high   common mode rejection ratio. 





## Tools Used
- Synopsys Custom Compiler:  The Synopsys Custom Compiler™ design environment is a modern solution for full-custom analog, custom digital, and mixed-signal IC design. As the heart of the Synopsys Custom Design Platform, Custom Compiler provides design entry, simulation management and analysis, and custom layout editing features. This tool was used to design the circuit on a transistor level.

- Synopsys Primewave:  PrimeWave™ Design Environment is a comprehensive and flexible environment for simulation setup and analysis of analog, RF, mixed-signal design, custom-digital and memory designs within the Synopsys Custom Design Platform. This tool helped in various types of simulations of the above designed circuit.

- Synopsys 28nm PDK:  The Synopsys 28nm Process Design Kit(PDK) was used in creation and simulation of the above designed circuit.



## Reference Circuit Details-


The circuit in Fig. 1 is a conventional CMOS differential amplifier used in analog circuits. The circuit is used to provide a voltage gain, which heavily depends on the output resistance of both PMOS and NMOS transistors. The output resistance in turn depends on channel length of MOSFET’s. The gain equation of the differential amplifier in Fig. 1 can be written as
                     AV =gm1,2 ron  || rop (1)






* **Reference Design**

![Reference Circuit Diagram](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemioryRead/blob/main/Circuit%20Diagrams/reference_design.png?raw=true)

* **Reference Waveforms**

![Reference Circuit Diagram](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead/blob/main/Waveforms/wavef.png?raw=true)



##  SRAM Cell Design

The objective of SRAM cell design is to arrive at an optimal cell ratio and optimal pull up ratio. For performing a quick read operation, the cell current should be optimal so that bitline discharges within a given period of time. Signifying that the combination of passgate and pulldown should be less resistive. Also taking care of the bitline leakage when not doing any read operation, the minimum length of the technology is not used. Cell stability also becomes a very important factor so the pull downs should be Larger than the pass gate. So that the Vbump generated during read operation would be smaller than SNM and then we can accept more noise preventing any cell flip during read operation. For the same reason. Pass gates should be more resistive than pull down. Pull down should be large, but not too large. Also, the sizing of pull up devices becomes important in this case so as to complete the Write operation. To be Able to write into a cell the combination of Write driver and pass gate should be stronger than that of the pullup. Pullups are the weakest device of the SRAM cell. Pull up devices also need to be optimally sized so as to maintain the Writability and write speed of the SRAM cell. 

So, the strength of the devices is in the following order Pulldown > Passgates > Pullup. 

Length greater than minimum technology size is used to prevented any unwanted leakage.
All the simulations are performed using Synopsys 28nm PDK and at TT 25 C.

* **SRAM Circuit Diagram**

![Reference Circuit Diagram](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead/blob/main/Circuit%20Diagrams/SRAM_schematic.png?raw=true)



* **Waveforms**

* Internal Node Q/QB set to 0/1 leading to the discharge of BL.

![Reference Circuit Diagram](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead/blob/main/Waveforms/read_BL_dis.png?raw=true)


* Internal Node Q/QB set to 1/0 leading to the discharge of BLB.

![Reference Circuit Diagram](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead/blob/main/Waveforms/read_BLB_dis.png?raw=true)





* **Sense Amplifier Circuit Diagram**

![Reference Circuit Diagram](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead/blob/main/Circuit%20Diagrams/Sense_schematic.png?raw=true)


![Reference Circuit Diagram](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead/blob/main/Waveforms/read1_s.png?raw=true)


## Memory Read Operation


For demonstrating the memory read operation, 6T SRAM cell is connected to a conventional last type sense amplifier via bitlines with a load of 100 fF representing the load of a column of bitcells . First, for demonstrating read 1, Node Q of the SRAM cell is initialized to a logic 0 which results in the discharge of BL and thus the offset appears at the SAF node of the sense amplifier. As soon as SEN (Sense Enable) signal is taken high SAF node discharges and SAT node is taken to VDD resulting in DOUT node to a logic 1.

Similarly, for demonstrating the read 0 operation, QB node of the SRAM cell is initialized to the logic 0 which leads to the discharge of it BLB, Therefore the offset appears at the SAT node of the sense amplifier as soon as the SEN signal is taken high, the SAT node discharges SAF node is taken to VDD. Resulting in DOUT node of the latch to a logic 0. The DOUT node of the latch is connected to a buffer to drive a higher Output load of 10 fF. 




* **Stimulus of various Signals are given as follows**

 - Wordline:

![Reference Circuit Diagram](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead/blob/main/Stimulus/BPCH.png?raw=true)


 - Bitline Precharge:

![Reference Circuit Diagram](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead/blob/main/Stimulus/WL.png?raw=true)


 - Precharge:

![Reference Circuit Diagram](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead/blob/main/Stimulus/PCH.png?raw=true)


 - Sense Enable:

![Reference Circuit Diagram](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead/blob/main/Stimulus/SEN.png?raw=true)


* **Circuit Diagram for demonstrating Read Operation**

![Reference Circuit Diagram](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead/blob/main/Circuit%20Diagrams/Read_schematic.png?raw=true)


* **Waveforms**

* Internal Node Q/QB set to 1/0 leading to Read 0 operation.

![Reference Circuit Diagram](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead/blob/main/Waveforms/read0.png?raw=true)


* Internal Node Q/QB set to 0/1 leading to Read 1 operation.

![Reference Circuit Diagram](https://github.com/DebjitLP/CloudBased_Analog_Hackathon_MemoryRead/blob/main/Waveforms/read1.png?raw=true)


## Netlist




* **Netlist for Demostrating Read Operation**




## Author


```bash
Anandita, National Institute of Technology, Patna
```


## Acknowledgements


 - Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalpghosh@gmail.com
 - https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/
 - Synopsys India
 - [VSD VLSI System Design](https://www.vlsisystemdesign.com/)
 - Chinmay panda, IIT Hyderabad
 - Sameer Durgoji, NIT Karnataka
## References

-[1]	B. Razavi, “Design of Analog CMOS Integrated Circuits,” McGraw-Hill Edition, 2001.
-[2]	R. Jacob Baker, “CMOS: Circuit Design, Layout, and Simulation,”
 Wiley-IEEE Press, 2nd Edition, 2005.

