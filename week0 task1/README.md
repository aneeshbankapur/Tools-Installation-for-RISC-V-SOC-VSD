# SoC / ASIC Design Flow

This document explains the typical design flow for a **System on a Chip (SoC)** or **Application-Specific Integrated Circuit (ASIC)**.  
It shows how a high-level concept is transformed into a **physical chip ready for manufacturing**.

<p align="center">
  <img src="https://github.com/aneeshbankapur/Tools-Installation-for-RISC-V-SOC-VSD/blob/f7398a4cb9915132c9f4624ea548d33e3d33c08f/week0%20task1/SOC%20design%20flow.png">
</p>

---
## 📌 Stage 1: Chip Modelling & Specification (O1)

**Goal:** Define what the chip should do (conceptual phase).

- **Specs (C Model):**  
  Start with a high-level functional model, usually written in **C/C++**.  
  This model defines the required functionality and serves as the **golden reference**.

- **C-language Testbench:**  
  A test environment is created in **C** to validate the C model against the specifications.  
  Ensures initial requirements are correct and achievable.

---

## 📌 Stage 2: RTL Architecture & Design (O2)

**Goal:** Translate the abstract specification into hardware description.

- **RTL Design:**  
  Engineers describe the hardware at **Register-Transfer Level (RTL)** using **Verilog** or **VHDL**.  
  This RTL code acts as the **blueprint** of the hardware.

- **SoC Verification:**  
  RTL is continuously simulated and compared against the **C model output** (indicated by the green loop in diagrams).  
  Ensures the hardware faithfully matches the original specification.

---

## 📌 Stage 3: Synthesis & SoC Integration (O3)

**Goal:** Convert RTL into a gate-level representation and assemble components.

- **Synthesis:**  
  RTL code → **Gate-Level Netlist** using **EDA tools**.  
  The netlist describes the design in terms of logic gates (AND, OR, NAND, etc.).

- **Component Integration:**  
  Modern SoCs integrate multiple components:
  - **Processor**: Core CPU (ARM, RISC-V, etc.) – usually provided as synthesizable RTL.
  - **Peripherals/IPs**: Standard IP blocks (USB, PCIe, Memory Controller).
  - **Macros**: Custom synthesized blocks.
  - **Analog IPs**: Pre-designed analog blocks (PLLs, ADCs). Provided as **Hard Macros (fixed layout)** with functional RTL models.

- **SoC Integration:**  
  Combine digital netlists + analog blocks → **Top-level SoC Netlist**.

---

## 📌 Stage 4: Physical Design (RTL → GDS)

**Goal:** Convert logical design into a **physical silicon layout**.

- **Floorplanning:** High-level placement of major blocks on the chip.  
- **Placement:** Precise location of every logic gate.  
- **Routing:** Drawing interconnects (metal wires) between gates/blocks.  

- **Hard vs Soft Macros:**  
  - **Hard Macros (HM):** Pre-defined physical layout (e.g., Analog IPs).  
  - **Soft Macros/Soft Logic:** Synthesized from RTL (e.g., CPU core).  

---

## 📌 Stage 5: Sign-off & Tape-out(O4)

**Goal:** Final verification before chip manufacturing.

- **GDSII:** Final file format containing the exact **geometric layout** for fabrication.  
- **Checks:**
  - **DRC (Design Rule Check):** Ensures layout follows foundry rules (wire width, spacing, etc.).  
  - **LVS (Layout vs. Schematic):** Confirms layout matches the netlist (electrical correctness).  

- **Tape-out:**  
  Once all checks pass, the **GDSII** file is sent to the foundry → **chip fabrication begins**.

---

## ✅ Summary Flow

1. **Chip Modelling & Specification** → Define functionality (C Model).  
2. **RTL Design & Verification** → Hardware description (Verilog/VHDL).  
3. **Synthesis & Integration** → Netlist + component assembly.  
4. **Physical Design** → RTL → GDSII (layout generation).  
5. **Sign-off & Tape-out** → Verification + send to foundry.  

## O1=O2=O3=O4
