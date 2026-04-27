## Members
Phillip Bozzay, Applied Electromagnetics (2026)
phillipb23@vt.edu
LinkedIn: https://www.linkedin.com/in/phillip-bozzay-830699220/
## Mentor
Shane Wynman, Aleks Salvetti 
## Current Status
IN PROGRESS

## Project Overview

This project develops a software-defined phased array receiver to digitally steer and track RF signals at 915 MHz — the same fundamental technology that enables satellite communication systems like Starlink or Amazon LEO to maintain connectivity with thousands of user terminals.

## Educational Value Added
- Beamforming
- RF circuit design
- ADS/HFSS



## Tasks


## Design Decisions
- Im gonna go with a an analog beamforming architecture with one ADC
- For first prototpye will use SMA-Monopoles for basic beamforming 
- 4-bit phase shifters to steer
- Raspberry pi pico to drive everything else 
<img width="2592" height="1002" alt="image" src="https://github.com/user-attachments/assets/e0bd105a-a4d1-4975-bcde-bfe5517c9379" />


**Component Selection**

Shared Components:



Antenna & Array:



PCB & Passives:
Test Equipment Needed:
915 MHz ISM band transmitter (LoRa module or signal generator)
Spectrum analyzer for RF validation
Oscilloscope for digital/IF debugging




3. Component specifications


## Design Misc
<img width="1858" height="1286" alt="image" src="https://github.com/user-attachments/assets/27bf59b7-99a2-4f99-8aa4-91c82f5fdb6f" />
<img width="2006" height="622" alt="image" src="https://github.com/user-attachments/assets/4b0d2cbc-52b4-4181-aa58-6801e5ac96e6" />


## Steps for Documenting Your Design Process

<!-- Your Text Here. You may work with your mentor on this later when they are assigned -->

## BOM + Component Cost

<!-- Your Text Here. You may work with your mentor on this later when they are assigned -->

## Timeline
1. Need to develop RF board for 915MHz rf rx.
2. Need to devlope eval board for antenna to adc
3. Need to develop eval board for 4 channel tranceivers to FPGA
<!-- Your Text Here. You may work with your mentor on this later when they are assigned -->

## Useful Links

<!-- Your Text Here. You may work with your mentor on this later when they are assigned -->

## Log

<!-- Your Text Here. You may work with your mentor on this later when they are assigned -->




