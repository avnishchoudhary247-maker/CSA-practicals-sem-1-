# Computer System Architecture — CPU Sim Practicals

**Course:** B.Sc. (Hons.) Computer Science  
**College:** Ramanujan College, University of Delhi  
**Simulator required by syllabus:** CPU Sim 3.6.9 or higher  
**Architecture:** Mano's Basic Computer (16-bit)

This repository contains assembly source files for Practicals 3–11 and step-by-step machine-design/fetch-sequence records for Practicals 1–2.

> **Important verification note:** The assembly files are prepared for the Mano-style instruction set shown in the University of Delhi syllabus. They have not been executed in CPU Sim 3.6.9 in this environment. Open them in the simulator, assemble, run, and save your own screenshots before treating them as verified practical work. Practicals 1–2 require creating and saving the machine inside CPU Sim; a written machine specification is included, not a pre-verified `.cpu` machine file.

## Repository structure

```text
.
├── README.md
├── Machine_Setup_P01_P02.md
├── Programs/
│   ├── P03_ADD.a
│   ├── P04_SUBTRACT.a
│   ├── P05_LOGICAL.a
│   ├── P06_MEMORY_REFERENCE.a
│   ├── P07_REGISTER_REFERENCE_1.a
│   ├── P08_REGISTER_REFERENCE_2.a
│   ├── P09_CIR_CIL.a
│   ├── P10_SUM_UNTIL_NEGATIVE.a
│   └── P11_SUM_UNTIL_ZERO.a
└── Practical_Reports/
    └── Practical_01_to_11_Notes.md
```

## How to use in CPU Sim

1. Open CPU Sim 3.6.9 or higher on a computer.
2. Create the Mano Basic Computer machine using `Machine_Setup_P01_P02.md`, then save it as `BasicComputer.cpu`.
3. Open one `.a` file from `Programs/`.
4. Use **Assemble & Load**. Resolve any syntax differences shown by your CPU Sim version before running.
5. Run or single-step the program. Enter the requested input values in the console when prompted.
6. Record the actual output and register values, and save screenshots in a `Screenshots/` folder.
7. Upload this repository to GitHub. Do not upload fabricated screenshots.

## Instruction set used

- Memory reference: `AND`, `ADD`, `LDA`, `STA`, `BUN`, `ISZ`
- Register reference: `CLA`, `CMA`, `CME`, `CIR`, `CIL`, `INC`, `SPA`, `SNA`, `SZA`, `SZE`, `HLT`
- I/O: `INP`, `OUT`

The syllabus also lists indirect variants and additional instructions. These practical programs use the subset required by Practicals 3–11.

## Notes

- Values are 16-bit two's-complement integers: -32768 to 32767.
- Arithmetic can overflow outside this range.
- `CMA` complements all 16 bits, so `NOT 12` is -13 in signed decimal.
- Practical 5 implements the logical functions using the Basic Computer's `AND` and `CMA` operations.
- Practical 10 excludes the terminating negative value; Practical 11 excludes the terminating zero.
