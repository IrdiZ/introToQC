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

## Exercise 3: Applying (H ⊗ I)CNOT to a Two-Qubit State

**Problem:**
Which quantum state do we get if we apply (H ⊗ I)CNOT to √(1/3)|00⟩ + √(2/3)|11⟩?

Here I is the 1-qubit identity operation, H is the one-qubit Hadamard, and CNOT is the 2-qubit controlled-not operation with the first (=leftmost) qubit being the control.

---

### Key Concepts

**Operator order:** In (H ⊗ I)CNOT|ψ⟩, apply operators **right-to-left**:
1. CNOT first (closest to state)
2. H ⊗ I second

**Tensor product of operators:** (A ⊗ B)|ab⟩ = (A|a⟩) ⊗ (B|b⟩)
- First operator acts on first qubit
- Second operator acts on second qubit

**Identity operator:** I|x⟩ = |x⟩ (does nothing)

---

### Solution

**Step 1: Initial state**

$$|\psi_0\rangle = \sqrt{\frac{1}{3}}|00\rangle + \sqrt{\frac{2}{3}}|11\rangle$$

---

**Step 2: Apply CNOT**

CNOT rule: flip 2nd qubit if 1st qubit is |1⟩

| Input | Control (q1) | Target flips? | Output |
|-------|--------------|---------------|--------|
| \|00⟩ | 0 | No | \|00⟩ |
| \|11⟩ | 1 | Yes (1→0) | \|10⟩ |

State after CNOT:
$$|\psi_1\rangle = \sqrt{\frac{1}{3}}|00\rangle + \sqrt{\frac{2}{3}}|10\rangle$$

---

**Step 3: Apply H ⊗ I**

H acts on qubit 1, I (identity) acts on qubit 2.

**For |00⟩:** (first qubit is |0⟩)
$$(H \otimes I)|00\rangle = (H|0\rangle) \otimes |0\rangle = \frac{|0\rangle + |1\rangle}{\sqrt{2}} \otimes |0\rangle = \frac{|00\rangle + |10\rangle}{\sqrt{2}}$$

**For |10⟩:** (first qubit is |1⟩)
$$(H \otimes I)|10\rangle = (H|1\rangle) \otimes |0\rangle = \frac{|0\rangle - |1\rangle}{\sqrt{2}} \otimes |0\rangle = \frac{|00\rangle - |10\rangle}{\sqrt{2}}$$

---

**Step 4: Combine with coefficients (linearity)**

$$|\psi_2\rangle = \sqrt{\frac{1}{3}} \cdot \frac{|00\rangle + |10\rangle}{\sqrt{2}} + \sqrt{\frac{2}{3}} \cdot \frac{|00\rangle - |10\rangle}{\sqrt{2}}$$

---

**Step 5: Expand**

$$= \frac{1}{\sqrt{6}}|00\rangle + \frac{1}{\sqrt{6}}|10\rangle + \frac{\sqrt{2}}{\sqrt{6}}|00\rangle - \frac{\sqrt{2}}{\sqrt{6}}|10\rangle$$

(Note: √(1/3) · 1/√2 = 1/√6 and √(2/3) · 1/√2 = √2/√6)

---

**Step 6: Collect like terms**

|00⟩ coefficient: 1/√6 + √2/√6 = (1 + √2)/√6

|10⟩ coefficient: 1/√6 − √2/√6 = (1 − √2)/√6

---

### Final Answer (Part a)

$$\boxed{\frac{1+\sqrt{2}}{\sqrt{6}}|00\rangle + \frac{1-\sqrt{2}}{\sqrt{6}}|10\rangle}$$

---

### Part b: Measurement Probability

**Problem:** What is the probability of seeing |11⟩ if we measure the resulting state in the computational basis?

**Method:** P(outcome) = |coefficient|²

**Step 1:** Identify the coefficient of |11⟩ in our final state

Final state: $\frac{1+\sqrt{2}}{\sqrt{6}}|00\rangle + \frac{1-\sqrt{2}}{\sqrt{6}}|10\rangle$

Basis states present:
- |00⟩ ✓ (coefficient = (1+√2)/√6)
- |10⟩ ✓ (coefficient = (1-√2)/√6)
- |01⟩ ✗ (not present)
- |11⟩ ✗ (not present)

**Step 2:** Coefficient of |11⟩ = 0

**Step 3:** Square it

$$P(|11\rangle) = |0|^2 = 0$$

**Answer:** P(|11⟩) = 0

---

### Bonus: Other Measurement Probabilities

$$P(|00\rangle) = \left|\frac{1+\sqrt{2}}{\sqrt{6}}\right|^2 = \frac{(1+\sqrt{2})^2}{6} = \frac{1 + 2\sqrt{2} + 2}{6} = \frac{3 + 2\sqrt{2}}{6}$$

