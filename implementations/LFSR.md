# LFSR (Linear Feedback Shift Register)

[GitHub Link](https://github.com/Legend101Zz/CircuitVerse/blob/feat/simulator/POC/simulator/src/modules/LFSR.js)

## Overview

The Linear Feedback Shift Register (LFSR) is a special shift register that uses feedback connections to generate pseudo-random bit sequences. It consists of a shift register with selected outputs XORed together and fed back to the input, creating a deterministic but statistically random-looking sequence.

## Implementation Details

This CircuitVerse component provides:

- **Configurable Bit Width**: Support for different register lengths (4-16 bits)
- **Customizable Taps**: Configurable feedback taps based on primitive polynomials
- **Maximal-Length Sequence**: Generates 2^n-1 unique states before repeating
- **Seed Control**: Ability to initialize with custom starting value
- **Edge-Triggered Operation**: Updates occur only on clock edges
- **Visual State Display**: Shows current register contents
- **Asynchronous Reset**: Option to reset to predefined state

## Inputs and Outputs

- **Seed Input**: Parallel input to set the initial state (n-bits)
- **Load Seed**: Control signal to load the seed value (1-bit)
- **Clock**: Rising edge triggers shift operation (1-bit)
- **Reset**: Asynchronously resets to all-ones state when high (1-bit)
- **Serial Output**: Output of the rightmost bit (1-bit)
- **Parallel Outputs**: One output per bit position showing internal state (n-bits)

## Behavior

1. When **Reset** is high, the register is set to all ones (or another predefined value)
2. When **Load Seed** is high, the **Seed Input** value is loaded into the register
3. On the rising edge of the **Clock** signal:
   - Bits shift one position to the right
   - The new leftmost bit is calculated as an XOR of selected tap positions
   - The rightmost bit appears at the **Serial Output**
4. A full sequence will generate all possible n-bit values except all-zeros before repeating

## Tap Selection

The component includes predefined optimal tap positions for common bit widths to ensure maximal-length sequences. For a given bit width, the taps are based on primitive polynomials that ensure the LFSR cycles through all 2^n-1 possible non-zero states.

## Example Usage

The LFSR is commonly used for:

- Pseudo-random number generation
- Built-in self-test (BIST) in integrated circuits
- CRC calculation
- Scrambling/descrambling in communications
- Noise generation
- Cryptographic applications

## Verilog Implementation

The component includes Verilog generation for hardware synthesis.

<!-- Add your images here -->
