#ML 

(Youtube) Context: Decision Tree is useful but have many drawbacks quote "The Elements of Statistical Learning": Trees have one aspect that prevents them from being the ideal tool for predictive learning, namely inaccuracy. They work great with the data used to create them, but they are not flexible when it comes to classifying new samples.

(Wiki) History: First propose in 1993 then further developed in 1995

(Wiki) Random Forest / Random Decision Forest is an ensemble learning method for classification, regression and other tasks. 

(Youtube) Random Forests combine simplicity of decision trees with flexibility resulting in a vast improvement in accuracy

# Step 1: Bootstrap
# Step 2: Create Decision Tree
# Step 3: Bagging

{'n_base_learner': 112, 'max_depth': 18, 'min_samples_leaf': 5, 'min_information_gain': 0.011558462916702938, 'numb_of_features_splitting': 'sqrt', 'bootstrap_sample_size': 0.983461847066747}.

Best Parameters: {'n_base_learner': 108, 'max_depth': 19, 'min_samples_leaf': 18, 'min_information_gain': 0.012931079183505816, 'numb_of_features_splitting': 'sqrt', 'bootstrap_sample_size': 0.7091151607994467}

{'n_base_learner': 117, 'max_depth': 16, 'min_samples_leaf': 16, 'min_information_gain': 0.019330446562925326, 'numb_of_features_splitting': 'sqrt', 'bootstrap_sample_size': 0.7174507320418088}