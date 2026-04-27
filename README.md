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

I will bandpass sample the IF frequency as i do not want to go directly to baseband 
I do not want to deal with: 
- LO leakage
- DC offset
- I/Q imbalance
- 1/f noise

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
<img width="1638" height="670" alt="image" src="https://github.com/user-attachments/assets/0bccc948-6fa8-4579-98d2-e40d0dc9f17e" />
- antenna: patch 
- LNA Transistor: BFP 420 
- Phase shifters: MAPS-010144 (covers 2.3-3.8GHz)
- Mixer: ADE-25MH+ (5MHZ-2.5GHZ 8SMD)
- Local oscillator: ADF4351
- RF Splitter: PD2425J5050S2HF or SCG-3-272+
- Pi Pico: SC0915

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




