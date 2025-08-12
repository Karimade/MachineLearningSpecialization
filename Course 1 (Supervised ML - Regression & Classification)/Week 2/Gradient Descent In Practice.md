# Multiple Features:
- Instead of make the training on one feature (x), we do the training on multiple features (xi,..).
- old version f(x) = wx + b;
- new version f(x) = w[i]x[i] +...+ w[n]x[n] + b;
- vectorized version = f(x) = w.x + b;, as w is a vector of all teh possible wi and x is the vector of all the xi
# Victorization:
## Difference between normal way VS victorization to calc mult features linear regression
- It is the dot product of two vectors.
- It makes the code shorter and makes it run much faster and it is easier to write and read.
- Without victorization you will take each input feature , multiply it by the parameter , then at the end summing all of them, or make that inside a loop and do the same process.
- But suppose the *n* is like 100,000 so this is not effecient as using victorization (using numpy library)
- The reason that the vectorized implementation is much faster is behind the scenes The numpy dot function is able to use parallel hardware in computer
![Victorization using numpy](/Images/NumpyVictorization.png)
*Figure: Showing the normal way of implementing the linear regression model with multiple input features VS using numpy victorization.*

## Why Victorization is better
- the normal way will make the calculation of the each step of ( f + w[i] * x[i] ) n times, so it makes n steps to calc the model
- The victorization numpy np.dot(), runs with victorization in the computer hardware, it calculates the model resutl in a single step only but multiplying each w[i] and x[i] in parallel.  

![Without Victorization VS Victorization behind the scenes](/Images/VictorizationBehindTheScenes.png)
*Figure: Showing why victorization is bette than the normal way without victorization.*

## why using victorization with multipel linear regression
- like before it also makes the update of the model parameters much faster, instead of updating n parameters inside a loop we use the victorized version to make it in a singel parallel step, and the impact appears when you have like thousands of features.
![Gradient Descent using victorization](/Images/GradientDescentWithVictorization.png)
*Figure: Showing the impact of using victorization with gradient descent.*
# Gradient Descent For Multiple Linear Regression:
