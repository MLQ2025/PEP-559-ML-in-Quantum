
# Hamiltonian Matrix Representation for Two-Qubit Transmon System

In this assignment, you'll explore the structure of the Hamiltonian used in reinforcement learning optimization of superconducting quantum circuits, as seen in the paper:

We will walk through how to construct the Hamiltonian matrix for a system of **two transmon qubits**, including:
- The nonlinear (anharmonic) energy levels
- The driving term due to external microwaves
- The coupling term between the two qubits

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
- $|2, 0\rangle$, $|0, 2\rangle$, etc.: higher excitation (leakage states)

We will construct the matrix representation of the Hamiltonian in a truncated Hilbert space with:
- $n_1, n_2 \in \{0, 1, 2\}$ → total of 9 basis states

---

## 2. Operators

For each transmon, define the annihilation and creation operators:

$$
\hat{a} |n\rangle = \sqrt{n} |n-1\rangle \\
\hat{a}^\dagger |n\rangle = \sqrt{n+1} |n+1\rangle
$$

Let:
- $\hat{a}_1$, $\hat{a}_1^\dagger$: operators for qubit 1
- $\hat{a}_2$, $\hat{a}_2^\dagger$: operators for qubit 2
- $\hat{n}_1 = \hat{a}_1^\dagger \hat{a}_1$, $\hat{n}_2 = \hat{a}_2^\dagger \hat{a}_2$: number operators

---

## 3. Hamiltonian (based on Eq. 1 from the paper)

The two-qubit Hamiltonian is:

$$
\hat{H} = \sum_{i=1}^2 \left[ \omega_i \hat{n}_i - \frac{\eta_i}{2} \hat{n}_i (\hat{n}_i - 1) + f_i(t)(\hat{a}_i + \hat{a}_i^\dagger) \right] + J(\hat{a}_1^\dagger \hat{a}_2 + \hat{a}_1 \hat{a}_2^\dagger)
$$

Where:
- $\omega_i$: frequency of qubit $i$
- $\eta_i$: anharmonicity of qubit $i$
- $f_i(t)$: drive amplitude
- $J$: coupling strength between the two qubits

---

## 4. Tasks

### Task 1: Define the basis

Write out all 9 basis states in lexicographic order:

$$
|0,0\rangle, |0,1\rangle, |0,2\rangle, |1,0\rangle, |1,1\rangle, |1,2\rangle, |2,0\rangle, |2,1\rangle, |2,2\rangle
$$

---

### Task 2: Apply operators

Demonstrate how the operators act on example basis states:

$$
\hat{a}_1 |1,0\rangle = \sqrt{1} |0,0\rangle \\
\hat{a}_2^\dagger |1,0\rangle = \sqrt{1} |1,1\rangle \\
\hat{n}_1 |2,1\rangle = 2 |2,1\rangle
$$

---

### Task 3: Compute matrix elements

Use the Hamiltonian and operator rules to compute matrix elements. Example:

$$
\langle 1,0| \hat{H} |0,0\rangle = f_1(t) \cdot \sqrt{1} \\
\langle 1,1| \hat{H} |0,2\rangle = J \cdot \sqrt{1 \cdot 2}
$$

Build the full $9 \times 9$ Hamiltonian matrix including:
- Diagonal terms from the number and anharmonicity operators
- Off-diagonal terms from drive and coupling

---

### Task 4 (Bonus): Identify leakage

- Highlight the computational subspace:

$$
|0,0\rangle, |1,0\rangle, |0,1\rangle, |1,1\rangle
$$

- Identify matrix elements that cause transitions from this subspace to higher excitations ($n_1$ or $n_2$ equal to 2).
- Discuss how this leakage arises from drive or coupling terms.

---

## Deliverables

Submit a PDF or Jupyter Notebook that includes:
- Full basis state list
- Examples of operator actions
- Matrix elements and how they are calculated
- Brief discussion of leakage

---

## Tip

You may use Python (e.g., with NumPy or SymPy) to automate matrix construction, or compute by hand for selected elements.

**Due Date:** _Insert here_  
**Points:** _Insert here_

---
