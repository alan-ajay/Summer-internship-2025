# Summer Internship 2025: Explorations in Quantum Computing

Welcome to my repository for the Summer 2025 internship. This collection of Jupyter notebooks documents my work and research in the field of quantum computing.

## Project Overview
This repository contains two main projects that explore different facets of quantum computation:

* **Variational Quantum Algorithms (VQAs)**: A look into solving combinatorial optimization problems, specifically the Max-Cut problem. The core of this project is the design of "dynamic ansatz" aimed at improving the performance of the Variational Quantum Eigensolver (VQE).
* **Quantum Cryptography**: An implementation of a quantum sealed-bid auction protocol, demonstrating how quantum mechanics can be used for secure, multi-party computation without a trusted third party.

---

## Projects

### 1. Ansatz Engineering for the Variational Quantum Eigensolver (VQE)

**File**: `ansatz_engineering.ipynb`

This project focuses on enhancing the performance of VQAs by engineering a more expressive quantum circuit, or "ansatz."

* **Problem**: The Max-Cut problem, a classic NP-hard optimization challenge.
* **Approach**:
    * **Dynamic Ansatz (`MaxCutDynamicSolver`)**: Instead of a fixed circuit, this solver cyclically alters the entangling gate pattern across optimization iterations. This is designed to allow the algorithm to explore a wider solution space.
    * **Benchmarking**: The dynamic ansatz's performance is rigorously compared against two baselines:
        * A standard, fixed `EfficientSU2` ansatz.
        * A classical brute-force solver that finds the exact optimal solution.
* **Key Findings**:
    The dynamic ansatz consistently outperforms the standard fixed ansatz, achieving solutions closer to the true optimum with greater stability. The results suggest that dynamic circuit structures are a promising direction for improving VQA performance in the NISQ era.

### 2. Quantum Sealed-Bid Auction

**File**: `Quantum Sealed-Bid Auction.ipynb`

This notebook implements the "highest bid finding phase" of a quantum sealed-bid auction protocol, a fascinating application of quantum cryptography.

* **Problem**: How can multiple bidders securely determine the highest bid interval without revealing their individual bid values to each other or a central authority?
* **Approach**:
    * **Phase Encoding**: Each bidder encodes their private bid as a phase on an entangled quantum state.
    * **Distributed Phase Interference**: The protocol uses quantum interference to collectively determine the most significant bit where the bids differ, thereby identifying the highest bid interval.
    * **Security**: The use of entanglement and the principles of quantum mechanics ensure that individual bids remain private throughout the process.

---

## VQA Subdirectory

**Directory**: `VQA/`

This folder contains earlier iterations and foundational work related to the Variational Quantum Eigensolver, including:

* `VQE_tutorial.ipynb`: An introductory notebook exploring the basics of VQE.
* `max-cut_problem1.ipynb` & `max-cut_problem2.ipynb`: Initial explorations into solving the Max-Cut problem with standard VQE approaches.

---

## Key Learnings & Future Work

This internship provided deep insights into both practical algorithm design and theoretical quantum protocols.

**Future Work**:

* **Ansatz Engineering**:
    * Test the dynamic ansatz on larger, more complex graphs.
    * Analyze its performance on real noisy quantum hardware.
    * Explore adaptive ansatz strategies where the circuit structure is modified based on optimizer feedback.
* **Quantum Auction**:
    * Implement the full auction protocol, including winner identification.
    * Analyze the protocol's robustness against various forms of noise and potential attacks.
