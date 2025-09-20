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

---

### 2. Iverilog  
**Purpose:** Compiles and simulates Verilog designs.

```bash
sudo apt update
sudo apt install iverilog
```

---

### 3. GTKWave  
**Purpose:** Visualize simulation waveforms.

```bash
sudo apt update
sudo apt install gtkwave
```

---

### 4. Ngspice  
**Purpose:** Analog and mixed-signal circuit simulation.

```bash
sudo apt update
sudo apt install ngspice
```

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

# Install system-wide
sudo make install


