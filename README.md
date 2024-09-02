*RISC-V Based Hardware Accelerator for K-Nearest Neighbors (KNN):*

This project involves the development of a custom hardware accelerator built on the RISC-V architecture, specifically designed to enhance the efficiency of K-Nearest Neighbors (KNN) operations. The accelerator features several key modules, including the Instruction Fetch Unit (IFU), Control Unit, Datapath, and a specialized Arithmetic Logic Unit (ALU). The design is implemented using Verilog, focusing on optimizing computation for KNN algorithms.

*Project Overview*:
The hardware accelerator is composed of the following primary components:

1. *Instruction Fetch Unit (IFU)*
Responsible for retrieving instructions from the instruction memory via the Program Counter (PC).
The instruction memory is implemented as Block RAM (BRAM).
2. *Control Unit*
Decodes the fetched instructions and generates the required control signals for the other processor modules.
Capable of handling various instruction types, including integer operations, floating-point operations, branch operations, and both floating-point and integer load instructions.
3. *Datapath*
The processor’s core, responsible for executing arithmetic and logical operations.
It comprises three main components:
-ALU (Arithmetic Logic Unit): Custom-tailored to perform KNN operations.
-Regfile (Register File): Includes 32 registers, each 32 bits in width.
-Memory (Data Memory): Contains two separate BRAMs for storing labels and data points.
4. *Customized ALU*
The ALU is designed specifically for KNN operations and includes the following modules:

Floating Point Subtraction and Multiplication: Integrated into a single module to compute squared differences.
Floating Point Square Root: Used for distance calculations.
Floating Point Addition: Facilitates summing distances and other operations.
Integer Addition: Handles index calculations and integer operations.
Greater Than Comparison: Assists in making branching decisions.
Sort and Majority Module: Determines the nearest neighbors and identifies the most frequent label among them.

5. *Memory Architecture*
Instruction Memory: Implemented as BRAM, utilized by the IFU to fetch instructions.
Data Memory:
One BRAM dedicated to storing labels.
Another BRAM reserved for storing data points.
Supported Instruction Types
The RISC-V-based accelerator supports a diverse set of instruction types, enabling it to perform various operations:

Integer Operations: Fundamental arithmetic and logical functions.
Floating Point Operations: Includes addition, subtraction, multiplication, and square root functions for floating-point numbers.
Branch Operations: Conditional branching based on comparison results.
Floating Point Load: Instructions for loading floating-point data from memory.
Integer Load: Instructions for loading integer data from memory.
