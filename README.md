# 🧠 Parameterized True Dual-Port RAM with Self-Checking Verification

## 📌 Overview

This project implements a **Parameterized True Dual-Port RAM using Verilog HDL**. The design uses a shared memory array accessible through two ports, allowing independent read and write operations controlled by individual enable and write-enable signals.

The project focuses on RTL design, memory modeling, self-checking verification, and simulation-based analysis using **AMD Xilinx Vivado 2025.1**.

## 🎯 Objectives

- Design a parameterized True Dual-Port RAM using Verilog HDL.
- Implement two independent memory access ports.
- Understand synchronous memory read and write operations.
- Develop a self-checking testbench to verify memory functionality.
- Test simultaneous access and boundary address conditions.
- Analyze RTL structure and simulation waveforms.
- Explore FPGA synthesis and resource utilization.

## ⚙️ Working Principle

The design consists of a shared memory array and two access ports, Port A and Port B. Each port has its own address, data input, data output, enable, and write-enable signals.

When a port is enabled, it performs the operation specified by its write-enable signal. Write operations store input data at the selected address, while read operations retrieve data from the memory.

Both ports use a common clock. Simultaneous operations on different addresses can be tested independently. When both ports access the same address, read/write collision behavior depends on the RTL implementation and must be verified.

### Main Signals

**Port A**
- `addr_a[7:0]` — Address input
- `din_a[7:0]` — Data input
- `dout_a[7:0]` — Data output
- `en_a` — Port enable
- `we_a` — Write enable

**Port B**
- `addr_b[7:0]` — Address input
- `din_b[7:0]` — Data input
- `dout_b[7:0]` — Data output
- `en_b` — Port enable
- `we_b` — Write enable

**Common Signal**
- `clk` — Shared clock input

## 🧩 Block Diagram

The block diagram illustrates the RAM architecture, showing the shared memory and the two independent access interfaces.

Add the block diagram image to the `docs/` folder using the filename `rtl_block_diagram.png`.

![Parameterized True Dual-Port RAM Block Diagram](docs/rtl_block_diagram.png)

## 💻 Tools and Technologies

- **Hardware Description Language:** Verilog HDL
- **Design Methodology:** RTL Design
- **Memory Architecture:** True Dual-Port RAM
- **Design and Synthesis Tool:** AMD Xilinx Vivado 2025.1
- **Verification:** Verilog Testbench and Self-Checking Assertions/Tasks
- **Analysis:** RTL Schematic and Simulation Waveform

## 📂 Project Structure

```text

parameterized-dual-port-ram/
│
├── README.md
│
├── rtl/
│   └── parameterized_ram.v
│
├── testbench/
│   └── ram_testbench.v
│
└── docs/
    ├── rtl_block_diagram.png
    └── simulation_waveform.png

```

*The synthesis utilization screenshot is optional and should be added after successful synthesis. Keep filenames consistent with the actual files uploaded to GitHub.*

## 🧪 Simulation and Verification

A self-checking Verilog testbench is used to apply input sequences to both ports and compare the observed outputs against expected values.

### Test Scenarios

- Memory read and write operations.
- Simultaneous access to different memory addresses.
- Boundary address testing, including addresses 0 and 255.
- Selected same-address read/write scenarios.
- Automated PASS/FAIL reporting using a checking task.

### Simulation Waveform

The simulation waveform can be included to demonstrate clock transitions, port control signals, addresses, input data, and output data during the test scenarios.

Add the waveform screenshot to `docs/simulation_waveform.png`.

![True Dual-Port RAM Simulation Waveform](docs/simulation_waveform.png)

### Verification Results

The testbench includes pass/fail counters to help identify mismatches between expected and observed outputs.

Record the final verification results here after running the complete testbench. Include only the test scenarios that have actually been executed.

## 🔧 FPGA Synthesis and Resource Utilization

The RTL design can be synthesized using AMD Xilinx Vivado 2025.1 to examine the inferred hardware structure and estimated FPGA resource usage.

The utilization report may include:

- Look-Up Tables (LUTs)
- Flip-flops
- Block RAM resources
- Other relevant FPGA resource estimates

The synthesis utilization screenshot can be added as `docs/synthesis_utilization.png` after synthesis completes successfully.

**Note:** This project is being developed and analyzed on a laptop without a physical FPGA board. Physical hardware testing and board-level validation are not claimed.

## 📚 Key Learning Outcomes

- Understanding parameterized memory design in Verilog HDL.
- Implementing a shared memory with two access ports.
- Developing self-checking testbenches.
- Verifying memory access and boundary conditions.
- Analyzing RTL schematics and simulation waveforms.
- Learning the FPGA synthesis and resource estimation workflow.

## 🚀 Future Enhancements

- Expand randomized testing and verification coverage.
- Verify port enable and output-hold behavior.
- Define and test same-address read/write collision behavior.
- Analyze FPGA resource utilization after successful synthesis.
- Explore implementation on a compatible FPGA development board.

## 👨‍💻 Author

**Suhair K**

Electronics and Communication Engineering

## 📄 License

No license has been specified for this repository yet.
