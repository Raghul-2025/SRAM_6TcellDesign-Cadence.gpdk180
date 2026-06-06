# SRAM - Single Bit Storage using 6T Cell
  A complete overview on the design SRAM( using 6T cell )and how it stores a bit. This Repo gives the clear working of Precharge circuit, 6T Cell, Write Driver ,Sense Amplifier and tells how the works in a integrated circuit.

## Content :-
1. Introduction on 6T SRAM
2. Architecture of 6T Cell
3. Precharge Circuit
4. Write Driver
5. Sense Amplifier
6. Write and Read Operation
7. Timing Analysis

## Overview of SRAM built using 6T cell which stores a Single bit
  SRAM is nothing but the *Static Random Access Memory* and in this, I built it using 6T cell which means that **six transistors** are connected to make the storage element of the circuit. It can also be built using 8T cell and 10T cell.
  It consists of *four separate circuits* that are integrated as a single circuit to make the single bit to read and write. They are,
  - Precharge Circuit 
  - 6T cell
  - Write Driver
  - Sense Amplifier


  ### 6T cell 
  ![Schemaitc of 6T cell](./images/SRAM_6Tcell.png)
    It is the actual element where the data ie.,bit is stored. It consists of two CMOS inverters which are connected to each other in *Cross Coupled manner*, which behaves like a latch. The two CMOS inverters forms the fours transistors of six and the remaining two are called as *Access Transistors* that are the connecting units of the 6T cell, that decides whether the storage element( latch - two cross coupled inverters) is availabe for read and write or disconnected. The gates of two access transistors are connected together and labelled as *Wordline* which is responsible for connecting and disconnecting the 6T cell from the external circuits(Precharge circuit, Write Driver & Sense amplifier). The Bit line and Bit line bar(The bar is just given for name sake, they are not need to be in complement always) are connected to the access transistors, based on the variations in their values the sense amplifier reads the data stored.

  ### Precharge Circuit
  ![Schematic of Precharge Circuit](./images/SRAM_PreChargeCircuit.png)
    
    

  
