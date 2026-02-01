# UART  (Verilog HDL)

This project implements a **UART (Universal Asynchronous Receiver Transmitter)** using **Verilog HDL**, featuring a **16× oversampling receiver** for reliable asynchronous serial communication. The design includes both **transmitter (TX)** and **receiver (RX)** blocks and is verified through simulation and waveform analysis.

---

## Overview

UART communication does'nt use a shared clock between transmitter and receiver. To handle clock mismatch and noise, the receiver samples incoming data at **16 times the baud rate**. This oversampling technique allows accurate detection of start bits and data bits by sampling near the center of each bit period.

This project follows a commonly used **industry-standard UART receiver design approach**.

---

## Features

- UART Transmitter and Receiver implementation
- 16× oversampling based UART receiver
- Configurable baud rate using clock divider
- Supports 8-bit data, start bit, and stop bit
- Modular and readable Verilog RTL
- Fully simulated and waveform-verified

---

## Design Description

The transmitter serializes parallel input data and transmits it according to the selected baud rate.  
The receiver generates a **16× baud clock**, detects the start bit, and samples each data bit at the midpoint of its bit duration to improve reliability.

The design is divided into:
- Baud rate / oversampling tick generator
- UART transmitter
- UART receiver
- Top-level UART module
- Testbench for verification

---

## 16× Oversampling Logic

- Each UART bit period is divided into 16 sampling ticks
- Start bit detection aligns the sampling counter
- Data bits are sampled at the **8th tick** (center of the bit)
- Improves noise immunity and tolerance to clock mismatch

---

## Simulation and Verification

Simulation is performed using **Icarus Verilog**, and waveforms are viewed using **GTKWave**.  
The waveform verification confirms:
- Correct start bit detection
- Proper baud timing
- Accurate data transmission and reception
- Correct `rx_done` signaling

