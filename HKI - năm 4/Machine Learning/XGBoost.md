#ML 

# I. Reference:
## 1. [XGBoost From Scratch](https://randomrealizations.com/posts/xgboost-from-scratch/)
## 2. [XGBoost Explained](https://randomrealizations.com/posts/xgboost-explained/index.html)
## 3. [XGBoost Paper](https://www.kdd.org/kdd2016/papers/files/rfp0697-chenAemb.pdf)

# II. XGBoost is a Gradient Boosting Machine
XGBoost is a gradient boosting method, iteratively constructed composite model. Formal model is as follow:
$$ \hat{y_i} = F(\mathbf{x}_i) = b + \eta \sum^{K}_{k=1} f_k(\mathbf{x}_i) $$
where $b$ is the base prediction, $\eta$ is the learning rate hyperparameter that helps control overfiting by reducing the contributions of each booster and each of the $K$ boosters $f_k$ is a decision tree.

# III. Characteristic
- Use Newton Descent instead of Gradient Descent
- Use L2 Regularization
- Split Finding