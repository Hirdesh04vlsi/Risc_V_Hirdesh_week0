
# RISC-V Hirdesh Week 0 🚀

This repository is a part of the **VSD RISC-V "Silicon to Tapeout" program** by **VSD** and **Kunal Ghosh** sir.  
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
<img width="916" height="546" alt="Screenshot 2025-09-19 005757" src="https://github.com/user-attachments/assets/fa24f645-004c-4796-bd84-d1967bda90a6" />

4. **Final Verification (O4)**  
   - At the end, outputs O1 = O2 = O3 = O4 must be consistent.  
   - This validates that chip implementation matches initial specifications.  
<img width="839" height="485" alt="Screenshot 2025-09-19 005848" src="https://github.com/user-attachments/assets/34a08d24-d4ef-4ff6-9043-a7a2f66ccf5b" />

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
<img width="1060" height="609" alt="Screenshot 2025-09-19 013924" src="https://github.com/user-attachments/assets/78556417-09ae-48f5-93dd-151567ac52d2" />

### 2. Icarus Verilog (Simulation Tool)

```bash
$ sudo apt-get update
$ sudo apt-get install iverilog
```
<img width="1104" height="360" alt="Screenshot 2025-09-19 013939" src="https://github.com/user-attachments/assets/041af9af-9660-42f9-a8ef-b6a68c47e247" />

### 3. GTKWave (Waveform Viewer)

```bash
$ sudo apt-get update
$ sudo apt install gtkwave
```
<img width="862" height="124" alt="Screenshot 2025-09-19 014213" src="https://github.com/user-attachments/assets/ca8a6774-0256-4e23-ab9e-c24d90acf6c2" />
<img width="2015" height="1339" alt="image" src="https://github.com/user-attachments/assets/0cefece2-8d49-4c75-aec7-5424621d0134" />

### 4. Ngspice (Circuit Simulation)

```bash
$ wget https://sourceforge.net/projects/ngspice/files/ng-spice-rework/45/ngspice-45.tar.gz
$ tar -zxvf ngspice-45.tar.gz
$ cd ngspice-45
$ mkdir release && cd release
$ ../configure --with-x --with-readline=yes --disable-debug
$ make
$ sudo make install
```
<img width="938" height="384" alt="Screenshot 2025-09-19 041709" src="https://github.com/user-attachments/assets/659434ff-dd83-4756-8fab-5251cdbd5f47" />


### 5. Magic VLSI (Layout Tool)

```bash
$ sudo apt-get install m4 tcsh csh libx11-dev tcl-dev tk-dev \
    libcairo2-dev mesa-common-dev libglu1-mesa-dev libncurses-dev
$ git clone https://github.com/RTimothyEdwards/magic
$ cd magic
$ ./configure
$ make
$ sudo make install
```
<img width="946" height="1079" alt="Screenshot 2025-09-19 041639" src="https://github.com/user-attachments/assets/7f2aceb1-d395-413f-abcb-7cd485551977" />

### 6. OpenLane (RTL to GDSII Flow)

```bash
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt install -y build-essential python3 python3-venv python3-pip make git
$ sudo apt install apt-transport-https ca-certificates curl software-properties-common

$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o \
    /usr/share/keyrings/docker-archive-keyring.gpg

$ echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] \
    https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | \
    sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

$ sudo apt update
$ sudo apt install docker-ce docker-ce-cli containerd.io

$ sudo groupadd docker
$ sudo usermod -aG docker $USER
$ newgrp docker
$ docker run hello-world
```

Install OpenLane:

```bash
$ cd $HOME
$ git clone https://github.com/The-OpenROAD-Project/OpenLane
$ cd OpenLane
$ make
($ make test)
$ docker run --rm \
    -v $(pwd):/openlane \
    -v $PDK_ROOT:$PDK_ROOT \
    -e PDK_ROOT=$PDK_ROOT \
    -u $(id -u):$(id -g) \
    efabless/openlane:latest \
    ./flow.tcl -design spm -tag mytest -overwrite

```
 <img width="949" height="646" alt="image" src="https://github.com/user-attachments/assets/8246f1da-d952-45e7-b207-856fd3ce5dc3" />


## 📌 Author

**Hirdesh Pamnani**
4th Year, Electronics & Communication Engineering
JSS Academy of Technical Education, Noida
mail: hirdeshpamani2@gmail.com




