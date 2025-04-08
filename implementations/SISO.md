# SISO (Serial-In Serial-Out) Shift Register

[GitHub Link](https://github.com/Legend101Zz/CircuitVerse/blob/feat/simulator/POC/simulator/src/modules/SISOShiftRegister.js)

## Overview

The Serial-In Serial-Out (SISO) shift register is the simplest form of shift register that accepts one bit of data at a time and outputs one bit at a time. It functions as a digital delay line, where input data is shifted through the register with each clock pulse.

## Implementation Details

This component extends CircuitVerse's `CircuitElement` class with the following features:

- **Configurable Bit Width**: Supports different register lengths (4 bits by default)
- **Edge Detection**: Updates only on the rising edge of the clock signal
- **Reset Capability**: Asynchronous reset clears the register to zero
- **Visual State Display**: Shows the current binary content of the register
- **Serialization Support**: Full save/load capability

## Inputs and Outputs

- **Data In**: Serial input for individual bits (1-bit)
- **Clock**: Triggers the shift operation on rising edge (1-bit)
- **Reset**: Asynchronously clears all bits to zero when high (1-bit)
- **Data Out**: Serial output of the last bit in the register (1-bit)

## Behavior

1. When **Reset** is high, all bits in the register are cleared to zero
2. On the rising edge of the **Clock** signal:
   - The bit at **Data In** enters the first position of the register
   - All other bits shift one position to the right
   - The rightmost bit is shifted out to the **Data Out** pin

## Example Usage

The SISO shift register is useful for:

- Creating digital delay lines
- Serial data transmission
- Implementing simple state machines
- Building more complex sequential components

## Verilog Implementation

The component includes Verilog generation that creates an appropriate module definition for hardware synthesis.

<!-- Add your images here -->
