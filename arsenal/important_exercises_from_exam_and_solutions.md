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
