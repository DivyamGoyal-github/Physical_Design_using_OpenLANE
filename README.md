## 🚀 Introduction

### Why Open-Source EDA Matters

EDA tools are critical for the design, simulation, and verification of integrated circuits. Open-source EDA democratizes chip design, removing licensing barriers and fostering collaborative innovation. Sky130 and OpenLANE are two of the most accessible platforms for learning and building digital ICs from scratch.

***

## 🛠️ How to Talk to Computers

### Abstraction in Digital Design

Computers operate on instructions at varying abstraction levels—software (high-level languages, OS), hardware (logic gates, flip-flops), and everything between. The pathway from code to silicon involves translation steps, each handled by specialized tools and flows.

- **Software Applications → Hardware:** Higher-level programs are converted by compilers and synthesis tools into logic that can be etched onto silicon.

***

## 🧩 Introduction to RISC-V

RISC-V is an open, royalty-free instruction set architecture (ISA) designed for flexibility and extensibility.

- **Modular ISA:** Core instructions (base integer set) plus optional extensions for multiplication, atomicity, floating-point, etc.
- **Open Ecosystem:** Enables customization for research, education, embedded systems, or high-performance applications.
- **Support for Multiple Privilege Modes:** From lightweight embedded cores to feature-rich platforms supporting operating systems.

***

## 🏗️ SoC Design and OpenLANE

### Components of Digital ASIC Design

Open-source digital ASIC design typically involves:

- **RTL (Register Transfer Level):** The hardware description code, generally written in Verilog or VHDL.
- **Synthesis:** Converts RTL to gate-level netlist using logic libraries.
- **Floorplanning and Placement:** Organizes logic elements physically on the die.
- **Routing:** Connects standard cells with metal interconnects.

### RTL2GDS Flow (Simplified)

- **RTL (Verilog) → Synthesis → Floorplan → Placement → Routing → GDSII (final tapeout layout).**
- OpenLANE automates this flow specifically for Sky130 PDK, handling each step and offering hooks for manual intervention or advanced configuration.

***

## ⚙️ OpenLANE and Sky130 PDK

### OpenLANE Overview

OpenLANE is an open-source digital ASIC flow built around the Sky130 PDK.

- Automated digital design flow (RTL → GDSII).
- Integrates multiple tools (yosys for synthesis, Magic for layout viewing, OpenROAD utilities for placement/routing).

### Key Features

- Scriptable and repeatable design flow.
- Detailed directory structure for managing design, scripts, reports, and resulting layout files.

***

## 📂 Exploring OpenLANE Directory Structure

OpenLANE organizes projects into directories for:

- **Designs:** User circuits and configurations.
- **Runs:** Per-design execution logs, results, and intermediate files.
- **PDK:** Standard cell libraries, LEF/DEF files, rules, etc.
- **Reports:** Timing, area, and metrics for each design step.

***

## 🏞️ Floorplanning and Placement

### Good Floorplan vs. Bad Floorplan

A well-thought-out floorplan improves routability, performance, and power integrity:

- **Utilization Factor:** Balances logic density.
- **Aspect Ratio:** Ensures die fits target packaging.
- **Pre-placed Cells & Decoupling Capacitors:** Ensures robust power delivery.
- **Pin Placement:** Affects timing, congestion, and ease of testing.

### Running Floorplan in OpenLANE

- OpenLANE scripts automate much of the setup; designers review output for errors and optimization opportunities.

***

## 🧪 Cell Design and Characterization

### From Schematic to Spice

- **CMOS Inverter as a Reference:** Begin with basic gates (inverter), create layout in Magic, simulate in ngspice.
- **Characterization:** Extract delay, power, threshold characteristics from SPICE simulations.

### Key Timing Parameters

- **Propagation Delay:** Time required for signal to propagate through a gate.
- **Transition Time:** Slope of the output signal, critical for performance.
- **Timing Thresholds:** Voltage levels at which logic state transitions occur.

***

## 🖥️ Sky130 Tech and Layout Labs

- **Magic Tool Use:** Layout editing and view, DRC checks, LEF/DEF generation from Magic-extracted layouts.
- **PDK Files:** Provide standardized models and DRC rules for process-correct design.
- **Troubleshooting Labs:** Real-world exercises like fixing DRC errors, adjusting poly/metal spacing, and interpreting Magic errors.

***

## 🕑 Timing Analysis and Clock Tree

### OpenSTA for Timing

- **Clock Setup/Hold Analysis:** Ensures that clocked elements (FFs/latches) receive valid signals at the correct time.
- **Post-synthesis/CTS Analysis:** Includes routing details and real clock network delays.

### TritonCTS for Clock Synthesis

- **H-Tree Algorithm:** Balances clock signal distribution across chip.
- **Signal Integrity:** Crosstalk and shielding methods to prevent spurious behavior.

***

## 🛣️ Routing, DRC, and Final Tapeout

### TritonRoute

- Handles detailed interconnect routing, respects routing guides, and honors DRC constraints.
- Outputs DRC-clean GDSII files for fabrication.

### Power Distribution Network (PDN)

- **Generation of Power Straps**
- Robust connection between standard cells and chip-level supply rails.

***

## 📝 Useful References

- RISC-V ISA official site
- OpenLANE: https://github.com/The-OpenROAD-Project/OpenLane
- SkyWater Sky130: https://github.com/google/skywater-pdk
- Magic VLSI: http://opencircuitdesign.com/magic/

***
