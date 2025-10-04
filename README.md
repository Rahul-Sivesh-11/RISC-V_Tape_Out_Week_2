# RISC-V_Tape_Out_Week_2
This repository showcases the functional modeling, simulation, and FPGA implementation of the VSDBabySoC, a compact System-on-Chip (SoC) built around a RISC-V architecture. The design brings together the RVMYTH processor core, a PLL, and a DAC module.
## Introduction
### VSDBabySoC Overview

**VSDBabySoC** is a compact yet powerful **System-on-Chip (SoC) built on the RISC-V architecture**, created to:

- Integrate and validate various open-source IP cores.  
- Perform calibration of analog modules such as the DAC.  
- Act as an educational platform for understanding **SoC design principles** and **RTL verification techniques**.  

---

### 🔧 Main Components

- **RVMYTH:** A lightweight RISC-V processor core.  
- **PLL:** An 8x phase-locked loop ensuring consistent and reliable clock generation.  
- **DAC:** A 10-bit digital-to-analog converter enabling communication with analog systems.  

---

### ⚙️ Operational Summary

1. **Startup & Clock Setup:**  
   The BabySoC triggers the PLL to produce a stable clock signal for system timing.  

2. **Computation Stage:**  
   The RVMYTH core performs data operations and updates registers that interface with the DAC.  

3. **Analog Output Phase:**  
   The DAC translates digital data from the CPU into analog signals for external use.  
