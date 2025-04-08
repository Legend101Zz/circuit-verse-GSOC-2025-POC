# PIPO (Parallel-In Parallel-Out) Shift Register

[GitHub Link](https://github.com/Legend101Zz/CircuitVerse/blob/feat/simulator/POC/simulator/src/modules/PIPOShiftRegister.js)

## Overview

The Parallel-In Parallel-Out (PIPO) shift register accepts multiple bits simultaneously as parallel inputs and makes all stored bits available simultaneously as parallel outputs. Unlike other shift registers, it doesn't perform shifting operations but instead acts as a synchronized data latch or buffer.

## Implementation Details

This implementation extends CircuitVerse's `CircuitElement` class with:

- **Configurable Bit Width**: Supports different register sizes (default 4 bits)
- **Edge-Triggered Operation**: Data is loaded only on clock edges
- **Enable Control**: Allows selective updating of register contents
- **Asynchronous Reset**: Clears all register bits
- **Visual State Display**: Shows current register contents
- **Full Input/Output Access**: Every bit position is accessible

## Inputs and Outputs

- **Parallel Data Inputs**: One input node per bit position (n-bits)
- **Clock**: Rising edge triggers data loading when enabled (1-bit)
- **Enable**: Controls whether register updates on clock edge (1-bit)
- **Reset**: Asynchronously clears all bits when high (1-bit)
- **Parallel Data Outputs**: One output node per bit position (n-bits)

## Behavior

1. When **Reset** is high, all bits in the register are cleared to zero
2. On the rising edge of the **Clock** signal:
   - If **Enable** is high:
     - All parallel inputs are simultaneously loaded into the register
   - If **Enable** is low:
     - Register contents remain unchanged
3. All bits in the register are continuously available at the parallel outputs

## Example Usage

The PIPO shift register is commonly used for:

- Data storage and buffering
- Implementing data latches
- Synchronizing data between different clock domains
- Temporarily holding data for parallel operations

## Verilog Implementation

The component includes Verilog generation that creates an appropriate module definition for hardware synthesis.

<!-- Add your images here -->
