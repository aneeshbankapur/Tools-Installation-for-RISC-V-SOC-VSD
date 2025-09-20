# Tools-Installation-for-RISC-V-SOC-VSD
# Week 0 – VLSI System Design (VSD) Program Setup

This week focused on preparing the development environment and installing essential open-source tools for synthesis, simulation, and layout design.

---

## System Configuration

| Specification | Details |
|---------------|---------|
| Operating System | Ubuntu 20.04+ |
| RAM | 6 GB |
| Storage | 50 GB |
| vCPUs | 4 |

---

## Installed Tools

| Tool | Purpose |
|------|---------|
| Yosys | RTL synthesis |
| Iverilog | Verilog simulation |
| GTKWave | Waveform viewing |
| Ngspice | Circuit simulation |
| Magic VLSI | Layout design |

---

### 1. Yosys  
**Purpose:** Converts RTL code into gate-level representations.

```bash
git clone https://github.com/YosysHQ/yosys.git
cd yosys
sudo apt install make build-essential clang bison flex \
libreadline-dev gawk tcl-dev libffi-dev git \
graphviz xdot pkg-config python3 libboost-system-dev \
libboost-python-dev libboost-filesystem-dev zlib1g-dev
make
sudo make install
```
## 📷 **Installation Verification**
<p align="center">
  <img src="https://github.com/aneeshbankapur/Tools-Installation-for-RISC-V-SOC-VSD/blob/bea951ec67cb013ef7c51d66a45b9a4f9ec0dcdb/Yosys%20installation.png">
</p>

---

### 2. Iverilog  
**Purpose:** Compiles and simulates Verilog designs.

```bash
sudo apt update
sudo apt install iverilog
```
## 📷 **Installation Verification**
<p align="center">
  <img src="https://github.com/aneeshbankapur/Tools-Installation-for-RISC-V-SOC-VSD/blob/d2533a0b456620b1051294bc31ecf22a87a3cc1f/iverilog%20installation.png">
</p>

---

### 3. GTKWave  
**Purpose:** Visualize simulation waveforms.

```bash
sudo apt update
sudo apt install gtkwave
```
## 📷 **Installation Verification**
<p align="center">
  <img src="https://github.com/aneeshbankapur/Tools-Installation-for-RISC-V-SOC-VSD/blob/d2533a0b456620b1051294bc31ecf22a87a3cc1f/gtkwave%20installation.png">
</p>
---

### 4. Ngspice  
**Purpose:** Analog and mixed-signal circuit simulation.

```bash
sudo apt update
sudo apt install ngspice
```
## 📷 **Installation Verification**
<p align="center">
  <img src="https://github.com/aneeshbankapur/Tools-Installation-for-RISC-V-SOC-VSD/blob/d2533a0b456620b1051294bc31ecf22a87a3cc1f/ngspice%20installation.png">
</p>
---

### 5. Magic VLSI  
**Purpose:** Layout editing and analysis.

```bash
# Install required dependencies
sudo apt-get install m4
sudo apt-get install tcsh
sudo apt-get install csh
sudo apt-get install libx11-dev
sudo apt-get install tcl-dev tk-dev
sudo apt-get install libcairo2-dev
sudo apt-get install mesa-common-dev libglu1-mesa-dev
sudo apt-get install libncurses-dev

# Clone Magic repository
git clone https://github.com/RTimothyEdwards/magic
cd magic

# Configure build
./configure

# Build Magic
make
```
## 📷 **Installation Verification**
<p align="center">
  <img src="https://github.com/aneeshbankapur/Tools-Installation-for-RISC-V-SOC-VSD/blob/d2533a0b456620b1051294bc31ecf22a87a3cc1f/magic%20installation.png">
</p>




