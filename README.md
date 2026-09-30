# ALUForge'26 — 8 Bit ALU Using Discrete IC Components
<p align="center">Team Octa-ALU · Hackathon Project</p>

---

# 8-Bit Arithmetic Logic Unit (ALU)

## 📌 Project Overview

This project is an **8-bit Arithmetic Logic Unit (ALU)** designed and physically built as a part of a custom **8-bit computer**.

The ALU is a fundamental component of a processor that performs arithmetic and logical operations on binary data. In this project, the ALU is constructed using individual digital logic components such as **register ICs, adder ICs, logic gates, and supporting components**.

Instead of using a single dedicated ALU IC, the circuit is built from basic digital building blocks to understand the internal operation of an ALU and the way data moves through a processor.

---

## 🧠 What is an ALU?

An **Arithmetic Logic Unit (ALU)** is a digital circuit responsible for performing arithmetic and logical operations on data.

It is one of the major functional blocks inside a CPU. The ALU receives binary data from registers, performs an operation according to the control signals, and produces the resulting data.

Typical ALU operations include:

- Addition
- Subtraction
- AND
- OR
- XOR
- NOT
- Increment
- Decrement
- Comparison

The exact operations available depend on the design of the ALU.

---

## ⚙️ Project Features

- 8-bit data processing
- Register-based data storage
- Adder-based arithmetic operations
- Control signal based operation selection
- LED-based binary output indication
- Breadboard hardware implementation
- Built using individual digital ICs
- Designed as a processing unit for a custom 8-bit computer

---

## 🧩 ALU Architecture

The basic data flow of the ALU can be represented as:

```
              INPUT A
                 │
                 ▼
        ┌─────────────────┐
        │   Register A    │
        └────────┬────────┘
                 │
                 │
                 ▼
        ┌─────────────────┐
        │                 │
        │     8-Bit ALU   │◄──── Control Signals
        │                 │
        │ ┌─────────────┐ │
        │ │ Arithmetic  │ │
        │ │  Circuit    │ │
        │ ├─────────────┤ │
        │ │    Logic    │ │
        │ │   Circuit   │ │
        │ └─────────────┘ │
        │                 │
        └────────┬────────┘
                 │
                 ▼
        ┌─────────────────┐
        │  Output Register│
        └────────┬────────┘
                 │
                 ▼
              OUTPUT
```

The input data is stored in registers and supplied to the ALU. Based on the control signals, the required arithmetic is selected. The resulting 8-bit data is then available at the output.

## Circuit image
<img width="500" alt="Circuit image" src="https://github.com/user-attachments/assets/c426292c-3c32-4826-859c-3d22bbf49b99" />

## 🔧 Components Used

The ALU was constructed using various digital electronics components

### Main Components
- Register ICs
- Adder ICs
- Logic Gate ICs
- LEDs
- Resistors
- Breadboards
- wires
- Power supply
- Supporting passive components

#### Register ICs
  Registers are used to temporarily store 8-bit binary data.<br>
  Ex: SN54173 ic<br>
  They provide a way to hold input values before processing and store the resulting data after an operation.

#### Adder ICs
  Adder ICs form the main arithmetic section of the ALU.<br>
  Ex: SN54HC283<br>
  They are used to perform binary addition and can also be used as part of subtraction and other arithmetic operations depending on the circuit design.

#### Logic Gate ICs
  Logic gates are used to implement logical operations and control the flow of binary signals.<br>
  The combination of gates allows the ALU to perform operations on individual bits of the input data.

#### LEDs
  LEDs are used to provide a visual indication of the binary output.<br>
  Each LED represents one bit of the 8-bit result.

## 🔄 Working Principle
The ALU works by receiving binary data from input registers and processing it according to the selected operation.

The general process is:

```
Input Data
    ↓
Input Registers
    ↓
Operation Selection
    ↓
Arithmetic / Logic Circuit
    ↓
8-Bit Result
    ↓
Output Register / LEDs
```

Step 1 — Input Data

The required binary values are loaded into the input registers.<br>
For an 8-bit ALU, each input can represent a value from:<br>
00000000 to 11111111<br>
which corresponds to decimal values from 0 to 255 for unsigned data.

Step 2 — Data Storage

The input registers hold the binary values and provide stable signals to the ALU circuitry.<br>
This prevents the input data from changing while the operation is being performed.

Step 3 — Operation Selection

Control signals determine which operation the ALU should perform.<br>
Depending on the control configuration, the input data is routed through the appropriate arithmetic or logic circuitry.

Step 4 — Processing

The selected arithmetic or logical circuit processes the input data.<br>
For example, during addition, the input bits are passed through the adder circuitry to generate an 8-bit result.

Step 5 — Output

The resulting binary data is sent to the output section.<br>
The result can be stored in a register and/or displayed using LEDs.

## ➕ Arithmetic Operations
### Binary Addition:<br>
The ALU can perform addition using the adder circuitry.

For example:
```
    00000101
  + 00000011
  ----------
    00001000
```
Here:

5 + 3 = 8

The addition is performed bit by bit using binary addition.

### Binary Subtraction:<br>
Subtraction can be implemented using complementary logic and adder circuitry.<br>
A common digital technique is to represent subtraction using two's complement arithmetic.

For example:

  A - B

