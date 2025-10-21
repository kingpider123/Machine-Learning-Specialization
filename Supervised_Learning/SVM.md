# SUPPORT VECTOR MACHINES
Able to learn very non-linear decision boundaries
* FOR LOGISTIC REGRESSION: takes the feature vector $X1, X2$ and map it into a high dimensional feature vector with $ X_1,X_2,X_1^2,X_2^2,X_1X_2, ...$ and put it into new feature vector $ \phi(X)$

## Optimal margin classifer 
### 🎯 Objective:
Find the hyperplane (linear line in high dimensional space) that maximizes the margin between classes.

### ✳️ Functional Margin:
For a training example $ (x^{(i)}, y^{(i)}) $, where $ y^{(i)} \in \{-1, +1\} $:



$
\hat{\gamma}^{(i)} = y^{(i)} (w^T x^{(i)} + b)
$



### 📐 Geometric Margin:


$
\gamma^{(i)} = \frac{\hat{\gamma}^{(i)}}{\|w\|}
= \frac{y^{(i)} (w^T x^{(i)} + b)}{\|w\|}
$



### 🧮 Optimization Problem (Hard Margin SVM):


$
\min_{w, b} \frac{1}{2} \|w\|^2
$


subject to:


$
y^{(i)} (w^T x^{(i)} + b) \geq 1 \quad \text{for all } i
$



### 🔧 Soft Margin (with slack variables $ \xi_i $):


$
\min_{w, b, \xi} \frac{1}{2} \|w\|^2 + C \sum_{i=1}^{m} \xi_i
$


subject to:


$
y^{(i)} (w^T x^{(i)} + b) \geq 1 - \xi_i, \quad \xi_i \geq 0
$



### 🧠 Prediction Rule:


$
\hat{y} = \text{sign}(w^T x + b)
$




### Separable case
### Inseparable case

## Kernels