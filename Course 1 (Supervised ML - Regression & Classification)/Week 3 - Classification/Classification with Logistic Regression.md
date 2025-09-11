# Linear Regression for Classification problems
## What is Classification
- The output variable (y) has a known range of values, meaning it can be only one of two values(classes,categories) in what is called **Binary Classification**
![Classification Problem](/Images/C1_W3_ClassificationProbelm.png)  
*Figure: Defining what is classification.*
---
## Why not Linear Regression for Classification
![Linear Regression for Classification](/Images/C1_W3_LinearRegressionForClassificationProblem.png)  
*Figure: Showing the result of using linear regression for classification problem.*
- from the figure we have two classes, we will denote them like `0` and `1`, so `y` should be `0` or `1`.
- Linear regression predicts not just the values of 0 and 1 but all numbers between 0 and 1 or even less than 0 or greater than 1.
- We could make a threshold to take like from `0` to `0.5` as `0` and the other range as 1.
- It will work for some cases, but if the data is scattered max on the right then the decision boundary also shift like in the figure, now things began to began worth.
## Logistic Regression and Sigmoid Function
- It is about predicitng a specific classes of categories Like `true` or `false`.
- To make the output identified by possible values like `0` or `1` we use the **Sigmoid Function**
- **Sigmoid Function** :No matter how the ouput is large or small , it will always has a value between 0 and 1.
![Sigmoid Function](/Images/C1_W3_SigmoidFunction.png)  
*Figure: Showing the mathematics of the sigmoid function.*
---
- So now we will take the prediction value of the model `f(x) = w.b + b` and pass it to the sigmoid function.
- So now the model becomes `f(x) = g(w.x + b)`
![Logistic Regression Model](/Images/C1_W3_LogisticRegression.png)  
*Figure: Showing the Logisic Regression model.*

### Interpretting Logisitc Regression ouput
- Think about the ouput of the logistic regression as the probability that the class will equal to one given a certain input `x`
 ![Logistic Regression output](/Images/C1_W3_LogisticRegressionOutput.png)  
 *Figure: Showing how to interpret logistic regression output.*

 ## Decision Boundary
 - The line that separates the positive and the negative predections (it is computed by making the prediction model equal to zero).
![Decision Boundary](/Images/C1_W3_DecisionBoundary.png)  
*Figure: Showing the decision boundary explanation of the logistic regression*  
---
![Decision Boundary example](/Images/C1_W3_DecisionBoundaryExample.png)  
*Figure: Showing an example on the decision boundary of the logistic regression* 
---
- If we used only non-polynomial features in logistic regression then the decision boundary will always linear.
- The non linear decision boundary arises when using polynomial features in logistic regression.
![Non Linear Decision Boundary example](/Images/C1_W3_NonLinearDecisionBoundary.png)  
*Figure: Showing an example on the non linear decision boundary of the logistic regression* 
---
![Complex Non Linear Decision Boundary example](/Images/C1_W3_ComplexNonLinearDecisionBoundary.png)  
*Figure: Showing an example on the complex non linear decision boundary of the logistic regression* 