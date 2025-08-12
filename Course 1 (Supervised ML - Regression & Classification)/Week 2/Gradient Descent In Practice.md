# Multiple Features in Linear Regression

## Concept
- In single-feature linear regression:  
  \( f(x) = wx + b \)  
- In multiple-feature linear regression:  
  \( f(x) = w_1x_1 + w_2x_2 + \dots + w_nx_n + b \)  
- **Vectorized form**:  
  \( f(\mathbf{x}) = \mathbf{w} \cdot \mathbf{x} + b \)  
  where:
  - \( \mathbf{w} \) is a vector of all weights \( w_i \)
  - \( \mathbf{x} \) is a vector of all features \( x_i \)

---

# Vectorization

## Normal way vs. Vectorization
- **Normal way**:  
  Multiply each \( x_i \) by its corresponding \( w_i \), sum them, then add \( b \). This requires a loop for \( n \) features.
- **Vectorized way**:  
  Compute the dot product \( \mathbf{w} \cdot \mathbf{x} \) in a single step, then add \( b \).  
  Example with NumPy:  
  ```python
  f = np.dot(w, x) + b
  ```
- **Why it’s faster**:
  - Avoids explicit loops in Python.
  - NumPy’s `dot()` leverages low-level optimized code and parallel hardware.

![Vectorization using numpy](/Images/NumpyVictorization.png)  
*Figure: Normal implementation vs. NumPy vectorized implementation.*

---

## Why Vectorization is Better
- **Normal way**:  
  Requires \( n \) separate multiplications and additions for \( n \) features.
- **Vectorized way**:  
  Performs all multiplications in parallel, producing the result in a single operation.

![Without Vectorization VS Vectorization behind the scenes](/Images/VictorizationBehindTheScenes.png)  
*Figure: How vectorization speeds up computations using parallel processing.*

---

## Vectorization with Gradient Descent
- Speeds up both prediction and parameter updates.
- Instead of updating each \( w_i \) in a loop, vectorized gradient descent updates all weights at once:
  ```python
  w = w - alpha * dj_dw
  b = b - alpha * dj_db
  ```
  where `dj_dw` is a vector containing partial derivatives for all weights.

![Gradient Descent using victorization](/Images/GradientDescentWithVictorization.png)  
*Figure: Impact of vectorization on gradient descent speed.*

---

# Gradient Descent for Multiple Linear Regression
- Same principle as single-feature case but applied to vectors.
- Update rule in vectorized form:
  \[
  \mathbf{w} := \mathbf{w} - \alpha \frac{\partial J}{\partial \mathbf{w}}, \quad b := b - \alpha \frac{\partial J}{\partial b}
  \]
- Vectorization ensures efficient updates even with thousands of features.

