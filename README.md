# Political-Tweet-Classification-and-Bot-Detection
This repository contains Political Tweet Classification and Bot detection project that is an ML and feature extraction based project to inspect tweets and users metadata and detect whether a tweet is political or not as well as detect whether a user is bot or not. Project has 3 parts which are feature extraction, tweet classification, and bot classification. The main purpose is to give a possibility range for any users (isBot) or tweets (isPolitical) between [0,1] and to minimize mean square error when those predictions compared to the real labels. Project has 3 steps, at each step the MSE values are decreased to optimize the predictors.

For the feature extruction, some major analysis are in the extraWorks file, and main implementation of the project with appropriate detailed explanation are in the tweet_experiment file.

Some feture extraction, and training data are here:

For data:
  * For the model training I have used the given dataset.
  * I have merged them with the corresponding JSON files to get desired features that I used in the training.
  * I have analyzed all the tweets in the user_tweets JSON file, and created some political entity lists for detection.

For features:
  I have created some features in order to detect if a tweet is a political tweet, or not:
  * 1) Number of political keywords: I created a huge list with many possible political keywords, and this feature calculates their count in the given tweet.
  * 2) Binarized number of political keywords: This feature specifies if the given tweet has some political keywords, or not.
  * 3) Number of political mentions: I created a huge list with many possible political users, and this feature calculates their count in the given tweet.
  * 4) Binarized number of political mentions: This feature specifies if the given tweet has some political mentions, or not.
  * 5) Number of political hashtags: I created a huge list with many possible political hashtags, and this feature calculates their count in the given tweet.
  * 6) Binarized number of political hashtags: This feature specifies if the given tweet has some political hashtags, or not.
  * 8) Politician bias elimination feature: This feature shows if the given tweet mentioning to an important politician: RTErdogan in this case.
  * 9) Net political feature: I created a tiny list of strings which implies being a political tweet for sure.
  * 10) No political feature: I created a tiny list of strings which implies being not a political tweet for sure.
  
  I have created some features in order to detect if a user is a bot, or not:
  * 1) Number of duplicate tweets: I calculated the approximate number of duplicate tweets of the user.
  * 2) Retweet ratio: This feature shows the ratio of retweets to all tweets of the user.
  * 3) Follow similarity: This feature specifies the similarity of followers and following counts.
  * 4) Average hashtag usage: Average number of hashtags used in all tweets of the user.
  * 5) Follow threshold: This features checks if the user is above a threshold, or not.

For models:
  * I have used Logistic Regression, even though this is a classification problem, I calculated the probabilities.
  * I have split the data into two train and test parts and then did cross validation.
  * At the end, my regression models returns values between 0-1 for both isPolitical and isBot predictions.

Additional explanations:
  * In the project, I preferred to use binarized versions of some features since they have a higher accuracy.
  * Also, I have made corrections for the predictions having some patterns in some features.
