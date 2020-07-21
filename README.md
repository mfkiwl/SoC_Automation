# System on Chip (SoC) Automation

This program automates SoC design. It expect json input and it outputs verilog files for the SoC and its testbench. 
Currently it supports AMBA AHB for the high-speed (main) bus and APB for the low speed peripherals bus. 

## Getting Started

This instruction will get you a copy of the project up and running on your local machine for development and testing purposes.
```shell
git clone https://github.com/habibagamal/SoC_automation
```
If you need help with how to run the program
```shell
node ./src/sys_gen.js -help 
```
To generate the full SoC .v files
```shell
node ./src/sys_gen.js -soc <soc.json> -mastersLib <masters_lib.json> -IPlib <ip_lib.json> -subsystem <subsystem.json> -outDir <output directory> 
```
- Omit any fields you don't need in the above command.
- If there are no subsystems or real masters, you can ommit "-subsystem <subsystem.json>" or "-mastersLib <masters_lib.json>", respectively, from the command.

## Memory Address Sketch
#### For AHB
![](Images/AHB.png)
--------------------------
#### For APB
![](Images/APB.png)

## Expected input
For instructions on how to write the JSON file for: 
- the masters library: [check this](JSON_format_doc/masters)
- the IPs library: [check this](JSON_format_doc/IPs)
- the system: [check this](JSON_format_doc/SoC)
- the subsyetem: [check this](JSON_format_doc/subsystems)

## Directory structure
- Examples: contains IPs library, masters library and soc examples
- IPs: contains verilog files for open-source IPs
- Images: contains images of memory address structures
- JSON_format_doc: contains documentation for JSON format
- masters: contains masters verilog files
- src: contains source code

## Currently supported features
- Having multiple dummy masters
![](Images/multi_masters.jpg)
- Having multiple buses
![](Images/multi_buses.jpg)
- Using created and open source verification IPs for testing
![](Images/IP_VIP.jpg)
- Using IPs that are not APB or AHB compatible
![](Images/IP_wrapper.jpg)
- Auto-generating self-checking testbench

## Flow
![](Images/flow.jpg)

## Note
- Go [here](https://developer.arm.com/) to download Arm Cortex M0, M3 files 

Check this [poster](DAC&#32;Poster&#32;Presention/poster.pdf) and [video](DAC&#32;Poster&#32;Presention/poster.mp4) presented in DAC 2020 Young Fellowship Program about the project.

## Used Projects
- Arbiter taken from [here](https://github.com/adki/gen_amba)

## Authors
* **Amr Gouhar** [agorararmard](https://github.com/agorararmard)
* **Habiba Gamal** [habibagamal](https://github.com/habibagamal)
* **Mohamed Shalan** [shalan](https://github.com/shalan)



