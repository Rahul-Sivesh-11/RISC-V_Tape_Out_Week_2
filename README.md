# RISC-V_Tape_Out_Week_2
This repository showcases the functional modeling, simulation, and FPGA implementation of the VSDBabySoC, a compact System-on-Chip (SoC) built around a RISC-V architecture. The design brings together the RVMYTH processor core, a PLL, and a DAC module.
## Introduction
### VSDBabySoC Overview

**VSDBabySoC** is a compact yet powerful **System-on-Chip (SoC) built on the RISC-V architecture**, created to:

- Integrate and validate various open-source IP cores.  
- Perform calibration of analog modules such as the DAC.  
- Act as an educational platform for understanding **SoC design principles** and **RTL verification techniques**.  

---

### Main Components

- **RVMYTH:** A lightweight RISC-V processor core.  
- **PLL:** An 8x phase-locked loop ensuring consistent and reliable clock generation.  
- **DAC:** A 10-bit digital-to-analog converter enabling communication with analog systems.  

---

### Operational Summary

1. **Startup & Clock Setup:**  
   The BabySoC triggers the PLL to produce a stable clock signal for system timing.  

2. **Computation Stage:**  
   The RVMYTH core performs data operations and updates registers that interface with the DAC.  

3. **Analog Output Phase:**  
   The DAC translates digital data from the CPU into analog signals for external use.  
## Objective

- Gain a strong understanding of **SoC design concepts** and **functional verification**.  
- Execute **VSDBabySoC simulations** using **Icarus Verilog** and **GTKWave** for waveform analysis.  
- Perform **FPGA synthesis** with **Yosys** to explore **gate-level implementation and mapping**.
## 🧩 BabySoC Modules

| Module/File                       | Description                                         |
| --------------------------------- | --------------------------------------------------- |
| `avsddac.v`                       | Implements the 10-bit DAC responsible for analog output. |
| `avsdpll.v`                       | Generates a stable clock using an 8x phase-locked loop (PLL). |
| `clk_gate.v`                      | Provides clock gating control to optimize power usage. |
| `pseudo_rand.sv`                  | Produces pseudo-random data sequences for testing. |
| `pseudo_rand_gen.sv`              | Auxiliary module to generate pseudo-random input signals in simulations. |
| `rvmyth.tlv`                      | Defines the **RVMYTH** RISC-V CPU core written in TL-Verilog. |
| `testbench.v`                     | Primary simulation testbench for verifying SoC behavior. |
| `testbench.rvmyth.post-routing.v` | Post-routing testbench used for timing and netlist validation. |
| `vsdbabysoc.v`                    | Top-level integration module connecting all SoC components. |
## Simulation Setup

**Tools Required:**

* **Icarus Verilog (`iverilog`)** – Compile Verilog modules.
* **GTKWave** – View `.vcd` waveform files for signal analysis.

---

## Simulation Steps

1. **Clone the BabySoC repo:**

```bash
git clone https://github.com/manili/VSDBabySoC
cd VSDBabySoC/src/module/
```

2. **Compile Verilog modules:**

```bash
iverilog -o ../../output/babysoc_sim.out -I ../include *.v testbench.v
```

3. **Run simulation:**

```bash
./../../output/babysoc_sim.out
```

4. **Open waveform in GTKWave:**

```bash
gtkwave ../../output/babysoc_sim.vcd
```
