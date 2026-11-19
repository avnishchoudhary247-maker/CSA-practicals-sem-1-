# Practical record notes (1–11)

Use this file as a concise record outline. Fill in actual observations and attach your own CPU Sim screenshots after running the programs.

## 1. Machine design
**Aim:** Create Mano's Basic Computer in CPU Sim.  
**Configuration:** IR/DR/AC = 16 bits; AR/PC = 12 bits; I/E = 1 bit; memory = 4096 × 16.  
**Result:** Fill after creating and saving `BasicComputer.cpu`.

## 2. Fetch routine
**Aim:** Implement the fetch sequence.  
**Sequence:** PC→AR; M[AR]→IR; PC+1→PC; IR(0–11)→AR; Decode IR.  
**Result:** Fill after single-stepping the fetch routine.

## 3. Addition
**Aim:** Read two integers and output their sum.  
**Sample test:** 25 and 17 should produce 42.

## 4. Subtraction
**Aim:** Subtract the second integer from the first.  
**Sample test:** 18 and 50 should produce -32.

## 5. Logical operations
**Aim:** Perform AND, OR, NOT, XOR, NOR and NAND.  
**Sample test:** A=12, B=10. Expected signed outputs: AND=8, OR=14, NOT A=-13, NOT B=-11, XOR=6, NOR=-15, NAND=-9.

## 6. Memory-reference instructions
**Aim:** Demonstrate ADD, LDA, STA, BUN and ISZ.  
**Sample test:** Repeated addition 5 × 3 should output 15.

## 7. Register-reference instructions
**Aim:** Demonstrate CLA, CMA, CME and HLT.  
**Observation:** Record AC, E, PC, AR and IR in decimal after each instruction.

## 8. Register-reference instructions
**Aim:** Demonstrate INC, SPA, SNA and SZE.  
**Observation:** Record AC, E, PC, AR and IR in decimal after each instruction.

## 9. Rotate instructions
**Aim:** Demonstrate CIR and CIL.  
**Observation:** Record AC, E, PC, AR and IR in decimal after each instruction.

## 10. Sum until negative
**Aim:** Add entered integers until a negative non-zero number is read; exclude that final value.  
**Sample input:** 4, 10, 0, 6, -3. Expected output: 20.

## 11. Sum until zero
**Aim:** Add entered integers until zero is read.  
**Sample input:** 8, 12, -5, 0. Expected output: 15.

---
**Reminder:** These are expected test cases and record notes, not evidence that the simulator has been run. Enter your actual register values, console output, and screenshots after testing.
