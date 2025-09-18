
# RISC-V Hirdesh Week 0 🚀

This repository is a part of the **VSD RISC-V "Silicon to Tapeout" program** by **Hirdesh Pamnani** (4th Year, ECE, JSSATEN).  
It documents my learning journey towards designing, verifying, and taping out a RISC-V based chip.

---

## 📖 Program Overview
The program focuses on learning **VLSI SoC design flow** – from chip specification, RTL coding, synthesis, floorplanning, and finally GDSII (tapeout).  

RISC-V is an **open-source Instruction Set Architecture (ISA)**, widely adopted in industry and academia because of:
- ✅ Flexibility & Custom Extensions  
- ✅ Open ecosystem (no license fees)  
- ✅ Use in low-power IoT devices, AI accelerators, microcontrollers, and high-performance CPUs  
- ✅ Backed by strong community and silicon-proven chips  

---

# 📂 Repository Structure

```
Risc_V_Hirdesh_week0/
│
├── README.md   <- main documentation
├── tools/      <- screenshots of tool installations (to be added later)
└── summary/    <- notes & learnings (week-wise)
```

---

## 📺 Week 0 – Learnings

### 🔹 Video Summary 
1. **Chip Modeling (O1)**  
   - Initial specification done using C model.  
   - Testbench written in C language for functional validation.  

2. **RTL Architecture (O2)**  
   - Soft copy of hardware created in RTL (Verilog).  
   - Processor, peripherals/IPs, macros, and analog IPs are modeled.  

3. **SoC Integration (O3)**  
   - Components like Processor, GPIOs, and IPs are integrated at SoC level.  
   - Gate-level netlist generated and synthesized.  
   - Floorplanning, placement, CTS, and routing lead to GDSII.  
   - DRC/LVS checks ensure manufacturability.  

4. **Final Verification (O4)**  
   - At the end, outputs O1 = O2 = O3 = O4 must be consistent.  
   - This validates that chip implementation matches initial specifications.  

📌 Key Learning: The **testbench is always in C language**, and the **SoC design flow ensures correctness from spec → RTL → synthesis → GDSII**.

---

## 🛠️ Tools Installation 

### 1. Yosys (Synthesis Tool)
```bash
$ sudo apt-get update
$ git clone https://github.com/YosysHQ/yosys.git
$ cd yosys
$ sudo apt install make build-essential clang bison flex \
    libreadline-dev gawk tcl-dev libffi-dev git \
    graphviz xdot pkg-config python3 libboost-system-dev \
    libboost-python-dev libboost-filesystem-dev zlib1g-dev
$ make config-gcc
$ make
$ sudo make install
````

### 2. Icarus Verilog (Simulation Tool)

```bash
$ sudo apt-get update
$ sudo apt-get install iverilog
```

### 3. GTKWave (Waveform Viewer)

```bash
$ sudo apt-get update
$ sudo apt install gtkwave
```

## 📌 Author

**Hirdesh Pamnani**
4th Year, Electronics & Communication Engineering
JSS Academy of Technical Education, Noida
