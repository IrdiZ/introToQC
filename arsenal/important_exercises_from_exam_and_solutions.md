# Important Exercises from Exam & Solutions

---

## Exercise 1: State Distinguishability

**Problem:**
Is there an experiment (measurement) where you can distinguish with absolute certainty whether the qubit is in state (α) or (β)?

- State (α): |0⟩
- State (β): (3/5)|0⟩ + (4/5)|1⟩

---

### Key Concept

**Distinguishability criterion:** Two quantum states can be distinguished with absolute certainty **if and only if** they are orthogonal.

$$\text{Perfect distinguishability} \iff \langle\psi|\phi\rangle = 0$$

---

### Solution

**Step 1:** Compute the inner product ⟨α|β⟩

$$\langle 0| \left(\frac{3}{5}|0\rangle + \frac{4}{5}|1\rangle\right) = \frac{3}{5}\langle 0|0\rangle + \frac{4}{5}\langle 0|1\rangle$$

$$= \frac{3}{5}(1) + \frac{4}{5}(0) = \frac{3}{5}$$

**Step 2:** Check if orthogonal

$$\langle\alpha|\beta\rangle = \frac{3}{5} \neq 0$$

**Conclusion:** The states are **NOT orthogonal**, therefore they **CANNOT** be distinguished with absolute certainty.

---

### Intuition: Where's the Ambiguity?

Measure in computational basis {|0⟩, |1⟩}:

| State | Possible outcomes |
|-------|-------------------|
| \|α⟩ = \|0⟩ | "0" only (100%) |
| \|β⟩ = (3/5)\|0⟩ + (4/5)\|1⟩ | "0" (prob 9/25) or "1" (prob 16/25) |

- If you measure **"1"** → definitely |β⟩
- If you measure **"0"** → could be |α⟩ OR |β⟩ → **ambiguous!**

The overlapping outcome "0" is why perfect distinguishability fails. The inner product 3/5 ≠ 0 quantifies this overlap.

---

### Exam Takeaway

> **States distinguishable with certainty ⟺ ⟨ψ|φ⟩ = 0 ⟺ orthogonal ⟺ no overlapping measurement outcomes**

---

## Exercise 1b: Measurement in a Different Basis

**Problem:**
For state |β⟩ = (3/5)|0⟩ + (4/5)|1⟩, what are the probabilities of measuring |+⟩ or |−⟩ in the {|+⟩, |−⟩} basis?

---

### Key Concept

**Born rule:** Probability of outcome |φ⟩ when measuring state |ψ⟩ is |⟨φ|ψ⟩|².

---

### Solution

**Step 1:** Compute amplitude for |+⟩

$$\langle +|\beta\rangle = \frac{3}{5}\langle +|0\rangle + \frac{4}{5}\langle +|1\rangle$$

Using ⟨+| = [1/√2, 1/√2]:
- ⟨+|0⟩ = 1/√2
- ⟨+|1⟩ = 1/√2

$$\langle +|\beta\rangle = \frac{3}{5} \cdot \frac{1}{\sqrt{2}} + \frac{4}{5} \cdot \frac{1}{\sqrt{2}} = \frac{7}{5\sqrt{2}}$$

**Step 2:** Square for probability

$$P(|+\rangle) = \left|\frac{7}{5\sqrt{2}}\right|^2 = \frac{49}{50}$$

**Step 3:** Probability for |−⟩

Either compute directly (using ⟨−| = [1/√2, −1/√2]):

$$\langle -|\beta\rangle = \frac{3}{5} \cdot \frac{1}{\sqrt{2}} + \frac{4}{5} \cdot \frac{-1}{\sqrt{2}} = \frac{-1}{5\sqrt{2}}$$

$$P(|-\rangle) = \left|\frac{-1}{5\sqrt{2}}\right|^2 = \frac{1}{50}$$

Or use: P(|−⟩) = 1 − P(|+⟩) = 1 − 49/50 = **1/50**

---

### Quick Reference: Basis Vectors

| Basis | Vectors |
|-------|---------|
| Computational | \|0⟩ = [1, 0]ᵀ, \|1⟩ = [0, 1]ᵀ |
| Hadamard | \|+⟩ = [1/√2, 1/√2]ᵀ, \|−⟩ = [1/√2, −1/√2]ᵀ |

| Inner products | Value |
|----------------|-------|
| ⟨+\|0⟩ = ⟨+\|1⟩ | 1/√2 |
| ⟨−\|0⟩ | 1/√2 |
| ⟨−\|1⟩ | −1/√2 |

---

## Exercise 2: No-Cloning Theorem

**Problem:**
Explain why classical copying of a quantum state is not possible (no-cloning theorem).

---

### Key Concept

**No-Cloning Theorem:** There is no unitary operation U that can copy an arbitrary unknown quantum state.

---

### Solution (Proof by Contradiction)

**Setup:** Suppose a universal cloning unitary U exists. It must satisfy:

$$U|\psi\rangle|0\rangle = |\psi\rangle|\psi\rangle \quad \text{for any state } |\psi\rangle$$

**Step 1:** Apply to two arbitrary states |ψ⟩ and |φ⟩

$$U|\psi\rangle|0\rangle = |\psi\rangle|\psi\rangle$$
$$U|\phi\rangle|0\rangle = |\phi\rangle|\phi\rangle$$

**Step 2:** Take the inner product of both equations

**Left side:**
$$\langle\psi|\langle 0|U^\dagger U|\phi\rangle|0\rangle = \langle\psi|\phi\rangle\langle 0|0\rangle = \langle\psi|\phi\rangle$$

(using U†U = I for unitary operators)

**Right side:**
$$\langle\psi|\langle\psi|\phi\rangle|\phi\rangle = \langle\psi|\phi\rangle \cdot \langle\psi|\phi\rangle = \langle\psi|\phi\rangle^2$$

**Step 3:** Set equal and solve

$$\langle\psi|\phi\rangle = \langle\psi|\phi\rangle^2$$

Let x = ⟨ψ|φ⟩. Then x = x², which has only two solutions:
- x = 0 (orthogonal states)
- x = 1 (identical states)

**Step 4:** Contradiction

A universal cloner must work for ANY pair of states, including non-orthogonal states where 0 < |⟨ψ|φ⟩| < 1. But x = x² forbids this.

**∴ No universal quantum cloner exists. ∎**

---

### The CNOT Trap

**Common mistake:** "CNOT can copy quantum states"

CNOT does copy basis states:
- CNOT|0⟩|0⟩ = |0⟩|0⟩ ✓
- CNOT|1⟩|0⟩ = |1⟩|1⟩ ✓

**But for superpositions:**

$$\text{CNOT}(\alpha|0\rangle + \beta|1\rangle)|0\rangle = \alpha|00\rangle + \beta|11\rangle$$

This is an **entangled state**, NOT two independent copies:

$$\alpha|00\rangle + \beta|11\rangle \neq (\alpha|0\rangle + \beta|1\rangle) \otimes (\alpha|0\rangle + \beta|1\rangle)$$

The right side would be: α²|00⟩ + αβ|01⟩ + αβ|10⟩ + β²|11⟩

---

### Classical vs Quantum Copying

| Classical bits | Quantum bits |
|---------------|--------------|
| Can copy freely: 0 → 00, 1 → 11 | Cannot copy unknown states |
| Reading doesn't disturb state | Measurement collapses state |
| CNOT copies basis states | CNOT creates entanglement for superpositions |

---

### Exam Takeaway

> **No-cloning proof:** Inner product argument gives x = x², only satisfied by x = 0 or x = 1. Non-orthogonal states (0 < |x| < 1) cannot be cloned.

---
