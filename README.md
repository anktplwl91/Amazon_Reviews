# Amazon_Reviews
Multilabel classification of Amazon reviews based on the provided title and complete review text  

**Problem Statement**

We are given Amazon reviews, review title and review complete text as input features, using which we are supposed to predict the labels for unseen reviews.

Train file has 3 columns, Review Title, Review Text and Topic(Target variable). Test file only has Review Title and Review Text.

**Data Cleaning**

As all Data Science projects should go, this is an essential first step to go about. The reviews are generally given by users on
Amazon website, and might contain noisy words, expressions, numbers, or phrases which do not actually add up to model performance,
or even sometimes degrade it. I used Regex to take out such quotations, weblinks, and few noisy expressions having Video ID.

**Models Used**

I experimented with 3 different models majorly : XgBoost, NB-SVM and Deep Learning (Bi-LSTM, LSTM-Conv1D). After training initial
models, I used *feature_importances* from trained models to filter out only features which were impacting the Target variable. 
Once I had this small subset of features, I then searched for optimal hyper-parameters using *RandomSearchCV* on this small
feature space.
