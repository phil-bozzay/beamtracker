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
3. Design single-channel receiver schematic in KiCad with reference design validation
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

1. High level specifications: 
**Signal Bandwidth** - Want minimum possible signal bandwidth, which is 500KHz defined by FCC guidelines, FCC Part 15, Subpart C, Section 15.247(a)(2)
**Signal Modulation** - i choose bpsk signal modulation, for simplicity. Also BPSK has no DC offset 
**Signal Frequency** - Standard ISM band 915MHz
**Zero IF** - zero intermediate frequency conversion, need 2 adcs for this but simplifies archetecture
**ADC Sample Rate** - (1 MSPS (2x signal bandwidth)) + 0.5 MSPS (filter rolloff buffer)
**Beamforming specifications** - need to be able to detect TDOA between elements, then point receive angle at this direction
- Spacing : want lambda/2 for maximum array factor, so im gonna do 16.4m spacing
- Needs to be configurable to 1x4 grid or 2x2 grid for both 1d and 2d beamforming.
- SMAs, cables, whip antennas lambda/4 because omnidirectional 
**FPGA Interface** - Four channel parallel ADC capture, serialized over USB to host computer

**Component Selection**
- Antenna (RF capture): Antenna, RF wave from environment → RF signal (~915 MHz single-ended)
- Low Noise Amplifier (LNA): SKY67150-396LF, RF input (50 Ω single-ended) → amplified RF output (50 Ω single-ended)
- RF Bandpass Filter: B39921B3728U410, RF input (902–928 MHz single-ended) → filtered RF output (single-ended)
- RF Balun (RF → differential): Mini-Circuits TC1-1-13, RF single-ended → RF differential (RF+, RF−)
- IQ Demodulator / Direct Conversion Mixer: ADL5380, RF+, RF− and LO+, LO− → I+, I−, Q+, Q− (differential baseband)
- LO Balun (LO → differential): Mini-Circuits TC1-1-13, LO single-ended → LO+, LO− (differential)
- Baseband Conditioning (diff→single-ended, LPF, gain, bias): OPA2320, I+, I− → I (0–3.3 V single-ended), Q+, Q− → Q (0–3.3 V single-ended)
- ADC (I channel): ADS7046, analog input I (0–3.3 V) → digital SPI output (I samples)
- ADC (Q channel): ADS7046, analog input Q (0–3.3 V) → digital SPI output (Q samples)
- DSP / AoA Estimation Processor: FPGA / MCU, digital I/Q samples → estimated angle-of-arrival (AoA)

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




