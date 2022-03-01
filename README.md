# CMOS-Differential-Amplifier-Circuit
The CMOS Differential Amplifier is designed using 28nm CMOS technology by using Synopsys Custom Compiler
 





## Contents

* [Abstract]
* [Introduction]
* [Tools used]
* [Reference circuit]
* [Differential Amplifier Design]
* [Waveforms]
* [Netlist]
* [Author]
* [Ackwedgement]
* [Reference]





## Abstract

This report presents a CMOS differential amplifier design with its corresponding A.C, D.C and Transient response. The advantage of differential operation over single ended operation is higher immunity to noise. The other advantage of differential amplifier is the increase in voltage swings. 


## Introduction

Differential amplifier is one of the fundamental building blocks of analog circuit. It is generally used as the input part of an operational amplifier. It is used to provide high voltage gain and high common mode rejection ratio. It has other characteristics such as very high input impedance, very low offset voltage and very low input bias current. Differential amplifier can operate in two modes namely common mode and differential mode. Common mode type would result zero output and differential mode type would result high output. This shall mean the amplifier has high   common mode rejection ratio. 





## Tools Used
- Synopsys Custom Compiler:  The Synopsys Custom Compiler™ design environment is a modern solution for full-custom analog, custom digital, and mixed-signal IC design. As the heart of the Synopsys Custom Design Platform, Custom Compiler provides design entry, simulation management and analysis, and custom layout editing features. This tool was used to design the circuit on a transistor level.

- Synopsys Primewave:  PrimeWave™ Design Environment is a comprehensive and flexible environment for simulation setup and analysis of analog, RF, mixed-signal design, custom-digital and memory designs within the Synopsys Custom Design Platform. This tool helped in various types of simulations of the above designed circuit.

- Synopsys 28nm PDK:  The Synopsys 28nm Process Design Kit(PDK) was used in creation and simulation of the above designed circuit.



## Reference Circuit Details-


The circuit in Fig. 1 is a conventional CMOS differential amplifier used in analog circuits. The circuit is used to provide a voltage gain, which heavily depends on the output resistance of both PMOS and NMOS transistors. The output resistance in turn depends on channel length of MOSFET’s.

![fig](https://user-images.githubusercontent.com/100422485/156125878-1b597967-5b60-4adb-be74-0bfef146fbad.png)






##  Differential Amplifier Design

* **Schematic of Differential Amplifier**


![1Schematic](https://user-images.githubusercontent.com/100422485/156125851-10075a31-fff0-4a81-a1be-48322a9217ad.png)



* **Symbol of Differential Amplifier**
 
 
![2symbol](https://user-images.githubusercontent.com/100422485/156125855-ce39e304-6703-4b0f-8e4d-c89447b31802.png)


* **TestBench of Differential Amplifier**


![3testbench](https://user-images.githubusercontent.com/100422485/156125860-f27af0a9-d665-4114-8807-64f1fed228d5.png)








## Waveforms


* **Primewavewindow**


![4Primewave window](https://user-images.githubusercontent.com/100422485/156125864-397a0af0-d8d8-4c63-93f0-6bf9db98de09.png)


* **Transient Analysis**
 
 
![6transientanalysis](https://user-images.githubusercontent.com/100422485/156125874-c0335b36-929a-461d-9404-c98c431097e8.png)


* **A.C Ananlysis**
 
 
![7acanalysis](https://user-images.githubusercontent.com/100422485/156127787-97ea63fb-ecbf-4d48-8bdc-3fda0ddcfea3.png)


* **D.C Analysis**
 
 
![8dcanalysis](https://user-images.githubusercontent.com/100422485/156125877-86928f08-1f2b-44d7-aea0-043ec826037a.png)






## Netlist


* **Netlist for Differential Amplifier**



![5netlist](https://user-images.githubusercontent.com/100422485/156125865-478dcf3e-1dae-48aa-b9fc-f1db9e11a4b4.png)



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

 
## References

-[1]	B. Razavi, “Design of Analog CMOS Integrated Circuits,” McGraw-Hill Edition, 2001.

-[2]	R. Jacob Baker, “CMOS: Circuit Design, Layout, and Simulation,”
 Wiley-IEEE Press, 2nd Edition, 2005.

