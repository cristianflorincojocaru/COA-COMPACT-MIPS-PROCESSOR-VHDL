# Computer Organization and Architecture - COMPACT MIPS PROCESSOR VHDL

An educational project that implements a **compact MIPS processor** in **VHDL**, focused on simplicity, modularity, and efficient hardware resource usage. The project provides a clear architecture that is easy to understand and extend, making it ideal for *Computer Organization and Architecture* courses as well as FPGA experimentation.

This design represents a reduced version of the MIPS processor, built to highlight the essential functional elements of a real CPU while removing additional complexity that may hinder understanding of fundamental architectural concepts.

---

## Project Objective

The main goal is the construction of a clear and compact processor with a **minimal viable instruction set** and an optimized datapath, suitable for:

- VHDL simulation environments (ModelSim / GHDL)
- FPGA synthesis and implementation
- Understanding how MIPS instructions are translated into low-level hardware execution

Compared to other implementations, this project aims for:
- a design **easy to follow and modify**
- reduced resource consumption
- emphasis on **architectural clarity**

---

## Architecture and System Structure

The processor follows a simplified **non-pipelined model**, executing an instruction through multiple logical phases within a single extended cycle. The architecture is based on a clean separation of modules:

### Main Modules
| Module | Description |
|--------|------------|
| **ALU** | Performs arithmetic and logical operations |
| **Register File** | 32 general-purpose registers |
| **Control Unit** | Decodes instructions and generates control signals |
| **Instruction Memory** | Read-only instruction storage (ROM) |
| **Data Memory** | Memory accessible through load/store instructions |
| **Program Counter** | Controls the sequencing of instruction execution |

The datapath is built using a Harvard-like model, clearly separating instruction memory and data memory to provide predictable behavior and simplified internal logic.

---

## Supported Instruction Set

The processor implements a relevant subset of the MIPS ISA:

### Arithmetic / Logical Instructions
- `ADD`, `SUB`, `AND`, `OR`, `SLT`

### Memory Instructions
- `LW`, `SW`

### Control-flow Instructions
- `BEQ`, `BNE`
- `J` (planned future upgrade)

This reduced ISA maintains complete functional capability without unnecessary complexity and supports good performance on minimal hardware configurations.

---

##  Example Program

```asm
rep:
  lw $2, 0x40($0)   # INW0 = 0xAAAA_AAAB
  lw $3, 0x44($0)   # INW1 = 0x5555_5555
  add $4, $2, $3
  sub $5, $2, $3
  and $6, $2, $3
  or  $7, $2, $3
  sw  $2, 0x48($0)
  sw  $3, 0x48($0)
  sw  $4, 0x48($0)
  sw  $5, 0x48($0)
  sw  $6, 0x48($0)
  sw  $7, 0x48($0)
  beq $2, $3, rep   # no branch (values differ)
  beq $0, $0, rep   # branch to rep (infinite loop)
```

## Simulation and Testing

Simulation can be performed using ModelSim, GHDL, or Vivado Simulator.  
The testbenches include execution examples based on real MIPS instruction sequences.

### Example test programs:
- Register increment and decrement
- Copying and manipulating values in memory
- Loop implementation using `BEQ` or `BNE`

The purpose of testing is to verify signal accuracy at each stage and validate correct control-flow behavior.

---

## Future Development Directions

- Implementation of a **5-stage pipeline** and hazard-handling mechanisms
- Adding additional instructions (`JAL`, `JR`, `MULT`, `DIV`)
- Introducing a **simple cache** for improved performance
- Publishing a **minimal compatible assembler**

---

## Resources and Inspiration

The project is developed based on personal academic experience and reference materials, taking inspiration and comparison from other open-source implementations such as:
- *MIPS Reduced Processor* — used as structural and organizational reference
- *Computer Organization and Design* — Hennessy & Patterson

The project was adapted and restructured for a more compact architecture and a clearer educational approach.

---

## CONTRIBUTIONS

Project created by **Cristian Florin Cojocaru** (**CSE.2** — **University of Craiova / Faculty of Automatics, Computer Science and Electronics**).  
Contributions are welcome! If you have suggestions for improving the code or documentation, please submit a pull request.

---

## LICENSE
This project is licensed under the [MIT License](LICENSE).
