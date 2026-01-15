# UART-Verilog


This project implements a **UART (Universal Asynchronous Receiver Transmitter)** using **Verilog HDL**, featuring a **16× oversampling receiver** for reliable asynchronous serial communication. The design includes both **transmitter (TX)** and **receiver (RX)** blocks and is verified through simulation and waveform analysis.


## Overview

UART communication does not use a shared clock between transmitter and receiver. To handle clock mismatch and noise, the receiver samples incoming data at **16 times the baud rate**. This oversampling technique allows accurate detection of start bits and data bits by sampling near the center of each bit period.

This project follows a commonly used **industry-standard UART receiver design approach**.

## Features

- UART Transmitter and Receiver implementation
- 16× oversampling based UART receiver
- Configurable baud rate using clock divider
- Supports 8-bit data, start bit, and stop bit
- Modular and readable Verilog RTL
