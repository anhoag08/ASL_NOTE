#ML 



Gradient Descent

Batch Gradient Descent

Multivariate Linear Regression

# 1. Model Representation
![[Pasted image 20241022160005.png|500]]

## a. Cost Function
Hypothesis:
$$h(x) = w_0 + w_1x$$
Parameters:
$$w_0, w_1$$
Cost Function: mean squared error (MSE)
$$J(w_0, w_1) = \dfrac{1}{2m}\sum_{i=1}^m(h(x_i) - y_i)^2$$
Goal: $min_{w_0w_1}J(w_0, w_1)$

## b. Gradient Descent
