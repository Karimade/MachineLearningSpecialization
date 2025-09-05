# Multiple Features in Linear Regression

## Concept
- In single-feature linear regression:  
  `f(x) = w * x + b`  
- In multiple-feature linear regression:  
  `f(x) = w1 * x1 + w2 * x2 + ... + wn * xn + b`  
- **Vectorized form**:  
  `f(x) = w · x + b`  
  where:
  - `w` is a vector of all weights `wi`
  - `x` is a vector of all features `xi`
---

# Vectorization

## Normal way vs. Vectorization
- **Normal way**:  
  Multiply each `x_i` by its corresponding `w_i`, sum them, then add `b`.  
  This requires a loop for `n` features.
- **Vectorized way**:  
  Compute the dot product `w · x` in a single step, then add `b`.  
  Example with NumPy:  
  ```python
  f = np.dot(w, x) + b
  ```
- **Why it’s faster**:
  - Avoids explicit loops in Python.
  - NumPy’s `dot()` uses low-level optimized code and can run operations in parallel on hardware.

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

![Victorization and normal way results](/Images/MeasureVictorizationVSNormalWay.png)  
*Figure: Showing the results of using victorization and normal way.*
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
- Same principle as the single-feature case but applied to vectors.
- **Update rule in vectorized form**:  
  ```
  w := w - α * (∂J/∂w)
  b := b - α * (∂J/∂b)
  ```
  - where `w` is a vector containing the model parameters
- Vectorization ensures efficient updates even with thousands of features.

![Vectorized Gradient Descent](/Images/VectorizedGradientDescent.png)  
*Figure: Showing the notation of the gradient descent with the vector notation.*

![Vectorized Gradient Descent2](/Images/C1_W2_VectorizedGradientDescentNotation.png)  
*Figure: Showing the notation of the gradient descent with the vector notation.*
