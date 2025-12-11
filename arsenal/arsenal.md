# Exam Arsenal

## 1. Inner Product Extracts Coefficients

For any state |ψ⟩ = α|0⟩ + β|1⟩:

```
⟨0|ψ⟩ = α   (coefficient of |0⟩)
⟨1|ψ⟩ = β   (coefficient of |1⟩)
```

**Why it works:**
- ⟨0|0⟩ = 1 (same state)
- ⟨0|1⟩ = 0 (orthogonal)

So: ⟨0|ψ⟩ = α⟨0|0⟩ + β⟨0|1⟩ = α(1) + β(0) = α

**Works for any orthonormal basis:**
- Computational basis: ⟨0|ψ⟩, ⟨1|ψ⟩
- Hadamard basis: ⟨+|ψ⟩, ⟨−|ψ⟩

**Why it matters:**
|⟨0|ψ⟩|² = |α|² = probability of measuring |0⟩

---

## 2. Orthogonality = Zero Inner Product

```
⟨a|b⟩ = 0  means |a⟩ and |b⟩ are orthogonal
```

**What orthogonal means:**
- No overlap between states
- Perfectly distinguishable by measurement
- Zero probability of measuring |a⟩ when in state |b⟩

**Key orthogonal pairs:**
- ⟨0|1⟩ = 0 (computational basis)
- ⟨+|−⟩ = 0 (Hadamard basis)

**Valid basis requirement:**
A set of states forms an orthonormal basis if:
1. All pairs are orthogonal: ⟨a|b⟩ = 0 for a ≠ b
2. All states are normalized: ⟨a|a⟩ = 1

---

## 3. Probability in Any Basis

To find probability of outcome |a⟩ when in state |ψ⟩:

```
P(|a⟩) = |⟨a|ψ⟩|²
```

**Method 1: Matrix multiplication**
```
⟨a|ψ⟩ = [row vector of ⟨a|] · [column vector of |ψ⟩]
```

**Method 2: Linearity**
```
If |ψ⟩ = α|0⟩ + β|1⟩, then:
⟨a|ψ⟩ = α⟨a|0⟩ + β⟨a|1⟩
```

**Key inner products to memorize:**
| | \|0⟩ | \|1⟩ | \|+⟩ | \|−⟩ |
|---|---|---|---|---|
| ⟨0\| | 1 | 0 | 1/√2 | 1/√2 |
| ⟨1\| | 0 | 1 | 1/√2 | −1/√2 |
| ⟨+\| | 1/√2 | 1/√2 | 1 | 0 |
| ⟨−\| | 1/√2 | −1/√2 | 0 | 1 |

---

## 4. Complex Amplitudes

When amplitude is complex, |z|² = z* · z

**Example:**
```
|ψ⟩ = (1/√2)|0⟩ + (i/√2)|1⟩

⟨1|ψ⟩ = i/√2

P(|1⟩) = |i/√2|² = (−i/√2)(i/√2) = −i²/2 = 1/2
```

**Swapping order gives conjugate:**
```
⟨a|b⟩ = ⟨b|a⟩*

If ⟨1|ψ⟩ = i/√2, then ⟨ψ|1⟩ = −i/√2
```

For probabilities: |⟨a|b⟩|² = |⟨b|a⟩|² (order doesn't matter)

---

## 5. Normalization Fixes Magnitude, Not Phase

If you know one amplitude and normalization, you can find the **magnitude** of the other, but not its **phase**.

```
|α|² + |β|² = 1

Given: α = 1/√3
Then:  |β|² = 1 - 1/3 = 2/3
       |β| = √(2/3)
```

But β can be **any** of:
```
β = √(2/3)        (real positive)
β = −√(2/3)       (real negative)
β = i√(2/3)       (imaginary)
β = e^(iθ)√(2/3)  (any phase θ)
```

**Why?** Normalization constrains |β|², not β itself. The phase is free.

**Works for any basis:** Knowing P(|+⟩) tells you P(|−⟩) = 1 − P(|+⟩), but not the phases of the coefficients.
