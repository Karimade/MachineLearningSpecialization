# Linear Regression for Classification problems
## What is Classification?  
- In **classification problems**, the target variable `y` belongs to a **set of categories** (e.g., `0` or `1` in **binary classification**, or multiple categories in multi-class problems).  
- Example: Spam (`1`) vs Not Spam (`0`).  

![Classification Problem](/Images/C1_W3_ClassificationProbelm.png)  
*Figure: Defining classification.*  

---
## Why not Linear Regression for Classification
- In regression, predictions can take **any real value** (negative, >1, etc.).  
- In classification, we need outputs limited to **0 or 1** (or probabilities between them).  
- One workaround: set a **threshold** (e.g., predict `1` if ≥ 0.5, else `0`).  
- **Problem:** The decision boundary shifts unpredictably if the data is scattered, leading to poor separation.  

![Linear Regression for Classification](/Images/C1_W3_LinearRegressionForClassificationProblem.png)  
*Figure: Linear regression failing at classification.*  

---

## Logistic Regression and the Sigmoid Function  

To solve this, we use **logistic regression**:  
- Instead of outputting raw values, it passes the linear model through the **sigmoid function**:  

`g(z) = 1 / (1 + e^(-z))`


- The sigmoid squashes any input into the range **(0,1)**.  
- Model:  

`f(x) = g(w · x + b)`


![Sigmoid Function](/Images/C1_W3_SigmoidFunction.png)  
*Figure: The sigmoid function.*  

---

### Interpreting Logistic Regression Output  
- The output of logistic regression = **probability** that the input belongs to the positive class (`y = 1`).  
- Example: If `f(x) = 0.8`, then there’s an **80% chance** the input belongs to class `1`.  

![Logistic Regression output](/Images/C1_W3_LogisticRegressionOutput.png)  C1_W3_LogisticRegressionOuput
*Figure: Logistic regression output interpretation.*  

---


## Decision Boundary  

- A **decision boundary** separates positive predictions (`y=1`) from negative ones (`y=0`).  
- Computed by solving:  

`w · x + b = 0`


![Decision Boundary](/Images/C1_W3_DecisionBoundary.png)  
*Figure: Linear decision boundary.*  

- With only **linear features**, the boundary is always a straight line (linear).  
- Adding **polynomial features** allows **nonlinear boundaries** that better fit complex data.  

![Decision Boundary example](/Images/C1_W3_DecisionBoundaryExample.png)  
*Figure: Example of linear decision boundary.*  

![Non Linear Decision Boundary example](/Images/C1_W3_NonLinearDecisionBoundary.png)  
*Figure: Example of nonlinear decision boundary using polynomial features.*  

![Complex Non Linear Decision Boundary example](/Images/C1_W3_ComplexNonLinearDecisionBoundary.png)  
*Figure: Complex nonlinear decision boundary.*  