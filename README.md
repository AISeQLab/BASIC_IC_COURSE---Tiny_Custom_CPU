 pypandoc

content = """## Tiny_Custom_CPU_ALU_Q8_7

### Introduction
This project demonstrates a **Tiny Custom CPU** featuring a lightweight **16-bit ALU** designed for fixed-point arithmetic using the **Q8.7 format**.  
The CPU executes arithmetic and logic operations based on opcodes received via UART.  
It is implemented on an FPGA platform and can be controlled using a Node.js web interface for real-time computation.

### ALU Specifications
The ALU supports the following operations on **16-bit Q8.7 fixed-point numbers**:

The Tiny CPU uses a simple opcode-based protocol to trigger ALU operations:

| Opcode | Mnemonic | Operation | Description |
|--------|----------|-----------|-------------|
| **0** | **NOP** | No operation| Fixed-point addition |
| **1** | **ADD** | a + b |       Fixed-point subtraction |
| **2** | **SUB** | a − b |       Fixed-point multiplication (Q8.7 × Q8.7 → Q8.7) |
| **3** | **MUL** | a × b (Q8.7)|  Bitwise AND |
| **4** | **AND** | a AND b |     Bitwise OR |
| **5** | **OR**  | a OR b |      Bitwise NOT |
| **6** | **NOT** | NOT a |       Bitwise XOR |
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