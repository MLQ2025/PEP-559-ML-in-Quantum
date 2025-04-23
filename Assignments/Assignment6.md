# Hamiltonian Matrix Representation for Two-Qubit Transmon System

In this assignment, you'll explore the structure of the Hamiltonian used in reinforcement learning optimization of superconducting quantum circuits, as seen in the paper.

We will walk through how to construct the Hamiltonian matrix for a system of **two transmon qubits**, including:
- The **anharmonic (nonlinear) energy levels**
- The **external drive terms**
- The **coupling interaction** between the qubits

We adopt the notation from Eq. (1) in the paper, written in the rotating wave approximation (RWA):

$$
\hat{H} = \frac{\eta}{2} \sum_{j=1}^2 \hat{n}_j (\hat{n}_j - 1) + g(t) ( \hat{a}_2^\dagger \hat{a}_1 + \hat{a}_1^\dagger \hat{a}_2 ) 
$$

$$
+ \sum_{j=1}^2 \delta_j(t) \hat{n}_j + \sum_{j=1}^2 i f_j(t) ( \hat{a}_j e^{-i \varphi_j(t)} - \hat{a}_j^\dagger e^{i \varphi_j(t)} )
$$



Where:
- $\hat{a}_j, \hat{a}_j^\dagger$: annihilation and creation operators for qubit $j$
- $\hat{n}_j = \hat{a}_j^\dagger \hat{a}_j$: number operator
- $\eta$: anharmonicity
- $g(t)$: time-dependent coupling strength between the qubits
- $\delta_j(t)$: detuning of qubit $j$
- $f_j(t)$: drive amplitude
- $\varphi_j(t)$: drive phase

---

## 1. Basis States

We model each transmon as a nonlinear oscillator with discrete energy levels.

Let $|n_1, n_2\rangle$ denote a Fock basis state where:
- $n_1$ is the excitation level of qubit 1
- $n_2$ is the excitation level of qubit 2

Examples:
- $|0, 0\rangle$: both qubits in ground state
- $|1, 0\rangle$: qubit 1 excited, qubit 2 in ground state
- $|0, 1\rangle$: qubit 2 excited
- $|1, 1\rangle$: both qubits excited
- $|2, 0\rangle$, $|2, 1\rangle$, $|2, 2\rangle$, $|1, 2\rangle$, $|0, 2\rangle$, etc.: higher excitation (leakage states)

We will construct the matrix representation of the Hamiltonian in a truncated Hilbert space with:
- $n_1, n_2 \in \{0, 1, 2\}$ → total of 9 basis states, among which, the lowest four form the so-called **qubit subspace**

---

## 2. Operators

Annihilation and creation operator actions:

$$
\hat{a} |n\rangle = \sqrt{n} |n-1\rangle
$$

$$
\hat{a}^\dagger |n\rangle = \sqrt{n+1} |n+1\rangle
$$

Let:
- $\hat{a}_1$, $\hat{a}_1^\dagger$: operators for qubit 1
- $\hat{a}_2$, $\hat{a}_2^\dagger$: operators for qubit 2
- $\hat{n}_1 = \hat{a}_1^\dagger \hat{a}_1$, $\hat{n}_2 = \hat{a}_2^\dagger \hat{a}_2$: number operators

---

## 3. Tasks

### Task 1: Define the basis

Write out all 9 basis states in lexicographic order:

$$
|0,0\rangle, |0,1\rangle, |0,2\rangle, |1,0\rangle, |1,1\rangle, |1,2\rangle, |2,0\rangle, |2,1\rangle, |2,2\rangle
$$

---

### Task 2: Apply operators

Show how the operators act on a few basis states:

$$
\hat{a}_1 |1,0\rangle = \sqrt{1} |0,0\rangle \\
\hat{a}_2^\dagger |1,0\rangle = \sqrt{1} |1,1\rangle \\
\hat{n}_1 |2,1\rangle = 2 |2,1\rangle
$$

---

### Task 3: Compute matrix elements

Using the full Hamiltonian above, compute matrix elements like:

$$
\langle 1,0| \hat{H}_{\text{RWA}}(t) |0,0\rangle = i f_1(t) e^{-i\varphi_1(t)} \sqrt{1} \\
\langle 1,1| \hat{H}_{\text{RWA}}(t) |0,2\rangle = g(t) \sqrt{1 \cdot 2}
$$

Build the full $9 \times 9$ Hamiltonian matrix, including:
- Diagonal terms from $\hat{n}_j(\hat{n}_j - 1)$ and $\delta_j(t)\hat{n}_j$
- Off-diagonal terms from coupling and drive

---

### Task 4 (Bonus): Identify leakage

- Highlight the computational subspace:

$$
|0,0\rangle, |1,0\rangle, |0,1\rangle, |1,1\rangle
$$

- Identify which terms in the Hamiltonian can cause transitions from the qubit subspace to leakage levels (where $n_1$ or $n_2 = 2$).
- Discuss how the drive or coupling contributes to leakage.

---

## Deliverables

Submit a PDF or Jupyter Notebook that includes:
- Full basis state list
- Examples of operator actions
- Matrix elements with explanation
- Discussion of leakage and its sources

---

## Tip

You may use Python (NumPy or SymPy) to help with operator algebra and matrix generation.

**Due Date:** _Insert here_  
**Points:** _Insert here_

---
