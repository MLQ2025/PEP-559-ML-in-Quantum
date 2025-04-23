# Hamiltonian Matrix Representation for Two-Qubit Transmon System

In this assignment, you'll explore the structure of the Hamiltonian used in reinforcement learning optimization of superconducting quantum circuits, as seen in the paper:

We will walk through how to construct the Hamiltonian matrix for a system of **two transmon qubits**, including:
- The **nonlinear (anharmonic) energy levels**
- The **driving term** due to external microwaves
- The **coupling term** between the two qubits

---

## 1. Basis States

We model each transmon as a **nonlinear oscillator** with discrete energy levels.

Let $|n_1, n_2\rangle$ denote a **Fock basis state** where:
- \( n_1 \) = excitation level of **qubit 1**
- \( n_2 \) = excitation level of **qubit 2**

For example:
- \( |0, 0\rangle \): both qubits in ground state
- \( |1, 0\rangle \): qubit 1 excited, qubit 2 in ground state
- \( |0, 1\rangle \): qubit 2 excited
- \( |1, 1\rangle \): both qubits excited
- \( |2, 0\rangle \), \( |0, 2\rangle \), etc.: higher excitation (leakage states)

You will **construct the matrix representation** of the Hamiltonian in a truncated Hilbert space with:
- \( n_1, n_2 \in \{0, 1, 2\} \) → total of **9 basis states**

---

## 2. Operators

For each transmon, define the **annihilation** and **creation** operators:

\[
\hat{a} |n\rangle = \sqrt{n} |n-1\rangle, \quad \hat{a}^\dagger |n\rangle = \sqrt{n+1} |n+1\rangle
\]

Let:
- \( \hat{a}_1, \hat{a}_1^\dagger \): for qubit 1
- \( \hat{a}_2, \hat{a}_2^\dagger \): for qubit 2
- \( \hat{n}_1 = \hat{a}_1^\dagger \hat{a}_1 \), \( \hat{n}_2 = \hat{a}_2^\dagger \hat{a}_2 \)

---

## 3. The Hamiltonian (from Eq. 1 of the paper)

\[
\hat{H} = \sum_{i=1}^2 \left[ \omega_i \hat{n}_i - \frac{\eta_i}{2} \hat{n}_i (\hat{n}_i - 1) + f_i(t) (\hat{a}_i + \hat{a}_i^\dagger) \right] + J (\hat{a}_1^\dagger \hat{a}_2 + \hat{a}_1 \hat{a}_2^\dagger)
\]

Where:
- \( \omega_i \): frequency of qubit \( i \)
- \( \eta_i \): anharmonicity (nonlinearity) of qubit \( i \)
- \( f_i(t) \): drive amplitude for qubit \( i \)
- \( J \): coupling strength

---

## 4. Tasks

### Task 1. Define the basis
Write out all 9 basis states in lexicographic order:  
\( \{ |0,0\rangle, |0,1\rangle, |0,2\rangle, |1,0\rangle, |1,1\rangle, |1,2\rangle, |2,0\rangle, |2,1\rangle, |2,2\rangle \} \)

### Task 2. Apply operators
Demonstrate how each operator acts on a few example states.  
For example:
```text
a_1 |1,0> = sqrt(1) |0,0>
a_2† |1,0> = sqrt(1) |1,1>
n_1 |2,1> = 2 |2,1>