can be implemented as:

  A + (Two's Complement of B)
```
7 - 2 using 2's Complement

  0111   (7)
+ 1110   (-2)
------
  0101   (5)

Result = 5
```

This allows the same adder circuitry to be used for both addition and subtraction.

### 🔢 Logical Operations
Logical operations operate on individual bits of the input data.

#### AND
The AND operation produces 1 only when both input bits are 1.
```
A   B   Output
0   0     0
0   1     0
1   0     0
1   1     1
```
#### OR
The OR operation produces 1 when at least one input bit is 1.
```
A   B   Output
0   0     0
0   1     1
1   0     1
1   1     1
```
#### XOR
The XOR operation produces 1 when the two input bits are different.
```
A   B   Output
0   0     0
0   1     1
1   0     1
1   1     0
```
#### NOT
The NOT operation inverts the input bit.
```
Input   Output
  0       1
  1       0
```
For an 8-bit value, these operations are performed independently on each bit.

## 💻 8-Bit Data Processing
An 8-bit ALU processes eight binary bits simultaneously.

For example:

Input A = 10101100<br>
Input B = 00010101

Each bit position represents a binary value:
```
Bit:     7 6 5 4 3 2 1 0
         │ │ │ │ │ │ │ │
         ▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼
Data:    1 0 1 0 1 1 0 0
```
The ALU processes these bits using its arithmetic and logic circuitry to generate an 8-bit result.

## 🏗️ Hardware Implementation
The ALU was physically assembled on breadboards using individual digital ICs and supporting components.

The hardware implementation provides a practical demonstration of how multiple digital circuits can be combined to create a functional processing unit.

The circuit contains separate sections for:
```
Input Registers
       ↓
Arithmetic Circuit
       ↓
Logic Circuit
       ↓
Output Selection
       ↓
Output Register
       ↓
LED Indicators
```
Each section performs a specific function and communicates with the other sections using digital signals.

## 🔌 Registers and Data Flow
Registers play an important role in the ALU because they provide temporary storage for binary data.

The basic data flow is:
```
Register A ──────┐
                 │
                 ▼
              ┌─────┐
              │ ALU │──────► Result
              └─────┘
                 ▲
                 │
Register B ──────┘
```
The registers hold the input values while the ALU performs the selected operation.

After processing, the result can be transferred to another register for use by other parts of the computer.

## 🎛️ Control Signals
The operation performed by an ALU is controlled using digital control signals.

These signals determine which section of the ALU should be active.

Conceptually:
```
Control Signals
      │
      ▼
┌───────────────┐
│ Operation     │
│ Selection     │
└───────┬───────┘
        │
        ▼
┌──────────────────────┐
│ Arithmetic / Logic   │
│ Circuit              │
└──────────┬───────────┘
           │
           ▼
        Result
```
In a complete 8-bit computer, these control signals can be generated by the control unit.

## 📊 Why Build an ALU Using Individual ICs?
Modern processors contain highly integrated ALUs inside a single chip. However, building an ALU using individual ICs makes the internal operation easier to observe and understand.

This project demonstrates how:
```
Logic Gates
     +
Adders
     +
Registers
     +
Control Signals
     ↓
Processing Unit
```
can be combined to create the basic functionality of a processor.

## 🎯 Learning Objectives
This project provides practical experience in:

- Digital logic design
- Binary number systems
- Binary arithmetic
- Registers and data storage
- Adder circuits
- Logic gates
- Combinational logic
- Sequential logic
- Data paths
- Control signals
- Hardware debugging
- Breadboard circuit construction
- Processor architecture

## 📚 Important Digital Logic Concepts
```
Enable Input
An Enable input controls whether a digital circuit is active or disabled.

Register
A register is a sequential digital circuit used to store binary data temporarily.

Register Input
A register input is the data signal that is loaded into the register for storage.

Register Output
A register output provides the binary data currently stored in the register.

Adder
An adder is a combinational digital circuit used to perform binary addition.

Carry Input
Carry Input (Cin) is the carry received from the previous bit or adder stage.

Carry Output
Carry Output (Cout) is the carry generated by an addition and passed to the next stage.

Tri-State Buffer
A tri-state buffer is a digital circuit whose output can be HIGH, LOW, or High-Impedance (Z).

High-Impedance State
The High-Impedance (Z) state makes a circuit output electrically disconnected, allowing multiple devices to share a common bus.

Data Bus
A data bus is a group of wires used to transfer binary data between different parts of a digital system.

Pull-Down Resistor
A pull-down resistor keeps a digital input at a default LOW (`0`) state when the input is not actively driven.

Pull-Up Resistor
A pull-up resistor keeps a digital input at a default HIGH (`1`) state when the input is not actively driven.

Floating Input
A floating input is a digital input that is not connected to a defined HIGH or LOW logic level and may produce unpredictable results.

Logic Level
A logic level represents binary information as LOW (`0`) or HIGH (`1`).

Combinational Logic
Combinational logic is a digital circuit whose output depends only on its present inputs.

Sequential Logic
Sequential logic is a digital circuit whose output depends on present inputs as well as previously stored state.

Clock Signal
A clock signal is a periodic digital signal used to synchronize operations in sequential circuits such as registers.

Multiplexer
A multiplexer (MUX) is a digital circuit that selects one input from multiple inputs and sends it to a single output.

Two's Complement
Two's complement is a binary representation method used to represent negative numbers and perform subtraction using addition.

Propagation Delay
Propagation delay is the time taken for a change at a digital circuit's input to appear at its output.

Fan-Out
Fan-out is the maximum number of digital inputs that a single output can reliably drive.

Overflow
Overflow occurs when the result of an arithmetic operation exceeds the range that can be represented using the available number of bits.
```

## 🔮 Future Improvements
- Possible improvements to the project include:
- Adding more arithmetic operations
- Expanding the supported logical operations
- Implementing Carry and Zero flags
- Adding Overflow and Sign flags
- Improving the control circuitry
- Integrating the ALU with the complete 8-bit computer
- Improving circuit organization and wiring
- Adding a dedicated control panel
- Designing a PCB version of the circuit

This ALU is one of the core building blocks of the custom 8-bit computer and serves as a practical implementation of arithmetic and logic processing using discrete digital ICs.
