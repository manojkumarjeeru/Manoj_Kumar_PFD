# A Novel Phase Frequency Detector for a High Frequency PLL
In this project I have implemented new phase frequency detector (PFD) which use only 10 transistors, whereas a conventional PFD uses 54 transistors. Prototype has been designed in Synopsys Custom Compiler  and implemented using 28nm technology with a supply voltage of 1.05V .The reset process has been completely removed in this design thereby eliminating the dead zone and speeding up the acquisition process reducing the delay in circuit. The design has been proposed for high speed, low power and low jitter applications. 

# Table of Contents 
1. [Introduction](#Introduction) 
2. [Circuit Design and Details](#Circuit-Design-and-Details) 
3. [Circuit Operation](#Circuit-Operation) 
4. [Simulation Waveforms](#Simulation-Waveforms) 
5. [Netlist](#Netlist)
6. [Conclusion](#Conclusion) 
7. [References](#References) 
8. [Acknowledgement](#Acknowledgement) 
9. [Author](#Author) 

## Introduction 
PLL circuits have a wide range of uses in modern communications, including
radios, telephones, cellular devices, Computers, as well as other devices. In mobile or
wireless communications, PLLs have many uses like synchronisation, clock synthesis,
and reducing jitter (Variation from its ideal position).

The power consumption in the PFD contributes to a significant part of the total power consumption of a PLL.
Therefore overall power consumption in a PLL can be reduced by minimizing the power consumption in PFD. The
main challenge in the design of PFD is to obtain very high operating frequency with minimal power dissipation. In this paper a novel PFD architecture is
proposed which is completely free from dead zone, dissipates very low power and operates at high frequency is given

## Circuit Design and Details 
![hack_4](https://user-images.githubusercontent.com/72538560/156032830-b93dff2e-d9d4-4770-bda5-49a0c96dcb31.png)

The Circuit Design consists of Two D-Flip Flops without reset .The design  design concentrates on eliminating reset delay so that the dead zones are completely
removed.The reset path is eliminated by adding pass transistor logic.Also, The design uses only 10 transistors which reduces power consumpumtion and overall area of the PLL Circuit compared to conventional PLL.
#### Symbol Of The Schematic
![hack_3](https://user-images.githubusercontent.com/72538560/156042098-5ff17e58-3fbd-4f99-a517-b38bacdef905.png)

Also,the testbench schematic used for the simulation of transient analysis is given. Here, we have provided a dc voltage of 1.05V as power supply and two voltage pulses namely clkref and clkvco where the later is lagging by 3ns from the clkref. We have obtained the output waveforms UP and DOWN which are shown later.

![hack_2](https://user-images.githubusercontent.com/72538560/156042981-e15ee473-f861-499c-946c-9280d2fac99d.png)

## Circuit Operation
![explanation](https://user-images.githubusercontent.com/72538560/156037554-811cdf36-3c28-4f8c-ad4c-9323ae9f17bf.png)

Initially the CLKref and CLKvco signals are at logic zero. At the rising edge of CLKref, N1, N4 and N5 turns on and the UP signal goes to logic high. At the
rising edge of CLKvco, N2, N3 and N6 turn on forcing DN to go high. When both UP and DN are high, the logic
levels at points A and B in Fig. 3 are pulled down to logic zero making UP and DN to go to logic zero without any
delay for reset. 

## Simulation Waveforms 
Transient Response Analysis for the proposed circuit is shown below . From the fig it is clear that we provided a delay between both the inputs, when CLKvco is
lagging CLKref by 3ns, the UP signal goes high and vice-versa .Also,whenever both are high immediately both UP and DN signal go
down. The operational waveforms are similar to that of conventional PFD.
![waveform](https://user-images.githubusercontent.com/72538560/156040612-88e9244c-62eb-40bf-ae18-12aaeb03f2eb.png)

## Netlist
[netlist.txt](https://github.com/manojkumarjeeru/A-Novel-Phase-Frequency-Detector-for-a-High-Frequency-PLL-/files/8161429/netlist.txt)



## Conclusion 
The proposed PFD is completely free from Dead Zone and the Reset time of the PFD is Zero.
Also this PFD uses only 10, whereas a conventional PFD uses 54 transistors. Maximum operating frequency of PFD1 is
 higher than other PFDs. It can also be seen that power dissipation is reduced by
 and area is saved when compared with conventional PFD. The Power dissipated by the circuit is calculated and shown below.
 
![power](https://user-images.githubusercontent.com/72538560/156043913-5253712d-9a7f-4473-b384-01f7f98ecbac.png)

![power1](https://user-images.githubusercontent.com/72538560/156044744-d03dce3f-4e93-412a-950b-a252555a6689.png)

we have obtained a power dissipation about 48.6n Watts which is very less compared to the the conventional PFD which uses more transistors.



## References 
Abdul Majeed K and Binsu J Kailath, "A Novel Phase Frequency Detector for a High Frequency PLL
Design ",International Conference On DESIGN AND MANUFACTURING, IConDM 2013 
, ( 2013 ) 377 – 384. 

## Acknowledgement 
Kunal Ghosh,Co-founder of VLSI System Design Corporation Pvt. Ltd;

Cloud Based Analog IC Design;

Synopsys India

## Author 
Manoj Kumar Jeeru, Final Year B.TECH, ECE, Indian Institute of Information Technology,Design and Manufacturing,(IIITDM) Kancheepuram Email: jmkreddy2001@gmail.com
