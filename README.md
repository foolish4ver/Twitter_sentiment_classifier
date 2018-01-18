### Twitter Sentiment Classifier

This repo contains the code that will classify tweets as either _positive_ or _negative_ using various machine learning models such as Naive baeyes, Random Forest and others. 
Rather than relying on older algorithms such as VADER and Textblob, this method models a classifier from scratch which also takes into account the presence of features such as emoticons, punctuations, exclamations, hashtags and other characters to determine the sentiment of the tweet.

#### **Usage:**

#####  Getting the data:

A training set of data from Stanford was used to train the model.It can be found [here.](http://cs.stanford.edu/people/alecmgo/trainingandtestdata.zip) 
A different training set can also be used to train the model as well. The path for the training data is **data/training.csv**
Any other data set can be used and placed in the above path to obtain the prediciton.
The format for the data is as follows:


| tweet  | Sentiment |
| ------------- | ------------- |
| eeeks i like some1 :X :S. gossh, i promised myself not again! but just cant help it this time   | 1  |
| @euniqueflair You would be very happy with a Razer Mamba  http://is.gd/13mMG recommended!  | 1  |
| Freakin' crap! I just bit my tongue on accident.  | 0  |


##### Extracting features:

The following features were added to the existing dataset.
1. No. of positive emoticons(/data/positive.txt)
2. No. of negative emoticons(/data/negative.txt)
3. No. of exclamations
4. No. of hashtags
5. No. of question marks
6. No. of hyperlinks

Prior to fitting the model and using machine learning algorithms for training, we need to represent it in a bag of words model. Plus to add the above features to the training and the testing data set, the following script is run on the script.
```
python add_features.py -f training.csv
```
_Note: Pass the name of the data file as the parameter for -f_

##### Prediction:

After the Analytical Base Table is ready for sentiment classification, various machine-learning algorithms can be used to classify the tweets as positive or negative.
Run the script to check the results of the prediction.
```
python predict.py
```
