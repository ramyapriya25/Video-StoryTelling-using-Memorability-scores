# Video-StoryTelling-using-Memorability-scores 

The overall architecture consists of two main models the video memorability model and the video captioning model.We have used memento10k dataset for training both these  models and used Video Story dataset for testing. To obtain the story of a given video follow the below steps:
1. Split the given video into n number of equal segments - use the video splitting python notebook.
2. Extract the HMP and C3D feature for each of the splitted segments usignthe HMP and C3d notebooks.
3. Predict the captions for each of the ideo segment using the video captioning model.
4. Use the HMP,C3D and caption to predict the memorability scores of each of the segments using the regression methods in video memorability model.
5. Discard the videos with low meorability scores and combine the captions of the remaining video segments in order.

We have used the Memento10k dataset for training the video captioning model and video memorability model and Video Story dataset for testing the whole project.

![Overall final](https://user-images.githubusercontent.com/69419671/235332386-f56da015-3903-4769-9d0c-90470ced4030.png)


**Video Memorability Model**

Various regression methods including linear regression,SVR,random forest and ridge regression are combined using stacking method.
Stacking is an ensemble learning technique that involves combining multiple models to improve the overall performance of a prediction task. In stacking, the predictions of multiple models are combined using another model, called a meta-model, which learns to weight the predictions of the base models.

In stacking, the base models are trained on the same data but using different algorithms or features. 
This diversity helps to ensure that the errors of the individual models are not correlated, which can lead to better overall performance.

Once the base models are trained, they are used to make predictions on the validation or test set. 
The predictions from the base models are then used as inputs for the meta-model, which learns to weight them in order to improve the final prediction.

**Video Captioning model**

In video captioning, LSTM models can be used to learn the mapping between the visual features of a video and their corresponding textual descriptions. The
visual features are extracted from the frames of the video using techniques such as convolutional neural networks (CNNs) , and the textual descriptions can be
represented as sequences of words or phrases. The LSTM model takes the visual features as input and generates a sequence of words that describe the visual content of the video. The model is trained on a large dataset of video-caption pairs, and it learns to generate captions that are semantically and grammatically correct. To use LSTM in video captioning, we have implemented the model using deep learning frameworks such as TensorFlow or PyTorch. The input to the model is a sequence of visual features extracted from the frames of the video, and the output is a sequence of words that describe the visual content of the video.


REFERENCES
https://medium.com/analytics-vidhya/video-captioning-with-keras-511984a2cfff
https://github.com/CryoliteZ/Video2Text

https://github.com/PacktPublishing/Intelligent-Projects-Using-Python/tree/master/Chapter05

https://pypi.org/project/PyPrind/
https://en.wikipedia.org/wiki/Keras
https://www.tensorflow.org/
https://en.wikipedia.org/wiki/Spearman%27s_rank_correlation_coefficient
https://github.com/dazcona/memorability
