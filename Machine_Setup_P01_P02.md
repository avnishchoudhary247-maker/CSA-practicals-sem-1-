# Practical 1 & 2 — Machine design and fetch cycle

## Practical 1: Create a machine

Create a new machine in CPU Sim and save it as `BasicComputer.cpu`.

### Register set

| Register | Width | Initial value | Purpose |
|---|---:|---:|---|
| IR | 16 bits | 0 | Instruction register |
| DR | 16 bits | 0 | Data register |
| AC | 16 bits | 0 | Accumulator |
| AR | 12 bits | 0 | Address register |
| PC | 12 bits | 0 | Program counter |
| I | 1 bit | 0 | Indirect-addressing bit |
| E | 1 bit | 0 | Carry / extend bit |

Add a 1-bit halt condition bit if your CPU Sim machine setup requires a separate halt flag.

### Memory

- Name: `M`
- Number of words: `4096`
- Bits per word: `16`

### Instruction format

A 16-bit instruction is arranged as:

- Bit 15: I (indirect/direct selection)
- Bits 14–12: opcode (3 bits)
- Bits 11–0: address (12 bits)

Register-reference and I/O instructions use fixed 16-bit instruction codes.

### Instruction codes

| Instruction | Code / opcode |
|---|---|
| AND | 0xxx |
| ADD | 1xxx |
| LDA | 2xxx |
| STA | 3xxx |
| BUN | 4xxx |
| BSA | 5xxx |
| ISZ | 6xxx |
| CLA | 7800 |
| CLE | 7400 |
| CMA | 7200 |
| CME | 7100 |
| CIR | 7080 |
| CIL | 7040 |
| INC | 7020 |
| SPA | 7010 |
| SNA | 7008 |
| SZA | 7004 |
| SZE | 7002 |
| HLT | 7001 |
| INP | F800 |
| OUT | F400 |

The indirect memory-reference variants use the corresponding indirect opcode encodings listed in the course syllabus.

### Core micro-operations to define

Create microinstructions that perform these transfers/operations:

- `PC -> AR`
- `M[AR] -> IR`
- `PC + 1 -> PC`
- `IR(0–11) -> AR`
- `M[AR] -> DR`
- `DR -> AC`
- `AC + DR -> AC`, with carry stored in `E`
- `AC -> M[AR]`
- `AR -> PC`
- `AC <- 0`
- `AC <- NOT AC`
- `AC <- AC + 1`
- `E <- NOT E`
- `INP -> AC`
- `AC -> OUT`
- `HLT`

Define the machine instructions by connecting each instruction to its required microinstruction sequence. For example, `LDA` reads memory into `DR` and transfers `DR` to `AC`; `STA` writes `AC` to memory; `BUN` transfers `AR` to `PC`.

## Practical 2: Fetch routine

Create the fetch sequence in this order:

1. `PC -> AR`
2. `M[AR] -> IR`
3. `PC + 1 -> PC`
4. `IR(0–11) -> AR`
5. Decode `IR`

### What to observe

Single-step the fetch sequence and note:

- Before fetch: PC points to the next instruction.
- After step 1: AR contains the old PC.
- After step 2: IR contains the instruction fetched from memory.
- After step 3: PC has increased by one.
- After step 4: AR contains the address field from IR.
- After step 5: the control unit decodes the opcode.

**Result:** The machine design and fetch routine are complete after you create them, save the machine, and verify the sequence in CPU Sim.
