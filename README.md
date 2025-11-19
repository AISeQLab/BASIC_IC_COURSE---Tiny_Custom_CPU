 pypandoc

content = """## Tiny_Custom_CPU_ALU_Q8_7

### Introduction
This project demonstrates a **Tiny Custom CPU** featuring a lightweight **16-bit ALU** designed for fixed-point arithmetic using the **Q8.7 format**.  
The CPU executes arithmetic and logic operations based on opcodes received via UART.  
It is implemented on an FPGA platform and can be controlled using a Node.js web interface for real-time computation.

### ALU Specifications
The ALU supports the following operations on **16-bit Q8.7 fixed-point numbers**:

| Operation | Description |
|----------|-------------|
| **ADD**  | Fixed-point addition |
| **SUB**  | Fixed-point subtraction |
| **MUL**  | Fixed-point multiplication (Q8.7 × Q8.7 → Q8.7) |
| **AND**  | Bitwise AND |
| **OR**   | Bitwise OR |
| **NOT**  | Bitwise NOT |
| **XOR**  | Bitwise XOR |

All operations are implemented in hardware for efficient execution within the Tiny CPU datapath.

### Opcode Table
The Tiny CPU uses a simple opcode-based protocol to trigger ALU operations:

| Opcode | Mnemonic | Operation |
|--------|----------|-----------|
| **0** | **NOP** | No operation |
| **1** | **ADD** | a + b |
| **2** | **SUB** | a − b |
| **3** | **MUL** | a × b (Q8.7) |
| **4** | **AND** | a AND b |
| **5** | **OR**  | a OR b |
| **6** | **NOT** | NOT a |
| **7** | **XOR** | a XOR b |

Opcodes above can be extended for branching, memory access, or custom instructions if needed.

### System Overview
1. **Hardware Platform:** Any FPGA supporting UART communication  
2. **CPU Components:**  
   - 16-bit ALU (Q8.7 fixed-point)  
   - Instruction decoder  
   - Register file (R0, R1, ACC)  
   - UART RX/TX module  
3. **Software Components:**  
   - C code for sending opcodes and operands  
   - Node.js server for user interaction through a web interface  
4. **Interface:** Web browser acts as a simple fixed-point calculator  
5. **Communication:** Node.js → C program → UART → Tiny CPU → result returned to web UI  

### Setup
The figure below illustrates the complete setup connecting the web browser, Node.js server, and FPGA running the Tiny CPU.

<img src="Figure/setup.png" alt="System Setup" width="500">

### Video Tutorial
The tutorial explaining the hardware and software workflow is split into two parts:

- **Part 1 – Hardware Design & ALU Explanation**  
  https://youtu.be/NQ5qTkZTr5I

- **Part 2 – Node.js Server & UART Integration**  
  https://youtu.be/UQM3CLi0w9A

### Author
Pham Hoai Luan  
Nara Institute of Science and Technology (NAIST), Japan