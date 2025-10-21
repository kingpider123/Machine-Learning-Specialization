# SUPPORT VECTOR MACHINES
Able to learn very non-linear decision boundaries
* FOR LOGISTIC REGRESSION: takes the feature vector $X1, X2$ and map it into a high dimensional feature vector with $ X_1,X_2,X_1^2,X_2^2,X_1X_2, ...$ and put it into new feature vector $ \phi(X)$
* The idea is to take low dimensional data and transform it into high dimensional data -----> Find a Support Vector Classifier that separates the higher dimensional data into groups

* Mathematically, SVM use sth called **Kernel Functions** to systematically find **Support Vector Classifer** in higher dimension

## Optimal margin classifer - separable datas
### Objective:
Find the hyperplane (linear line in high dimensional space) that maximizes the margin between classes.

###  Functional Margin:
For a training example $ (x^{(i)}, y^{(i)}) $, where $ y^{(i)} \in \{-1, +1\} $:



$
\hat{\gamma}^{(i)} = y^{(i)} (w^T x^{(i)} + b)
$



###  Geometric Margin:


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

## Kernels - inseparable datas
* Kernel functions only calculate the relationships between every pair of points as if they are in the higher dimensions; they don't actually do the transformation

* This is called **the Kernel trick** - reduce the amount of computation required for SVC by avoiding the math that transforms the data from low to high dimensions
###  Polynomial Kernel, which has a parameter ***d***, which stands for the **degree** of the polynomial
* The polynomial kernel computes the relationships between each 
pair of observations in d-Dimension

* And those relationships are used to find a SVC

* We can find a good value for **d** with **Cross Validation**

### Radial Kernel (Radial Basis Function- RBF Kernel)
* Find SVCs in infinite dimensions

* Behave like a **Weighted Nearest Neighbor** model where the closest observations (the nearest neighbors) have a lot of influence on how we classify the new observation

* RBF Kernel uses the closes neighbors' classification for the new observation