# 3-Stage Audio Amplifier with Class AB Output

## Overview
This repository contains the schematic, simulation files, and custom PCB layout for a 3-stage audio amplifier with volume control. The circuit is designed to take a weak audio signal (such as the output from a smartphone or microphone) and amplify it sufficiently to drive an 8Ω speaker with clear, audible sound. This project was developed as part of the ECE211s Electronics course at Ain Shams University.

The design was fully simulated in Proteus 8, verified using virtual oscilloscopes, and fabricated on a custom PCB.

## Circuit Architecture
The amplifier is built using three primary functional stages to provide both voltage and current gain:
* **Stage I: Preamplifier (Voltage Gain):** An inverting amplifier configuration using an LM358 operational amplifier. It includes a 1 MΩ potentiometer to act as a volume control by adjusting the feedback loop.
* **Stage II: Buffer:** A voltage follower stage utilizing the LM358. This stage prevents loading effects and matches the output of the preamplifier to the power amplifier.
* **Stage III: Class AB Power Amplifier (Current Gain):** A push-pull amplifier utilizing a discrete NPN (BC337) and PNP (BC327) transistor pair. This stage provides the large current necessary to drive the speaker efficiently while minimizing crossover distortion.

## Hardware Specifications & Performance

| Parameter | Value |
| :--- | :--- |
| **Supply Voltage** | 9V DC |
| **Input Signal** | ~20mVpk (1 kHz sine wave) |
| **Output Load** | 8 Ω Speaker |
| **Total System Gain** | 100 V/V |
| **Max Output Power** | ~140.6 mW |

## Bill of Materials (BOM)

| Component | Part Number | Quantity | Role |
| :--- | :--- | :--- | :--- |
| Dual Op-Amp | LM358N | 2 | Preamplifier and Buffer stages |
| NPN Transistor | BC337 | 1 | Class AB push-pull (positive half-cycle) |
| PNP Transistor | BC327 | 1 | Class AB push-pull (negative half-cycle) |
| Potentiometer | 1 MΩ | 1 | Volume control (Gain adjustment) |
| Electrolytic Caps | 47µF, 100µF, 470µF | 1 each | Signal coupling and supply bypass |
| Resistors | 10kΩ, 100kΩ | Various | Biasing and feedback networks |
| Indicator LED | Green LED | 1 | Power indicator |

## Repository Contents
* `Audio_amp.pdsprj`: The Proteus 8 simulation source file containing the full circuit schematic and virtual oscilloscope setup.
* `Audio_Amp.png`: High-resolution export of the Proteus circuit schematic.
* `Audio_Amp_PCB.png`: Snapshot of the custom PCB layout designed for the amplifier.

## Testing & Validation
The circuit was tested using a smartphone frequency generator application. The input signal and the amplified output were measured using a digital multimeter and an oscilloscope to confirm the target voltage gain of 100 V/V. The physical circuit successfully drove an 8Ω speaker with clear audio and minimal distortion.
