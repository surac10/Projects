# Frequency Analyzer Project

## Overview
Semester-long analog electronics project for **ECE 2600 Electronics**, focusing on the analysis, simulation, and testing of a frequency analyzer circuit. While the PCB layout was provided by Professor Caroline Crockett, I assembled, simulated, analyzed, and verified each analog subsystem, using KiCad simulations and laboratory measurements to characterize circuit behavior. Each student chose a song to reference throughout the project - I chose *Chicago* by Michael Jackson.

## Features 
- Audio input processed through multiple analog subsystems.
- Sallen-Key filters isolate desired frequency ranges.
- Peak detectors convert filtered AC signals into DC control voltages.
- Triangle-wave oscillator and PWM circuitry control LED brightness.
- Red LED indicates frequencies below approximately 110 Hz.
- Green LED indicates frequencies above approximately 800 Hz.

### Sub-System Overview

The purpose of each sub-system for the frequency analyzer is summarized below; the component values for each system can be found in `schematic/component_values.md`.

| Sub-System  | Purpose |
| :---------  | :-----: |
| **Summing Amplifier** | Combines and conditions the right and left input signals from the input jack. |
| **Sallen-Key Low-Pass Filter** | Detects frequencies below ~110 Hz |
| **Sallen-Key High-Pass Filter** | Detects frequencies above ~800 Hz |
| **Low- and High-Pass Peak Detectors** | Capture the amplitude information of the filtered AC signals. |
| **Triangle-Wave Oscilaltor** | Generates a triangle-wave for PWM modulation using a Schmitt trigger and an integrator. |
| **PWM and Analog Led Driver** | Controls the LED brightness using both PWM and analog configurations for comparison and educational purposes. |

## Highlights
- Simulated each subsystem using KiCad before breadboard implementation and testing.
- Performed DC operating point, DC sweep, AC sweep, transient, and pole-zero analyses in KiCad.
- Calculated Sallen-Key filter component values using Python (Jupyter Notebook) and validated filter responses through KiCad simulations and laboratory experiments.
  - Produced a technical report focusing on the design, simulation, and experimental verification of the low-pass and high-pass Sallen-Key filters, written in the active voice. *See* `sallen-key-report/Sallen_Key_Filters.pdf`.
- Interpreted Bode plots to verify filter cutoff frequencies through simulation and experiments.
- Debugged circuits systematically using measured voltages and simulation results, rather than taking blind, educated guesses.
- Successfully demonstrated frequency-dependent LED indication using the audio input.
  - Note: The completed circuit exhibited higher sensitivity to input frequencies when powered by a 9 V battery compared with the Analog Discovery 2 (AD2) 9 V supply. The exact cause was not determined but may be due to differences in supply characteristics or experimental setup.

## Images

### Schematic
See `schematic/Schematic.pdf`: contains full schematic including all subsystems and power supply circuits. 

### Finished PCB

#### Demonstration

- **Chicago – Michael Jackson**
  - `videos/chicago_on_pcb.mp4`
  - Demonstrates the analyzer responding to the reference song used throughout the project.

- **The Hills – The Weeknd**
  - `videos/hills_on_pcb.mp4`
  - Demonstrates the analyzer's response to a song with different instrumentation and frequencies.
