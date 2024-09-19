# FAST : Rapid Prototyping Framework for Cybersecurity Applications on Heterogeneous Computing

Welcome to the repository for the Rapid Prototyping Framework for Cybersecurity Applications using FPGAs. This project focuses on providing tools, templates, and workflows to accelerate the development of secure applications in FPGA-based heterogeneous computing environments. Fast Framework is designed for developing cybersecurity application accelerators using FPGA-based heterogeneous computing systems. This framework provides an easy-to-use platform for building and testing secure systems that integrate hardware and software components.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Getting Started](#getting-started)
- [Installation](#installation)
- [Framework Structure](#framework-structure)
- [Usage](#usage)
- [Supported Platforms](#supported-platforms)
- [Contributing](#contributing)
- [License](#license)
- [References](#references)

## Overview

This framework aims to accelerate the development of cybersecurity applications on heterogeneous computing platforms with FPGA acceleration. The focus is on resource-constrained environments, such as IoT devices, and systems requiring secure cryptographic operations, memory protection, and real-time security defenses.

## Features

- **Pre-built cryptographic IP cores** for common cryptographic algorithms (AES, RSA, SHA).
- **FPGA-CPU** hybrid design templates.
- **Rapid prototyping tools to** accelerate secure design iteration.
- **RISC-V** and **Physical Memory Protection (PMP)** support for secure execution.
- **Modular structure** for easy customization and extension.
- Built-in unit testing and simulation environments for threat modeling and security validation.


## Getting Started

### Prerequisites

Ensure you have the following tools and libraries installed:

- Python 3.7+
- Vivado Design Suite (for FPGA synthesis and simulation)
- Xilinx PYNQ libraries (for PYNQ boards)
- RISC-V toolchain (for PMP support)
- CMake and GCC toolchain (for CPU modules)

### Platforms Supported:

- TUL PYNQ-Z2
- Zynq UltraScale+
- Ultra-96 v1 and Ultra96 v2
- Alveo U200

## Installation

To set up the framework, follow these steps:

### Clone the repository:

```bash
git clone https://github.com/risehendar/Fast/Fast.git
```

### Navigate into the project directory:
```bash
cd Fast
```

### Install the required Python packages:
```bash
pip install -r requirements.txt
```

### Set up the FPGA build environment (for Xilinx boards):
```bash
source /opt/Xilinx/Vivado/2022.1/settings64.sh
```

## Framework Structure
```bash
.
├── docs/                # Documentation and guides
├── src/                 # Source code for applications
│   ├── hw/              # FPGA hardware components
│   ├── sw/              # Software components
├── tests/               # Unit tests for validation
├── ip_cores/            # Cryptographic IP cores (AES, RSA, SHA)
├── scripts/             # Automation scripts
├── tools/               # Tools for benchmarking and prototyping
└── examples/            # Example projects and demos

```

## Usage
Example Workflow

**Step 1: Build the FPGA design**

Navigate to the `examples/ directory` and select a `cryptographic` example (e.g., AES encryption).

Build the FPGA bitstream:
```bash
vivado -mode batch -source scripts/build_fpga.tcl
```
**Step 2: Deploy the bitstream to FPGA**

Upload the generated bitstream to the board:
```bash
pynq_upload bitstream.bit
```

**Step 3: Run the software component**

For example, to run a secure memory management demo using PMP:
```bash
make && make upload
```
**Step 4: Validate the design with tests**

Run tests to validate the cryptographic functions:
```bash
pytest tests/test_aes.py
```


### Hybrid FPGA-CPU Workflow
This example shows how to integrate CPU and FPGA components for offloading cryptographic computations:
```bash
// CPU-FPGA hybrid code snippet
initialize_fpga();
load_encryption_key(fpga);
encrypt_data(fpga, plaintext, ciphertext);
```

## Supported Platforms
The following platforms have been tested:
   - TUL PYNQ-Z2 (RISC-V PMP protection)
   - Zynq UltraScale+
   - Ultra-96 v1 and Ultra96 v2
   - Alveo U200


## Contributing
We welcome contributions from the community! Please review our Contributing Guide for more details on how to get started. Feel free to open issues or submit pull requests.

## License
This project is licensed under **the MIT License** - see the LICENSE file for details.

## Contact
Hendarmawan ([Email](hendar.rise@gmail.com)).


## TO ADD
- Makefile: HLS IP, SYNTHESIS, VALIDATION, SHELL, Upload and program FPGA
- HW Specs
- config files
- ipynb Jupyter Notebook + Python
- TCL auto build apps
- Fast toolkits
- Auto compiler for re
- Bitstream, hwh, tcl for PYNQ
- HLS exploits: decoder, encoder, exploits, DMA-Memory interconnect, streaming data FIFO
- Example
- Tutorial

## Tutorial
- Copy `requirements.txt` from this repo onto the Pynq board, for example using SCP:

    ```scp requirements.txt xilinx@192.168.2.99:/home/xilinx```

    Installing the Bnn-Pynq requires the BOARD env variable to be set. SSH into the Pynq board and run as sudo:

    ```shell
    echo export BOARD=Pynq-Z2 >> /root/.bashrc && source /root/.bashrc
    sudo pip3 install -r requirements.txt
    ```

- Note that if you are connecting more than 1 Pynq boards, each of them will have to be assigned a unique IP address. This can be done by modifying the default value `192.168.2.99` to something else (`192.168.2.100` etc.) in `/etc/network/interfaces.d/eth0`
