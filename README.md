# Financial-News-Sentiment-Analysis
## Intro
Sentiment Analysis has many impactful real world applications particularly in economics and finance. Financial News can give very meaningful insights about the price of a financial instrument, and we often don't have the time read every news article to make our own decisions. So, how can we leverage Natural Language Processing to aid our classification of financial news? There are three approaches to financial news sentiment analysis that I cover in this repository. The first is to build a Bag of Words model. That is, using word counts to calculate the probability that an article is negative, neutral, or positive. The second approach is to utilize word embeddings, which asssign each word a 300 dimensional word vector that represents its overall meaning. Finally, we can classify News Articles using sentence transformers that convert sentences into a 768 dimensional vectors that represent the meaning of the sentence and fit a classifier using these vectors. With these approaches we can use article headlines to classify financial news as either negative, netural or positive. 

## Data Overview and Criteria for success

The data for for acccomplishing this task was taken from kaggle (link in sources section), and it consists of 4846 news headlines with labeled sentiments. There not an equal amount of examples for each sentiment. This is called class imbalance. To overcome this imbalance, the metrics we are most concerned about are precision and recall scores for positive and negative sentiment headlines. Using this metric as our metric for performance has two advantages, it combats against the class imbalance that we have, and it makes our model accuracy more relavent to the real world. If an investment bank is looking to use NLP to classify financial news, we're going to want to know when we predict a positive sentiment, what is the likelihood that the article is actually positive. This metric can be described by recall. Additionally, when we're going to want to measure of all of the news that we know was positive how many of them were correctly classfiied as such by our model. This metric is known as precision, and for this project our goal is to have over 75 % precision and recall for our model.

## Bag of Words

The first approach is a BOW (Bag Of Words) model. BOW model is simply taking the entire vocabulary of all of our headlines and using each word in our voaculary as a feature. Then, the features for any given headline is the word count for every word in the vocabulary. For example, consider the headline:

>“We went to the market with yield guidance of the 7.25 % area , which gave us the flexibility to go up or down by 1-8th.”

This can be represented by the following dataframe:



I did not include every column, but



