# DISCRIMINATIVE LEARNING
* Learn P(y|x) or learn the mapping from x to y
* Use gradient descent to update the decision boundary between classes
* Look at classes simultaneously and learn the decision boundary

# GENERATIVE LEARNING ALGORITHM
* GDA 
* Naive Bayes
    * This would instead learn P(x|y) and P(y) - class prior
    * Look at each classes specifically and learn the features of each class

# Bayes' Rule

Bayes' Rule describes the probability of an event, based on prior knowledge of conditions that might be related to the event.

$$P(y=1|x) = \frac{P(x|y=1)P(y=1)}{P(x)}$$

where $$P(x)=P(x|y=1)P(y=1)+P(x|y=0)P(y=0) $$

# GAUSSIAN DISCRIMINANT ANALYSIS
##  Gaussian Discriminant Analysis (GDA) works decently under data that is Gaussian. If it is not Gaussian then it wouldn't be as good as LOGISTIC REGRESSION.

GDA is a generative learning algorithm that models the joint probability distribution \( P(x, y) \) and uses Bayes' Rule to compute the posterior \( P(y|x) \).
$$P(x | y = 0) = \frac{1}{(2\pi)^{n/2} |\Sigma|^{1/2}} \exp\left( -\frac{1}{2} (x - \mu_0)^T \Sigma^{-1} (x - \mu_0) \right)$$
$$P(x | y = 1) = \frac{1}{(2\pi)^{n/2} |\Sigma|^{1/2}} \exp\left( -\frac{1}{2} (x - \mu_0)^T \Sigma^{-1} (x - \mu_1) \right)$$
$$P(y)=\phi^y(1-\phi)^{1-y} $$
###  Model Assumptions
- $ y \in \{0, 1\} $
- $ x | y = 0 \sim \mathcal{N}(\mu_0, \Sigma) $
- $ x | y = 1 \sim \mathcal{N}(\mu_1, \Sigma) $
- Shared covariance matrix $ \Sigma $

###  Parameters
- $$ \phi = P(y = 1) $$
- $$ \mu_0 = \mathbb{E}[x | y = 0] $$
- $$ \mu_1 = \mathbb{E}[x | y = 1] $$
- $$ \Sigma = \mathbb{E}[(x - \mu_y)(x - \mu_y)^T] $$

###  Decision Rule
Use Bayes' Rule to compute:


$$
P(y = 1 | x) = \frac{P(x | y = 1) P(y = 1)}{P(x)}
$$



Predict \( y = 1 \) if:


$$
\log\left(\frac{P(x | y = 1)}{P(x | y = 0)}\right) + \log\left(\frac{\phi}{1 - \phi}\right) \geq 0
$$



This results in a **linear decision boundary** when the covariance matrices are shared.

If we use different covariance matrices the **decision boundary is not linear** anymore

# NAIVE BAYES
## Naive Bayes Classifier Formula

Given a feature vector \( x = (x_1, x_2, ..., x_n) \), the Naive Bayes classifier predicts the class label \( y \) using:



$
P(y \mid x) \propto P(y) \prod_{i=1}^{n} P(x_i \mid y)
$



###  Explanation:
- $ P(y) $: Prior probability of class $ y $
- $ P(x_i \mid y) $: Likelihood of feature $ x_i $ given class $ y $
- Assumes **conditional independence**: each feature $ x_i $ is independent given the class label $ y $

###  Prediction Rule:
Choose the class $ y $ that maximizes the posterior:



$
\hat{y} = \arg\max_y \left[ P(y) \prod_{i=1}^{n} P(x_i \mid y) \right]
$



###  Laplace Smoothing (to avoid zero probabilities):


$
P(x_i \mid y) = \frac{\text{count}(x_i, y) + 1}{\text{count}(y) + k}
$


- $ k $: number of possible values for $ x_i $