$$P(|10\rangle) = \left|\frac{1-\sqrt{2}}{\sqrt{6}}\right|^2 = \frac{(1-\sqrt{2})^2}{6} = \frac{1 - 2\sqrt{2} + 2}{6} = \frac{3 - 2\sqrt{2}}{6}$$

**Verification:** P(|00⟩) + P(|10⟩) = (3+2√2)/6 + (3-2√2)/6 = 6/6 = 1 ✓

---

### Exam Takeaways

> **Operator order:** (A)(B)|ψ⟩ means apply B first, then A (right-to-left)

> **Tensor product shortcut:** |x⟩ ⊗ |0⟩ = |x0⟩ (just append the second qubit)

> **Linearity:** U(α|ψ⟩ + β|φ⟩) = αU|ψ⟩ + βU|φ⟩ — coefficients stay, only kets transform

---

## Key Concept: Tensor Product Notation

### The Rule

For tensor product of operators acting on a two-qubit state:

$$(A \otimes B)|cd\rangle = (A|c\rangle) \otimes (B|d\rangle)$$

- First operator (A) acts on first qubit (c)
- Second operator (B) acts on second qubit (d)

---

### Shorthand Notation

The ⊗ symbol is often hidden in compact notation:

| Full notation | Shorthand |
|---------------|-----------|
| \|0⟩ ⊗ \|0⟩ | \|00⟩ |
| \|1⟩ ⊗ \|0⟩ | \|10⟩ |
| \|0⟩ ⊗ \|1⟩ | \|01⟩ |
| \|1⟩ ⊗ \|1⟩ | \|11⟩ |
| \|a⟩ ⊗ \|b⟩ | \|ab⟩ |

---

### Example: Distributing Tensor Product

When you have a superposition tensored with a single state:

$$\frac{|0\rangle + |1\rangle}{\sqrt{2}} \otimes |0\rangle$$

Distribute the ⊗ over the sum:

$$= \frac{|0\rangle \otimes |0\rangle}{\sqrt{2}} + \frac{|1\rangle \otimes |0\rangle}{\sqrt{2}}$$

Then use shorthand:

$$= \frac{|00\rangle}{\sqrt{2}} + \frac{|10\rangle}{\sqrt{2}} = \frac{|00\rangle + |10\rangle}{\sqrt{2}}$$

---

### Exam Takeaway

> **Tensor product distributes:** (|a⟩ + |b⟩) ⊗ |c⟩ = |a⟩⊗|c⟩ + |b⟩⊗|c⟩ = |ac⟩ + |bc⟩

---

### Worked Example: Applying to H ⊗ I

**Goal:** Compute (H ⊗ I)|00⟩

**Step 1:** Split into two qubits
$$|00\rangle = |0\rangle \otimes |0\rangle$$

**Step 2:** Apply operators to their qubits
$$(H \otimes I)|00\rangle = (H|0\rangle) \otimes (I|0\rangle)$$

**Step 3:** Compute each part
- H|0⟩ = (|0⟩ + |1⟩)/√2
- I|0⟩ = |0⟩

**Step 4:** Tensor the results
$$= \frac{|0\rangle + |1\rangle}{\sqrt{2}} \otimes |0\rangle$$

**Step 5:** Distribute (append |0⟩ to each term on the left)
$$= \frac{|0\rangle \otimes |0\rangle + |1\rangle \otimes |0\rangle}{\sqrt{2}}$$

**Step 6:** Use shorthand
$$= \frac{|00\rangle + |10\rangle}{\sqrt{2}}$$

---

### Another Example: (H ⊗ I)|10⟩

**Step 1:** Split
$$|10\rangle = |1\rangle \otimes |0\rangle$$

**Step 2:** Apply operators
$$(H \otimes I)|10\rangle = (H|1\rangle) \otimes (I|0\rangle)$$

**Step 3:** Compute each part
- H|1⟩ = (|0⟩ − |1⟩)/√2
- I|0⟩ = |0⟩

**Step 4:** Tensor
$$= \frac{|0\rangle - |1\rangle}{\sqrt{2}} \otimes |0\rangle$$

**Step 5:** Distribute (append |0⟩ to each term)
$$= \frac{|0\rangle \otimes |0\rangle - |1\rangle \otimes |0\rangle}{\sqrt{2}}$$

**Step 6:** Shorthand
$$= \frac{|00\rangle - |10\rangle}{\sqrt{2}}$$

---

### Quick Reference: H ⊗ I Results

| Input | Output |
|-------|--------|
| (H ⊗ I)\|00⟩ | (\|00⟩ + \|10⟩)/√2 |
| (H ⊗ I)\|01⟩ | (\|01⟩ + \|11⟩)/√2 |
| (H ⊗ I)\|10⟩ | (\|00⟩ − \|10⟩)/√2 |
| (H ⊗ I)\|11⟩ | (\|01⟩ − \|11⟩)/√2 |

**Pattern:** H changes the first qubit, second qubit stays the same.

---
