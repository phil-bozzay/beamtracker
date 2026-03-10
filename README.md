## Members
Phillip Bozzay, Applied Electromagnetics (2026)
phillipb23@vt.edu
LinkedIn: https://www.linkedin.com/in/phillip-bozzay-830699220/
## Mentor
Shane Wynman, Aleks Salvetti 
## Current Status
IN PROGRESS

## Project Overview

This project develops a software-defined phased array receiver to digitally steer and track RF signals at 915 MHz — the same fundamental technology that enables satellite communication systems like Starlink to maintain connectivity with thousands of moving user terminals. Starting from a single custom receive chain and scaling to a four-element array, the system demonstrates end-to-end RF hardware design, FPGA-based data acquisition, and real-time digital beamforming in GNU Radio. Each stage of the receiver — LNA, filtering, downconversion, digitization, and processing — is designed from first principles using off-the-shelf components on a custom PCB. The result is a fully functional phased array platform for experimentation in beam steering, interference nulling, and direction finding.

## Educational Value Added



## Tasks
1. Define system requirements: frequency, bandwidth, IF, ADC sample rate, beamforming specifications
2. Select and procure components: LNA, SAW filter, mixer, PLL/LO, ADC, FPGA dev board, antennas
3.Design single-channel receiver schematic in KiCad with reference design validation
4. Simulate RF front end performance: noise figure cascade, gain budget, image rejectio
5. Layout single-channel PCB with controlled impedance traces and proper RF grounding
6. Fabricate, assemble, and bring up single-channel board
7. Validate RF performance: verify gain, noise figure, and IF output with spectrum analyzer
8. Interface ADC to FPGA: write VHDL/Verilog for single-channel data capture and USB serialization
9. Stream data into GNU Radio and demodulate BPSK test signal end-to-end
10. Design and fabricate four-channel receiver board with matched RF paths and shared LO distribution
11. Extend FPGA firmware for four-channel parallel acquisition and serialization
12. Implement digital beamforming in GNU Radio: phase weighting, beam steering, and pattern visualization
13. Calibrate array channels to correct phase and amplitude mismatches
14. Demonstrate beam steering, interference nulling, and direction finding with live RF signals
## Design Decisions
**Signal Bandwidth** - Want minimum possible signal bandwidth, which is 500KHz defined by FCC guidelines 

## Design Misc
<img width="1858" height="1286" alt="image" src="https://github.com/user-attachments/assets/27bf59b7-99a2-4f99-8aa4-91c82f5fdb6f" />


## Steps for Documenting Your Design Process

<!-- Your Text Here. You may work with your mentor on this later when they are assigned -->

## BOM + Component Cost

<!-- Your Text Here. You may work with your mentor on this later when they are assigned -->

## Timeline

<!-- Your Text Here. You may work with your mentor on this later when they are assigned -->

## Useful Links

<!-- Your Text Here. You may work with your mentor on this later when they are assigned -->

## Log

<!-- Your Text Here. You may work with your mentor on this later when they are assigned -->


