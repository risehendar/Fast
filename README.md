# Rapid Prototyping Framework for Cybersecurity Applications on Heterogeneous Computing with FPGA

Welcome to the Rapid Prototyping Framework for developing cybersecurity applications using FPGA-based heterogeneous computing systems. This framework provides an easy-to-use platform for building and testing secure systems that integrate hardware and software components.

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
- Pre-built cryptographic IP cores (AES, RSA, SHA).
- FPGA-CPU hybrid design templates.
- **RISC-V** and **Physical Memory Protection (PMP)** support for secure execution.
- Modular structure for easy customization and extension.
- Built-in unit testing and simulation environments.
- Support for **Trusted Execution Environments (TEE)**.

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
- Intel Cyclone V
- Alveo U200

## Installation

To set up the framework, follow these steps:

### Clone the repository:

```bash
git clone https://github.com/yourusername/yourrepository.git
