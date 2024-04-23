## Introduction

This is a project that aims to build classifiers for text, this way you can find the correct subreddit for the topic your text uses. This way you will be able to communicate with others on the appropriate scope. We present 3 different models to select from to classify the text given.

## Usage

To use the tool follow the simple steps below
Navigate to the models Tab (should start on this tab)
In the ‘Enter Text’ field put the thread you want to post about, may want to keep this relatively simple
Select one of the model types below
You will then be presented with one of the subreddits
*Note there is only 100 subreddit types classified

“Cat”-[KNN]-r/aww

“I like to drive cars around”-[Naive Bayes]-r/cars

“What is trump doing”-[MLP]- r/politic

## Documentation

Data Distribution (simply used matlab to display distribution)

![image](https://huggingface.co/spaces/mrgs22/CSI4180HW04SubredditClassificaiton/blob/main/dataDist.png)

This project involved using several different tools, data collection was an issue with the large amount of subreddits that exist. So for the purposes of this project the set of results was reduced down to the 100 present in the dataset. This data set contains all the information necessary, labels and threads. To build the models I made extensive use of the SKL library. I also used NLTK to pull the most important stopwords from the corpus. Finally I used the Numpy, pandas, and gradio for the remainder of the tasks.
![image](https://huggingface.co/spaces/mrgs22/CSI4180HW04SubredditClassificaiton/blob/main/CSI4180HW04.drawio.png)
The biggest part is the creation of training of the models. Starting with preprocessing the threads (which were treated as documents). To do this I simply lowercase everything, then tokenized it all, removed stopwords, stemmed it, checked if it exists in the alphabet. This removed all the unnecessary threads that I could find. Then I threw the result into a simple skl tf idf vectorizer. 

I made three relatively simple models: KNN, Multilayer Perceptron (MLP), and Naive Bayes(NB). All these models performed simple classification on the labels and vectors using the sklearn library. KNN's only configuration is 100 = n, I tried a few different numbers (1,5,10,100,1000) and 100 seem to be the best fitting. MLP has 100 layers (also played around with dimensions to see if significantly improved perfromance), this takes a long time to completely finish training so if you stop it in the middle it will sometimes just use those weights. Finally is the NB which requires no specific parameters. All of these used a simple 95/5 split on the dataset.

## Contribution

Training models - Tuning basic parameters on the models (KNN and MLP) to improve performance
Data preparation - prepreprocess and vectorize dataset

## Limitation

Trained on 100 subreddit threads (limited output to these subreddits)
Issue with Thread being to long
Issue with Threads containing multiple specific topics
