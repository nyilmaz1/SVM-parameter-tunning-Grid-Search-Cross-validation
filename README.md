# SVM-parameter-tuning-Grid-Search-Cross-validation

**SVM:**
SVM draws a hyperplane to separate the classes.

SVMs are used for **classification, regression and outliers detection.**

For multiclass classification: **SVC, NuCVS, LinearSVC.** 

**Multiclass** If there are three or more classes, the problem is considered multiclass classification. If there are two classes, then it's a **binary** classification problem. Mutliclass is different from Multilabel classification. In mutliclass, each instance is assigned to only one label: a fruit can be either an apple or a pear but not both at the same time. In **mutlilabel** problems, one instance can have more than one label: a book might be about any of politics or finance at the same time or none of these. 

We can reduce the problem of multiclass classification to multiple binary classification problems. It can be categorized into **One vs Rest and One vs One.** 

**One-vs-rest:** Training one classifier per class. For class A, it will assume instances with class A as positive and the rest as negative. 

**One-vs-one:** Training one binary classifier per two pairs of classes at a time. 

For regression: Support Vector Regression (SVR), NuSVR and LinearSVR.

For outliers detection: OneClassSVM. `estimator.fit` is only given `X_train`. like in an unsupervised model. Predict method sorts the new observations as inliers or outliers: `estimator.predict(X_test)`. 


## Parameter Tuning for SVM:
### KERNEL:
it must be one of linear, poly, rbf, sigmoid, precomputed or a callable. If none is given , rbf will be used. 
**linear:** for linear models, use this.
**poly:** allows learning of non-linear models. Popular in Natural Language Preprocessing  
**rbf:** more popular than poly for non-linear data points. commonly used in  SVM classifications.    

### REGULARIZATION:
Regularization is termed as C parameter in sklearn library. Smaller C misclassifies more data points, while higher C make better classification to an extend.

### GAMMA:
The model is highly sensitive to gamma parameter. High gamma will cause overfitting.When the gamma is too low, model cannot capture the complexity of the data

### GRID SEARCH:
Scikit-Learn's `GridSearchCV` is a one way to fine-tune model parameters. Grid Search evaluate all possible combinations of hyperparameter using cross-validation from the list of values you provided. 

## Cross-Validation: cv = Leave One Out: accuracy score 0.99

**Leave One Out:** If you have N images in total, the parameter optimization is performed on N-1 images and then the performance of the model is tested on Nth image. This process is repeated for N times, each time leaving out a different image to use as the single test set. 
