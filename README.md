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
**Signal Modulation** - i choose bpsk signal modulation, only need I channel 
**Signal Frequency** - Standard ISM band 915MHz
**IF frequency** - 70 MHz
**LO Frequency** - 845 MHZ (need BPF to reject the image frequency (845-70 = 775 MHz) => shows up as -70 MHz
**ADC Sample Rate** - (1 MSPS (2x signal bandwidth)) + 0.5 MSPS (filter rolloff buffer)
**Beamforming specifications** - need to be able to detect TDOA between elements, then point receive angle at this direction
- Spacing : want lambda/2 for maximum array factor, so im gonna do 16.4m spacing
- Needs to be configurable to 1x4 grid or 2x2 grid for both 1d and 2d beamforming.
- SMAs, cables, whip antennas lambda/4 because omnidirectional 
**FPGA Interface** - Four channel parallel ADC capture, serialized over USB to host computer

**Component Selection**
RF Front End (per channel, ×4 for full array):

Skyworks SKY67013-396LF — LNA, 0.85 dB NF, 14 dB gain at 915 MHz
SAW bandpass filter 902-928 MHz — image rejection, ~2.5 dB insertion loss
Analog Devices LT5560 — mixer, 0.01-4 GHz, ~-2 dB conversion gain
IF amplifier (~22 dB gain at 70 MHz) — TBD, something like AD8354 or op-amp stage
Texas Instruments ADS7042 — 12-bit, 1 MSPS ADC, SPI interface

Shared Components:

Analog Devices ADF4351 — PLL/LO synthesizer, 35 MHz-4.4 GHz, generates 845 MHz LO for all four channels
Reference crystal oscillator — 10 or 25 MHz TCXO for the ADF4351
LO power splitter — 1:4 to distribute LO to all four mixers
FPGA dev board — serializes four ADC channels over USB to computer
3.3V and 5V voltage regulators for power supply
Decoupling capacitors — 100 nF and 10 µF at every power pin

Antenna & Array:

4× quarter-wave whip antennas, 915 MHz ISM band, SMA connector
4× SMA coax cables (matched length for phase coherence)
Mounting fixture/rail for configurable 1×4 or 2×2 array geometry

PCB & Passives:

4-layer PCB (signal, ground, power, signal) with controlled impedance
50 ohm impedance matching networks — per datasheet reference designs
SMA edge connectors for antenna inputs and LO distribution

Test Equipment Needed:
915 MHz ISM band transmitter (LoRa module or signal generator)
Spectrum analyzer for RF validation
Oscilloscope for digital/IF debugging




3. Component specifications


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



