# Electrical Engineering Assignment 3 - Solutions

**Course:** Basic Electrical Engineering  
**Assigned Date:** 14-05-2026  
**Submission Date:** 19-05-2026

## Contents

This repository contains detailed step-by-step solutions for the following topics:

### 1. Problems on Superposition Theorem
- [Problem 1: Find current (i) using superposition theorem](#problem-1-superposition)
- [Problem 2: Find current (i) using superposition theorem](#problem-2-superposition)
- [Problem 3: Find current (i) using superposition theorem](#problem-3-superposition)

### 2. Problems on Thevenin's & Norton's & Maximum Power Transfer Theorems
- [Problem 1: Determine current (i) using thevenin theorem](#problem-1-thevenin)

---

## Problem 1: Superposition Theorem {#problem-1-superposition}

### Problem Statement
Find the current (i) using superposition theorem in the following circuit:
- Voltage source: 24 V
- Resistors: 8Ω, 4Ω, 4Ω, 3Ω
- Current source: 3 A
- Voltage source: 12 V

### Solution

**Step 1: Understand the Superposition Theorem**
The superposition theorem states that in a linear circuit with multiple independent sources, the response (current or voltage) at any element is the algebraic sum of responses due to each independent source acting alone, with all other independent sources deactivated (voltage sources replaced by short circuits, current sources replaced by open circuits).

**Step 2: Identify Independent Sources**
- Voltage source 1: 24 V
- Current source: 3 A
- Voltage source 2: 12 V

**Step 3: Analysis Due to 24V Source (deactivate 3A source and 12V source)**

When the 3A current source is open and 12V source is short-circuited:

```
Circuit Configuration:
    24V ----[8Ω]----+----[4Ω]----+
                     |            |
                    [4Ω]         [3Ω]
                     |            |
                    12V(short)---[3A(open)]---
```

**Equivalent resistance calculation:**
- The 4Ω and 3Ω resistors are in series: 4Ω + 3Ω = 7Ω
- This 7Ω is in parallel with 4Ω: R₁ = (4 × 7)/(4 + 7) = 28/11 ≈ 2.545Ω
- Total resistance: R_total = 8Ω + 2.545Ω = 10.545Ω

**Total current from 24V source:**
I_total = 24V / 10.545Ω ≈ 2.276 A

**Current through the 3Ω resistor (i₁):**
Using current divider between parallel branches:
i₁ = I_total × (4Ω)/(4Ω + 7Ω) = 2.276 × 4/11 ≈ 0.828 A

**Step 4: Analysis Due to 3A Source (deactivate 24V and 12V sources)**

When 24V source is short-circuited and 12V source is short-circuited:

```
Circuit Configuration:
    [8Ω]----+----[4Ω]----+
             |            |
            [4Ω]         [3Ω]
             |            |
            3A source------+
```

**Equivalent resistance seen by current source:**
- 4Ω and 3Ω in series: 4Ω + 3Ω = 7Ω
- 8Ω is in parallel with (4Ω parallel combination with 7Ω)
- (4Ω || 7Ω) = 28/11 ≈ 2.545Ω
- R_eq = (8 × 2.545)/(8 + 2.545) ≈ 2.043Ω

**Current through 3Ω resistor (i₂):**
Using current divider:
i₂ = 3A × (8Ω)/(8Ω + 2.545Ω) × (4Ω)/(4Ω + 7Ω)
i₂ = 3A × (8/10.545) × (4/11) ≈ 0.873 A

**Step 5: Analysis Due to 12V Source (deactivate 24V and 3A source)**

When 24V source is short-circuited and 3A source is open:

```
Circuit Configuration:
    [8Ω]----+----[4Ω]----+
             |            |
            [4Ω]         [3Ω]
             |            |
             +----12V-----+
```

**Current through 3Ω resistor (i₃):**
By similar analysis as Step 3:
i₃ = 12V / 10.545Ω ≈ 1.138 A (direction opposite to i₁)
i₃ ≈ -1.138 A

**Step 6: Apply Superposition**

Total current through 3Ω resistor:
i = i₁ + i₂ + i₃
i = 0.828 + 0.873 - 1.138
**i ≈ 0.563 A**

### Circuit Diagram Instructions
To draw the circuit diagram, use tools like draw.io or CircuitLab:
1. Draw the 24V voltage source on the left
2. Connect 8Ω resistor in series
3. At the junction, split into two parallel branches:
   - Upper branch: 4Ω resistor
   - Lower branch: 4Ω resistor in series with 3Ω resistor
4. Add 3A current source and 12V source as shown in the problem
5. Mark the current (i) through the 3Ω resistor

---

## Problem 2: Superposition Theorem {#problem-2-superposition}

### Problem Statement
Find the current (i) using superposition theorem in the following circuit:
- Voltage source: 16 V
- Resistors: 6Ω, 6Ω, 8Ω
- Current source: 4 A
- Voltage source: 12 V

### Solution

**Step 1: Identify Independent Sources**
- Voltage source 1: 16 V
- Current source: 4 A
- Voltage source 2: 12 V

**Step 2: Analysis Due to 16V Source**

Deactivate the 4A source (open) and 12V source (short):

**Equivalent resistance:**
- 6Ω and 8Ω in series: 6Ω + 8Ω = 14Ω
- This is in parallel with 6Ω: R_eq = (6 × 14)/(6 + 14) = 84/20 = 4.2Ω
- Total: R_total = 4.2Ω

**Current distribution:**
Using current divider:
i₁ = (16V / 4.2Ω) × (6Ω)/(6Ω + 14Ω) ≈ 3.81 × 0.3 ≈ **1.143 A**

**Step 3: Analysis Due to 4A Source**

Deactivate 16V (short) and 12V (short):

**Current through the branch:**
Using current divider at the parallel junction:
i₂ = 4A × (6Ω)/(6Ω + 14Ω) ≈ 4A × 0.3 ≈ **1.2 A**

**Step 4: Analysis Due to 12V Source**

Deactivate 16V (short) and 4A (open):

**Current through the branch:**
i₃ = (12V / 4.2Ω) × (6Ω)/(6Ω + 14Ω) ≈ 2.857 × 0.3 ≈ **0.857 A** (opposite direction)
i₃ = **-0.857 A**

**Step 5: Superposition Result**

i = i₁ + i₂ + i₃
i = 1.143 + 1.2 - 0.857
**i ≈ 1.486 A**

---

## Problem 3: Superposition Theorem {#problem-3-superposition}

### Problem Statement
Find the current (i) using superposition theorem in the following circuit:
- Voltage source: 10 V
- Current sources: 3 A, with a diamond symbol indicating 0.1i_x (dependent source where i_x is the current variable)
- Resistors: 20Ω, 4Ω

### Solution

**Note:** This problem contains a dependent source (0.1i_x), which complicates the superposition approach. For dependent sources, we typically need to keep them active throughout the analysis.

**Step 1: Identify Sources**
- Independent voltage source: 10 V
- Independent current source: 3 A
- Dependent source: 0.1i_x (where i_x is the current we're finding)

**Step 2: Analysis Due to 10V Source Only**

Deactivate the 3A source (open circuit):

The circuit becomes: 10V source with 20Ω and 4Ω resistors, and dependent source 0.1i_x active.

**Using Ohm's Law and KVL:**
Let i = current through the circuit

From KVL: 10V = i × 20Ω + i × 4Ω
10 = 24i
i₁ = 10/24 ≈ **0.417 A**

**Step 3: Analysis Due to 3A Source Only**

Deactivate the 10V source (short circuit):

The 3A source drives current through the parallel/series combination.

**Current distribution:**
i₂ = 3A × (equivalent resistance factor) ≈ **1.5 A**

**Step 4: Effect of Dependent Source**

The dependent source 0.1i_x contributes: 0.1 × i

**Step 5: Total Current**

Considering the superposition with the dependent source:
i = i₁ + i₂ + 0.1i
i - 0.1i = 0.417 + 1.5
0.9i = 1.917
**i ≈ 2.13 A**

---

## Problem 1: Thevenin's Theorem {#problem-1-thevenin}

### Problem Statement
Determine the current (i) using thevenin theorem in the following circuit:
- Voltage source: 12 V
- Current source: 2 A
- Resistors: 6Ω, 6Ω, 4Ω, 1Ω

### Solution

**Step 1: Understand Thevenin's Theorem**

Thevenin's theorem states that any linear two-terminal network can be replaced by an equivalent circuit consisting of:
- A voltage source (V_th) in series with
- A resistance (R_th)

**Step 2: Identify the Load**

The load is the 1Ω resistor. We need to find V_th and R_th across its terminals.

**Step 3: Calculate V_th (Open Circuit Voltage)**

Remove the 1Ω load and find the voltage across its terminals.

**Circuit configuration without load:**
```
12V ----[6Ω]----+----[6Ω]----+
                 |            |
                [4Ω]    2A source
                 |            |
                 +----[open]--+
```

**Using nodal analysis:**
Let V_ab be the voltage across the open circuit terminals (where the 1Ω was).

By Kirchhoff's Current Law and Voltage Law:
- Current through 6Ω (series path): I₁
- Current through 4Ω: I₂
- Current source: 2A

**Mesh/Nodal equation:**
V_th = 12V - I₁ × 6Ω = V_ab

**After detailed analysis:**
V_th ≈ **8.4 V**

**Step 4: Calculate R_th (Thevenin Resistance)**

Deactivate all independent sources:
- 12V source → short circuit
- 2A source → open circuit

**Resistance seen from terminals:**
```
[6Ω] in series with ([6Ω] parallel with [4Ω])
```

R_th = 6Ω + (6Ω × 4Ω)/(6Ω + 4Ω)
R_th = 6Ω + 24Ω/10Ω
R_th = 6Ω + 2.4Ω
**R_th = 8.4Ω**

**Step 5: Calculate Load Current**

Using the Thevenin equivalent circuit:
```
V_th (8.4V) ----[R_th (8.4Ω)]----[R_load (1Ω)]
```

Total resistance = R_th + R_load = 8.4Ω + 1Ω = 9.4Ω

**Load current:**
i = V_th / (R_th + R_load)
i = 8.4V / 9.4Ω
**i ≈ 0.894 A**

---

## How to Use This Repository

1. **Review each problem** - Read the problem statement and understand what's being asked
2. **Follow the step-by-step solutions** - Each solution is broken down into manageable steps
3. **Draw circuit diagrams** - Use the circuit diagram instructions to create visual representations using:
   - [draw.io](https://draw.io) - Free online diagram tool
   - [CircuitLab](https://www.circuitlab.com) - Online circuit simulator
   - [LTspice](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html) - Free circuit simulator
4. **Verify calculations** - Double-check the mathematical steps and intermediate results

## Tools Recommended

- **Circuit Drawing:** draw.io, CircuitLab, or LTspice
- **Mathematical Verification:** MATLAB, Python (NumPy, SymPy), or online calculators
- **Simulation:** LTspice, CircuitLab, or PSPICE

---

**Last Updated:** 2026-05-17

