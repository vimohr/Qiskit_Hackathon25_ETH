# Qlueless — Qiskit Hackathon Submission 🧠⚛️

Welcome to the official repository for **Qlueless**, our submission for the Qiskit Quantum Hackathon 2025! 🚀  
This project tackles quantum circuit optimization using two complementary approaches focused on **CNOT parallelization** and **resource pruning**, aiming to improve efficiency on noisy or resource-constrained backends.

---

## 💡 Problem Motivation

Quantum circuits executed on real hardware are subject to noise, limited coherence times, and qubit connectivity constraints. Our goal is to optimize quantum workloads by **parallelizing costly two-qubit gates** and **rerouting of two-qubit gates based on device-specific error rates**, thereby enhancing the functional performance of the original circuit.

---

## 🧪 Our Approaches

We explored two optimization strategies (both in `submission.ipynb`):

### 1. **CNOT binary tree fan-out**
- Summary: This approach targets CNOT ladder structures, which typically exhibit a two-qubit depth scaling of $\mathcal{O}(N)$. By applying our resource pruning method, we reduce the effective depth to approximately $\mathcal{O}(\sqrt{N})$ on 2D hardware topologies, such as IBM’s FakeTorino device. We demonstrate this improvement in the context of GHZ state preparation, showcasing significant depth reduction.
- Outlook:
  - Application to other circuit structures such as VQE.

### 2. **Noise-aware resource pruning**
- Summary: This project implements the noise-aware resource pruning method based on arXiv:2402.08226v2, using Qiskit to create high-fidelity hardware partitions by filtering out noisy components based on user-defined thresholds. The script then benchmarks circuits of increasing size consisting of CNOT ladders on both the full and pruned maps, generating plots that compare final circuit depth and total error to demonstrate the effectiveness of this optimization strategy.
- Outlook: 
  - Automation of the error threshold selection and integration of this pruning logic directly into Qiskit's transpile by creating a custom transpiler Pass.


## 🛠️ Requirements

Install dependencies with:

```bash
pip install -r requirements.txt
