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

import numpy as np
import matplotlib.pyplot as plt

# Function
def f(x):
    return 0.25 * x**4 + x**2 - 8*x + 12

# Continuous curve
x = np.linspace(0, 2, 200)
y = f(x)

# Uniform search points
x_points = np.array([0, 0.5, 1.0, 1.5, 2.0])
y_points = f(x_points)

# Plot
plt.figure(figsize=(8, 5))

# Function curve
plt.plot(x, y, label="f(x)")

# Search nodes
plt.scatter(x_points, y_points, color='red', label="Search Nodes (x_k)")

# Labels on points
for i in range(len(x_points)):
    plt.text(x_points[i], y_points[i] + 0.3, f"{y_points[i]:.4f}", ha='center')

# Title and labels
plt.title("Method of Alternatives: Uniform Search Grid")
plt.xlabel("x")
plt.ylabel("f(x)")

# Grid and legend
plt.grid()
plt.legend()

# Save image (IMPORTANT)
plt.savefig("optimization_plot.png")

# Show plot
plt.show()
## Visualization


![Plot](optimization_plot.png)
