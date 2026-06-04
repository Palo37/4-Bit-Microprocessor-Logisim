# Design and Implementation of a Microprogrammed 4-Bit Processor

## Project Overview

This project implements a complete **4-bit microprogrammed processor** using **Logisim-Evolution**. The processor follows a **Harvard Architecture** with separate instruction and data memories and executes instructions through a **microprogrammed control unit** implemented using ROM-based microcode.

The design was developed as part of the ACOL 216 course assignment to demonstrate fundamental concepts of processor architecture, datapath design, control logic, instruction execution, and conditional branching.

---

## Features

### Processor Architecture

- 4-bit Datapath
- Harvard Architecture
- 8-bit Program Counter (PC)
- 8-bit Instruction Memory (ROM)
- 4-bit Data Memory (RAM)
- Four General Purpose Registers:
  - R0
  - R1
  - R2
  - R3
- Zero Flag (Z) Register

### Custom Components

The following components were designed using basic logic gates:

- Multiplexers
- Decoders
- Arithmetic Logic Unit (ALU)

### Control Unit

- ROM-based Microprogrammed Control Unit
- Step Counter for instruction sequencing
- Control Word generation through Control ROM
- Support for conditional branching using the Zero Flag

---

## Supported Instruction Set

| Opcode | Instruction | Description |
|----------|------------|-------------|
| 0001 | LDI | Load Immediate into R0 |
| 0010 | ADD | Add Register B to Register A |
| 0011 | SUB | Subtract Register B from Register A |
| 0100 | AND | Bitwise AND |
| 0101 | LD | Load from Data RAM into R0 |
| 0110 | ST | Store R0 into Data RAM |
| 0111 | JMP | Unconditional Jump |
| 1000 | JZ | Jump if Zero Flag is Set |
| 1001 | DEC | Decrement Register |

---

## Project Files

### `processor.circ`

Main Logisim-Evolution project containing:

- Datapath implementation
- Register File
- ALU
- Control Unit
- Memory modules
- Supporting subcircuits

### `Microcode_Spreadsheet.xlsx`

Documentation of:

- Control Word format
- Control ROM addresses
- Binary microinstructions
- Corresponding micro-operations

### `loop_test.hex`

Test program demonstrating:

1. Loading value 4 into a register
2. Countdown loop using DEC
3. Conditional branching using JZ
4. Program termination
5. Data storage into RAM

---

## Test Program Workflow

```text
LDI 4
LOOP:
DEC R0
JZ END
JMP LOOP

END:
Store result to Data RAM
```

The program verifies:

- Arithmetic operations
- Flag generation
- Conditional branching
- Loop execution
- Memory operations

---

## Tools Used

- Logisim-Evolution
- Microsoft Excel / LibreOffice Calc

