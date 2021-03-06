# Two_input_NAND_gate
Design and Analysis of two input NAND gate in 28nm CMOS technology using synopsys custom compiler™️
## Table of Contents
* [Abstract](#Abstract)
* [Tools used](#Tools-used)
* [Reference circuit diagram](#reference-circuit-diagram)
* [Reference circuit waveform](#reference-circuit-waveform)
* [Circuit designing](#circuit-designing)
  * [Schematic](#schematic)
  * [Symbol](#symbol)
* [Test Bench](#test-bench)
  * [Test Bench Schematic](#test-bench-schematic) 
  * [Params set for input voltage source A](#params-set-for-input-voltage-source-A)
  * [Params set for input voltage source B](#Params-set-for-input-voltage-source-B)
  * [Model files inclusion](#Model-files-inclusion)
  * [Transient Settings](#transient-settings)
  * [waveform](#waveform)
  * [Netlist](#netlist)
  * [Primewave Definition](#primewave-definition)
  * [Primewave Log File](#primewave-log-file)
* [Conclusion](#conclusion)
* [Acknowledments](#acknowledgements)
* [Author](#author)
* [References](#references)

## Abstract
The breadth of the work is to design a two input NAND gate 
in 28nm CMOS technology[1] on Synopsys Custom Compiler platform. 
In Digital Electronics, a NAND gate is logic circuit which 
outputs a logic high if one of the inputs is logic low. Other 
basic gates such as AND, NOT etc can be designed using a 
NAND gate as it is the series combination of an AND gate 
& OR gate. Due to this reason, it is called an UNIVERSAL gate

## Tools used
* Synopsys Custom Compiler™️
* Synopsys Primewave Simulator™️

## Reference circuit diagram
<!-- ![reference circuit diagram](https://user-images.githubusercontent.com/100553237/155942025-0ff30c89-8c37-4568-a0b4-ad14da77914a.png)-->
<img src="https://user-images.githubusercontent.com/100553237/155942025-0ff30c89-8c37-4568-a0b4-ad14da77914a.png" width="550" height="450">

## Reference circuit waveform
<!-- ![Reference circuit waveform](https://user-images.githubusercontent.com/100553237/155942374-ce4c7dfc-6e9a-48de-9f05-7ced04e23dac.png)-->
<img src="https://user-images.githubusercontent.com/100553237/155942374-ce4c7dfc-6e9a-48de-9f05-7ced04e23dac.png" width="750" height="500">


## Circuit Designing
* **Schematic Diagram** 
   - Before we create a schematic of the circuit, We should create a library so as to create a schematic view of the required circuit.
   - Use the bind key 'w' for wire connections, 'l' to create the labels, 'p' to assign the pins to the inputs and outputs.
   - After a schematic view is created, we have to design the circuit by importing the required mosfets from the tech library.
   
![NAND_GATE_schematic](https://user-images.githubusercontent.com/100553237/155943109-b0b2b8a9-045d-4934-b5e2-5e4cdd83386c.png)

* **Symbol**
   - After the schematic is being created, we need to build a symbol of the circuit so as to use the circuit in any other circuit and not to repeat the process of building the circuit from the scratch.
   - To build the symbol, go to _Design->New CellView->From CellView_ or simply use the _bind key 'Y'_ and you will see the below table.
   
   - ![symbol](https://user-images.githubusercontent.com/100553237/155980257-8222f055-822e-4d31-b582-4a767b6a138c.jpg)
   - After clicking OK, you will see the following symbol of the nand gate circuit.

![NAND_GATE_symbol](https://user-images.githubusercontent.com/100553237/155943162-87c62fa7-0e2a-40cc-92af-adca28ba4346.png)


## Test bench
* **test bench schematic**
   - Now that we have created the symbol, we need to connect to the circuit to the required components i.e, voltage sources, clock pulses, output capacitor and ground.
   - By making use of the analog library, we need to import the above mentioned components.
   - You can see below the voltage, rise time, fall time, pulse width and time period of the clock pulse applied to one of the inputs.
 
### Params set for input voltage source A
![a_params](https://user-images.githubusercontent.com/100553237/155966093-b0dba843-ed76-4cb7-877c-c16b3927fea5.jpg)

   - You can see below the voltage, rise time, fall time, pulse width and time period of the clock pulse applied to another input.
 
### Params set for input voltage source B
![b_params](https://user-images.githubusercontent.com/100553237/155943531-5e11044d-1853-4b4d-9537-6dee876e8701.png)
 
   - After the output capacitor and ground connections are made, the circuit looks like below.

![NAND_GATE_TB_schematic](https://user-images.githubusercontent.com/100553237/155943774-03d05755-f47c-4e58-aa03-78c603ec5b6d.png)


* **PrimeWave definition**
   - After the circuit is built without any connection errors, we need to import the model library files to perform the simulation.
   - Go to _Tools->PrimeWave_ and you will see the below table. 
![prime_wave_window](https://user-images.githubusercontent.com/100553237/155970189-db22c668-9c62-4caf-893f-d0e90d1970ad.jpg)

* **Model files inclusion**
   - Click on the Model Files.   
   
![model_file_inclusion](https://user-images.githubusercontent.com/100553237/155970354-bbe9cc2d-859a-46aa-87ac-3d2608fc2b36.jpg)

   - You can see that we have included the path for the hspice files and that we are checking the design for the TT corner but not for
     SS or FF corner.

* **Transient Settings**
    - After the corner is being mentioned, we need to mention the transition time.
<img src="https://user-images.githubusercontent.com/100553237/155984278-38e6ee28-5bf2-4bda-8785-70451e9864d1.jpg" width="750" height="500">

* **waveform**
    - Post everything is given as the input, we need to go to _'Simulation->Netlist and Run'_ or use _'Ctrl+Shift+R'_.
    - So the waveform with the input values will be created and netlist will be generated
<!-- [waveform](https://user-images.githubusercontent.com/100553237/155943842-0f44b1f1-bfa7-4651-9bf5-39883a76e179.png)-->
<img src="https://user-images.githubusercontent.com/100553237/155985569-d8c3a054-f6d0-4ca8-a34a-6589dbd1f756.png" width="750" height="350">
<!--![waveform](https://user-images.githubusercontent.com/100553237/155995458-b0dacea6-7b97-4f54-8b4c-6ec87f597414.png)-->


* **Netlist**
    - To access the netlist, go to _'Simulation->Netlist'_, you can see the netlist for this circuit.
<!--[primesi](https://github.com/psudheerk/Two_input_NAND_gate/files/8152118/primesim.txt)-->
```
*  Generated for: PrimeSim
*  Design library name: NAND_GATE
*  Design cell name: NAND_GATE_TB
*  Design view name: schematic
.lib 'saed32nm.lib' TT

*Custom Compiler Version S-2021.09
*Wed Feb 23 19:36:31 2022

.global gnd!
********************************************************************************
* Library          : NAND_GATE
* Cell             : NAND_GATE
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt nand_gate a b gnd_1 vdd vout
xm1 vout b vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm0 vout a vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm3 net13 b gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm2 vout a net13 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
.ends nand_gate

********************************************************************************
* Library          : NAND_GATE
* Cell             : NAND_GATE_TB
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
xi0 a b gnd! net14 vout nand_gate
v1 net14 gnd! dc=1.8
v3 b gnd! dc=0 pulse ( 0 1.8 0 0.1u 0.1u 15u 30u )
v2 a gnd! dc=0 pulse ( 0 1.8 0 0.1u 0.1u 5u 10u )
c4 vout gnd! c=1p

.tran '0.1u' '30u' name=tran

.option primesim_remove_probe_prefix = 0
.probe v(*) i(*) level=1
.probe tran v(a) v(b) v(vout)

.temp 25

.option primesim_output=wdf

.option parhier = LOCAL

.end
```

* **PrimeWave Log file**
     - Post simulation, the log file will be generated and can be viewed for the purpose of debug.
```
                                   PrimeSim 

                 Version S-2021.09 for linux64 - Aug 26, 2021 

                    Copyright (c) 2003 - 2021 Synopsys, Inc.
   This software and the associated documentation are proprietary to Synopsys,
 Inc. This software may only be used in accordance with the terms and conditions
 of a written license agreement with Synopsys, Inc. All other use, reproduction,
   or distribution of this software is strictly prohibited.  Licensed Products
     communicate with Synopsys servers for the purpose of providing software
    updates, detecting software piracy and verifying that customers are using
    Licensed Products in conformity with the applicable License Key for such
  Licensed Products. Synopsys will use information gathered in connection with
    this process to deliver software updates and pursue software pirates and
                                   infringers.

 Inclusivity & Diversity - Visit SolvNetPlus to read the "Synopsys Statement on
            Inclusivity and Diversity" (Refer to article 000036315 at
                        https://solvnetplus.synopsys.com)
---------------------------------------------------------------------------------

PrimeSim SPICE S-2021.09 RHEL64  (Compiled on Aug 26 2021 at 14:29:28 (US-Pacific)) build id: 7232578

Hostname: snps-analog-group-17, Username: sudheercbit305, PID: 16479
Tool Path: /Applications/Synopsys/Install/primesim/S-2021.09/primesim/platform/linux64/primesim_spice

**** Environment Variables
(NAME)               (VALUE) 
LD_LIBRARY_PATH      /Applications/Synopsys/Install/primesim/S-2021.09/lib/linux64:/Applications/Synopsys/Install/primesim/S-2021.09/python/linux64/lib:/Applications/Synopsys/Install/customcompiler/S-2021.09/linux64/platform/lib/python-2.6:/Applications/Synopsys/Install/customcompiler/S-2021.09/linux
64/lib/freeType:/Applications/Synopsys/Install/customcompiler/S-2021.09/linux64/platform/lib:/Applications/Synopsys/Install/customcompiler/S-2021.09/linux64/lib:/Applications/Synopsys/Install/customcompiler/S-2021.09/linux64/OA/lib/linux_rhel60_64/opt:/Applications/Synopsys/Install/customcompiler/S-2
021.09/linux64/PyCellStudio/linux64/3rd/Python/lib:/Applications/Synopsys/Install/customcompiler/S-2021.09/linux64/PySide/2.6.2/lib:/Applications/Synopsys/Install/customcompiler/S-2021.09/linux64/PyCellStudio/linux64/lib:/Applications/Synopsys/Install/customcompiler/S-2021.09/linux64/PyCellStudio/lin
ux64/lib/python-38:/Applications/Synopsys/Install/customcompiler/S-2021.09/linux64/PyCellStudio/linux64/lib/python-26 
PRIMESIM             1 
PRIMESIM_HOME        /Applications/Synopsys/Install/primesim/S-2021.09 
****

OS: CentOS Linux release 7.9.2009 (Core)
CPU model name	: DO-Premium-AMD, Speed : 1999.997(MHz), Cache  (L1 64K Data, L1 64K Instruction, L2 512K Unified, )

Started at Wed Feb 23 19:36:32 2022
Command line: 	/Applications/Synopsys/Install/primesim/S-2021.09/bin/primesim /home/sudheercbit305/simulation/TestSuite11/history_2/simulation/Testbench1/PrimeSimSPICE/nominal/netlist/primesim.spi -o primesim -remove_backslash -spice -sae -inc /PDK/SAED_PDK32nm/hspice
Working Directory: /home/sudheercbit305/simulation/TestSuite11/history_2/simulation/Testbench1/PrimeSimSPICE/nominal/results

INFO! read global configuration file (/Applications/Synopsys/Install/primesim/S-2021.09/primesim.cfg)

                </PDK/SAED_PDK32nm/hspice/saed32nm.lib>

Resource Usage for Reading Netlist(self/total): 0.1/0.1 sec (cpu), 0.0/0.0 sec (elapsed), 767.4/767.4 MB

primesim_output_dc=wdf is used for .dc analysis.
primesim_output_op=wdf is used for .op analysis
primesim_output_ac=wdf is used for .ac analysis

**** Used Options:
   primesim_remove_probe_prefix = 0
   primesim_output = wdf
   parhier = local
****

**** Macro Options:
****
  Main Setting: runlvl
Resource Usage for Parsing(self/total): 0.0/0.1 sec (cpu), 0.0/0.0 sec (elapsed), 14.5/781.9 MB

Simulation mode: SPICE
License: Checked out primesim(2) successfully from :27020@178.128.123.110 

Resource Usage for License(self/total): 0.0/0.1 sec (cpu), 0.0/0.0 sec (elapsed), 2.3/784.2 MB

Elapsed checking license time: 0.0 seconds

Title: *  Generated for: PrimeSim

**** expand probe
   probe pattern 'v(*)' (level=1) matches with 6 nodes on toplevel (primesim.spi:48)
   probe pattern 'i(*)' (level=1) matches with 3 devices on toplevel (primesim.spi:48)
****

  # MOSFET   : 4
  # Capacitor: 1 (Min/Max=1e-12/1e-12) 
  # V Source : 3 (Max/Min=1.8V/0V)

  TEMP=25
Resource Usage for Circuit Elaboration(self/total): 0.0/0.1 sec (cpu), 1.0/1.0 sec (elapsed), 44.8/829.0 MB

Generating MOS models ...
  Table value up to 1.8V
  Model 4/5
  Level=54 Version=4.5
Resource Usage for MOS Model(self/total): 0.0/0.1 sec (cpu), 0.0/1.0 sec (elapsed), 2.9/831.9 MB

Building Connectivity ...
Resource Usage for Connectivity Building(self/total): 0.0/0.1 sec (cpu), 0.0/1.0 sec (elapsed), -9.0/822.9 MB

Building DB ...
Resource Usage for DB Building(self/total): 0.0/0.1 sec (cpu), 0.0/1.0 sec (elapsed), 0.0/822.9 MB

Initializing ...
Resource Usage for Initialization(self/total): 0.0/0.1 sec (cpu), 0.0/1.0 sec (elapsed), 0.0/822.9 MB

Preparing Outputs ...
  # probed signals  : 9
Resource Usage for Output Preparation(self/total): 0.0/0.1 sec (cpu), 0.0/1.0 sec (elapsed), 0.0/822.9 MB

Building Matrices ...
Resource Usage for Matrix Building(self/total): 0.0/0.1 sec (cpu), 0.0/1.0 sec (elapsed), -12.0/810.9 MB

Starting DC Initialization ...
    ic file 'primesim.ic'
  DC converged at step 1

End of DC Initialization
Resource Usage for DC Initialization(self/total): 0.0/0.1 sec (cpu), 0.0/1.0 sec (elapsed), 3.0/813.9 MB

Starting Transient Analysis ...
  Important settings:
	runlvl = 4
	tolscale = 10
    3.24us (10.7 %) at Wed Feb 23 19:36:33 2022 (1s)
    6.21us (20.6 %) at Wed Feb 23 19:36:33 2022 (1s)
    9.21us (30.6 %) at Wed Feb 23 19:36:33 2022 (1s)
   12.14us (40.4 %) at Wed Feb 23 19:36:33 2022 (1s)
   15.10us (50.3 %) at Wed Feb 23 19:36:33 2022 (1s)
   18.02us (60.0 %) at Wed Feb 23 19:36:33 2022 (1s)
   21.17us (70.5 %) at Wed Feb 23 19:36:33 2022 (1s)
   24.17us (80.5 %) at Wed Feb 23 19:36:33 2022 (1s)
   27.03us (90.0 %) at Wed Feb 23 19:36:33 2022 (1s)
   30.00us (100.0 %) at Wed Feb 23 19:36:33 2022 (1s)
    finished at 30us
    output file 'primesim_wdf/tran.tran'
    # time points: 229
End of Transient Analysis                               
Resource Usage for Transient Analysis(self/total): 0.0/0.2 sec (cpu), 0.0/1.0 sec (elapsed), 8.6/822.5 MB

Simulation ended at Wed Feb 23 19:36:33 2022

Total CPU time: 0.2 seconds (0.00 hours)
Total memory usage: peak= 831.9 MB, avg= 587.1 MB

Total elapsed time: 1.0 seconds (0.00 hours)
PrimeSim Successfully Completed at Wed Feb 23 19:36:33 2022
```

## Conclusion
Thus, the two input NAND gate is being designed and simulated with the 28nm CMOS technology using synopsys custom compile with 4 MOSFETs.

## Acknowledgements
* Mr.[Kunal Ghosh](https://www.linkedin.com/in/kunal-ghosh-vlsisystemdesign-com-28084836) Co-Founder at VLSI System Design(VSD)
* Mr.[Chinmaya Panda](https://ee.iith.ac.in/staff.html) System Administrator for VLSI Lab at IIT-Hyderabad
* Mr.[Sameer Durgoji](https://www.linkedin.com/in/sameer-s-durgoji-340b26180)
* [Synopsys Inc](https://www.synopsys.com/company/contact-synopsys/office-locations/india.html)
* [Cloud Based Analog IC Design Hackathon](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/)

## Author
 * Sudheer kumar pabbathi,Third year in Bachelor of Engineering in Electronics and Communication Engineering, Chaitanya Bharathi Institute of Electronics, Hyderabad-500075.
 
## References
* [John Wawrzynek, CMOS Implementation Technologies (feature size ~ 28nm)](https://inst.eecs.berkeley.edu/~cs150/sp12/agenda/lec/lec09-CMOS.pdf)


