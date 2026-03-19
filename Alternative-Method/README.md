# Method of Alternatives (Uniform Search)

This implementation demonstrates the **Uniform Search Method** for finding the minimum of a unimodal function.

---

## Theoretical Breakdown

The method divides the interval \([a, b]\) into equal segments and evaluates the function at each point.

- **Objective:** Find the minimum of \( f(x) \)
- **Grid Construction:** Divide interval into \( n \) parts
- **Step size:**
  \[
  h = \frac{b - a}{n}
  \]
- **Points:**
  \[
  x_k = a + k \cdot h
  \]
- **Selection:**
  \[
  f(x^*) = \min f(x_k)
  \]

- **Error:**
  \[
  \varepsilon = \frac{b - a}{n}
  \]

---

## Numerical Example

- **Function:**  
  \( f(x) = \frac{1}{4}x^4 + x^2 - 8x + 12 \)

- **Interval:** \([0, 2]\)  
- **Precision:** \( \varepsilon = 0.5 \)  
- **Segments:** \( n = 4 \)

| xᵢ | f(xᵢ) |
|----|------|
| 0.0 | 12.0000 |
| 0.5 | 8.2656 |
| 1.0 | 5.2500 |
| 1.5 | **3.5156** |
| 2.0 | 4.0000 |

**Result:** The approximate minimum is at **x = 1.5**

---

## Visualization

![Plot](optimization_plot.png)
