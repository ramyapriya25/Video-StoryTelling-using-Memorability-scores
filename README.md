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

**Video Captioning model**

In video captioning, LSTM models can be used to learn the mapping between
the visual features of a video and their corresponding textual descriptions. The
visual features are extracted from the frames of the video using techniques such
as convolutional neural networks (CNNs) , and the textual descriptions can be
represented as sequences of words or phrases.
The LSTM model takes the visual features as input and generates a sequence of
words that describe the visual content of the video. The model is trained on a
large dataset of video-caption pairs, and it learns to generate captions that are
semantically and grammatically correct.
To use LSTM in video captioning, we have implemented the model using deep
learning frameworks such as TensorFlow or PyTorch. The input to the model is a
sequence of visual features extracted from the frames of the video, and the output
is a sequence of words that describe the visual content of the video.
The encoder’s first LSTM cell receives the features from the first frame. The
elements of the second frame come next, and so on until the eighty-first frame.
All other encoder outputs are ignored because, for this issue, we are only
concerned with the encoder’s final state. The encoder LSTM’s final state now
serves as the decoder LSTM’s initial state. Here, LSTM ’bos’ serves as input to
begin the phrase in the first decoder. Each and every word of the caption from the
training data is fed one by one until ’eos’.
The decoder cell’s starting state is always the encoder cell’s final state. For our
issue, we’ll feed the decoder the captions while using the encoder to input the
video features.

REFERENCES
https://medium.com/analytics-vidhya/video-captioning-with-keras-511984a2cfff
https://github.com/CryoliteZ/Video2Text

https://github.com/PacktPublishing/Intelligent-Projects-Using-Python/tree/master/Chapter05

https://pypi.org/project/PyPrind/
https://en.wikipedia.org/wiki/Keras
https://www.tensorflow.org/
https://en.wikipedia.org/wiki/Spearman%27s_rank_correlation_coefficient
https://github.com/dazcona/memorability
