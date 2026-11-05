# SEU Fault Injection and Recovery System using SystemVerilog

## Overview
This project demonstrates a Single Event Upset (SEU) fault injection and recovery system using Triple Modular Redundancy (TMR).

TMR uses three identical 8-bit registers to store the same data. A majority voter determines the output, while an error detector identifies differences between the registers.

## Features
- Three redundant 8-bit registers (R1, R2 and R3)
- Selectable fault injection into any one register
- Selectable bit position for fault injection
- Majority voting for error detection and correction
- Automatic recovery of corrupted register data
- SystemVerilog RTL design and testbench

## Tools Used
- SystemVerilog
- EDA Playground
- QuestaSim 2025.2
- EPWave

## Simulation Results

Single-bit faults were injected into the following locations:

| Register | Faulty bit | Error detected | Recovery |
|---|---:|---|---|
| R1 | 2 | Yes | Successful |
| R2 | 5 | Yes | Successful |
| R3 | 0 | Yes | Successful |

The recovered output matched the original input:

`10110110`

The error signal returned to 0 after recovery in all three tested cases.

## How It Works

1. Three registers store identical input data.
2. A fault is injected into a selected register and bit.
3. The error detector identifies disagreement between registers.
4. The majority voter determines the correct data.
5. The corrupted registers are restored using the majority output.

## Project Files
- `design.sv` – RTL implementation.
- `testbench.sv` – Simulation testbench.
- `README.md` – Project documentation.

## Simulation
The project was simulated using QuestaSim 2025.2 on EDA Playground.

[Open the EDA Playground project](https://edaplayground.com/x/Z9j6)

## Limitation
This educational implementation assumes a single faulty register at a time. It does not guarantee recovery from simultaneous faults in multiple registers.
