# Video-StoryTelling-using-Memorability-scores

The overall architecture consists of two main models the video memorability model and the video captioning model.We have used memento10k dataset for training both these  models and used Video Story dataset for testing.

**Video Memorability Model**

Various regression methods including linear regression,SVR,random forest and ridge regression are combined using stacking method.
Stacking is an ensemble learning technique that involves combining multiple models to improve the overall performance of a prediction task. In stacking, the predictions of multiple models are combined using another model, called a meta-model, which learns to weight the predictions of the base models.

In stacking, the base models are trained on the same data but using different algorithms or features. 
This diversity helps to ensure that the errors of the individual models are not correlated, which can lead to better overall performance.

Once the base models are trained, they are used to make predictions on the validation or test set. 
The predictions from the base models are then used as inputs for the meta-model, which learns to weight them in order to improve the final prediction.

Ensemble approach using SVR, Decision Tree’s and Linear Regression as base classifiers and Ridge Linear Regression as the final estimator.
The initial dataset is divided into a 90:10 test and training set, accordingly. The Keras library is used to create neural networks,
and the architecture has three layers. Ensemble approach contains Decision Tree Regressor, SVR and Linear Regression as used as the base estimators
and are stacked upon each other. Rigid Regression is implemented as the final estimator. In regression techniques, linear regression 
is run on default setup except normalize set to true. SVR and Rigid Regressing is run with a regularization parameter to impose penalty.
Maximum depth of the Random Forest decision trees is set to 10. 
