# VHDL: Incorrect Signal Assignment in Clocked Process

This repository demonstrates a common error in VHDL: improper signal assignment within a clocked process. This can cause unexpected behavior such as incorrect output values or race conditions.

## The Bug
The provided VHDL code attempts to create a simple register. The issue lies in the signal assignment inside the process. Because the signal `internal_data` is assigned before the output signal `data_out` gets updated in the same clock cycle, it can result in an output which is one clock cycle behind the input. In some cases this might not be an issue, in some it will create unexpected behaviours.

## The Solution
The solution involves ensuring correct signal assignments and potentially using intermediate signals for clarity and proper timing.

## How to Reproduce
1.  Clone this repository.
2.  Simulate the code using your preferred VHDL simulator (ModelSim, GHDL, etc.).
3.  Observe the output `data_out` and compare it to the input `data_in`.  You will notice a clock cycle delay. 
4. Review the solution for a correct implementation.
