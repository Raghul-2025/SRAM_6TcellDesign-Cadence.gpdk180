# SRAM - Single Bit Storage using 6T Cell
  A complete overview on the design of SRAM( using 6T cell ) and on the working of how it stores a bit. This Repo gives the clear working of Precharge circuit, 6T Cell, Write Driver ,Sense Amplifier and tells how they together works as an integrated circuit.

## Content :-
1. Introduction on 6T SRAM
2. Architecture of 6T Cell
3. Precharge Circuit
4. Write Driver
5. Sense Amplifier
6. Write and Read Operation
7. Timing Analysis

## Overview of SRAM built using 6T cell which stores a Single bit
  SRAM is nothing but the *Static Random Access Memory* and in this, I built a SRAM which stores a single bit using 6T cell which means **six transistors** are connected to make the storage element of the circuit. It can also be built using 8T cell and 10T cell.
  It consists of *four separate circuits* that are integrated as a single circuit to make the single bit to read and write. They are,
  - Precharge Circuit 
  - 6T cell
  - Write Driver
  - Sense Amplifier


  ### 6T cell 
  ![Schemaitc of 6T cell](./images/SRAM_6Tcell.png)
    It is the actual element where the data ie.,bit is stored. It consists of two CMOS inverters which are connected to each other in *Cross Coupled manner*, which behaves like a latch. The two CMOS inverters forms the fours transistors of six and the remaining two are called as *Access Transistors* that are the connecting units of the 6T cell, that decides whether the storage element( latch - two cross coupled inverters) is available for read and write or disconnected. The gates of two access transistors are connected together and labelled as *Wordline* which is responsible for connecting and disconnecting the 6T cell from the external circuits(Precharge circuit, Write Driver & Sense amplifier). The Bit line and Bit line bar(The bar is just given for name sake, they are not need to be in complement always) are connected to the access transistors, based on the variations in their values the sense amplifier reads the data stored.

  ### Precharge Circuit
  ![Schematic of Precharge Circuit](./images/SRAM_PreChargeCircuit.png)
    It is the circuit that charges the Bit line and the Bit line bar to VDD(lets say 1.8 V) before every read operation and write operation. It consists of three PMOS transistors - two transistors to connect and disconnect the Bit line and the Bit bar line to vdd and the another transistor called *Equalizer transistor* that confirms the condition that both the bit and bit line bar are equal in voltage before performing any operation, beacuse the any difference in the voltage may disturb the read and write operation. The precharge circuit is made of PMOS not NMOS because PMOS transistors are good at pulling nodes UP toward VDD. They are called pull up transistors. And, here PC is the control input of the precharge circuit, when it's high(ie., logic 1 or 1.8V), all the PMOS stays off, so the bit line and the bit bar line gets disconnected from the precharge circuit and when the is low(ie., logic 0 or 0V) all the PMOS gets on, So the bit line and the bit line bar connected to the precharge circuit and gets charged to VDD. Here, *Bit line and the Bit bar line has the Parasitic Capacitance*, which makes them to stay with VDD even after the precharge circuit is disconnected, which is the key speciality for read and write operation. 

  ### Write Driver
  ![Schematic of Write Driver](./images/SRAM_WriteDriver.png)
    It is the circuit that writes the data into the 6T cell by means of bit line and bit line bar. It has a control input called Write Enable that connects and disconnects the bit line and the bit bar line from the Write Driver. When write enable is high write operation is performed with the input data given as Datain, and when the write enable is low the write driver is disconnected from the bit line and the bit bar line. 

  ### Sense Amplifier
  ![Schematic of Sense Amplifier](./images/SRAM_SenseAmplifier.png)
    Sense Amplifier is one kind of amplifier circuit, that amplifies the small difference between the values of the bit line and the bit line bar to read the desired output. Here needs the clear understanding of working of transistor to know how the small difference amplifies here and read as a required output which is stored in the 6T cell. In the 6T cell, based on the data stored(either 0 or 1) there is a minor differences in the voltages of bit line and bit line bar. Here, Read enable is the control input like the Write enable which decides whether the bit lin and the bit line bar need to be connected or disconnected.

  ### SRAM design to store a single bit
  ![Schematic of the SRAM Design](./images/SRAM_SingleBitStorage.png)
  
  #### Output Waveform
  ![This shows the read and the write operation](./images/SRAM_Waveform_SingleBit.png)  
    
    

  
