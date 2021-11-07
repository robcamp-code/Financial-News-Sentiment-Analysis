# Financial-News-Sentiment-Analysis
## Intro
Sentiment Analysis has many impactful real world applications particularly in economics and finance. Financial News can give very meaningful insights about the price of a financial instrument, and we often don't have the time read every news article to make our own decisions. So, how can we leverage Natural Language Processing to aid our classification of financial news? There are three approaches to financial news sentiment analysis that I cover in this repository. The first is to build a Bag of Words model. That is, using word counts to calculate the probability that an article is negative, neutral, or positive. The second approach is to utilize word embeddings, which asssign each word a 300 dimensional word vector that represents its overall meaning. Finally, we can classify News Articles using sentence transformers that convert sentences into a 768 dimensional vectors that represent the meaning of the sentence and fit a classifier using these vectors. With these approaches we can use article headlines to classify financial news as either negative, netural or positive. 

## Data Overview and Criteria for success

The data for for acccomplishing this task was taken from kaggle (link in sources section), and it consists of 4846 news headlines with labeled sentiments. There are not an equal amount of examples for each sentiment. This is called class imbalance.
![newplot(2)](https://user-images.githubusercontent.com/59036285/140618447-9263ee1a-72a1-4f51-9017-acfbde7b5244.png)
To overcome this imbalance, the metrics we are most concerned about are precision and recall scores for positive and negative sentiment headlines. Using this metric as our metric for performance has two advantages, it combats against the class imbalance that we have, and it makes our model accuracy more relavent to the real world. If an investment bank is looking to use NLP to classify financial news, we're going to want to know when we predict a positive sentiment, what is the likelihood that the article is actually positive. This metric can be described by recall. Additionally, we want a metric for the percentage of labeled positive news that was correctly classified by our model. This metric is known as precision, and for this project our goal is to have over 75 % precision and recall for our model.

### Model Metrics:

- Precision
- Recall
- AUC
- Accuracy


## Bag of Words

The first approach is a BOW (Bag Of Words) model. BOW model is simply taking the entire vocabulary of all of our headlines and using each word in our voaculary as a feature. Then, the features for any given headline is the word count for every word in the vocabulary. For example, consider the headline:

>“We went to the market with yield guidance of the 7.25 % area , which gave us the flexibility to go up or down by 1-8th.”

This can be represented by the following dataframe:

![Bow_Example](https://user-images.githubusercontent.com/59036285/140618434-1329e887-d938-409c-b989-82e4438c214d.png)

I did not include every column, but you can see how our model will use the information from the headline to make a prediction. Using word counts can give us some useful plots for understanding which words contribute to news sentiment. The plot below shows the probability of each sentiment given that the word said appears in our headline.

![said](https://user-images.githubusercontent.com/59036285/140618452-8550893e-028b-4dba-a56b-20eb714d3615.png)

In red are the probabilities given that said appeared in the headline, and in blue are the headlines where said does not appear in the headline. We can calculate the probability of a positive article given the occurence of "said" in the headline using bayes theorem: 

<img width="574" alt="Bayes_Theorem" src="https://user-images.githubusercontent.com/59036285/140660817-e49f237e-b96f-406f-bb38-5a723dd587da.png">

The calculation above confirms what we see in the plot. You can view the code in the EDA notebook to see the calculations. The following two plots illustrate the same conditional probabilities with different key words.

![increase](https://user-images.githubusercontent.com/59036285/140618440-f2c10db5-4672-4965-89ce-06c1a5ba215a.png)

![profit](https://user-images.githubusercontent.com/59036285/140618449-43b5b793-a33c-4325-9bd8-b59ea7e6aeb9.png)


![BOW_performance](https://user-images.githubusercontent.com/59036285/140618437-dc311af8-35f5-4f43-bee4-9ce6c5fba0a7.png)
<br>
**Model Metrics**
- Accuracy:
- Precision: 
- Recall:
- AUC score: 

## RNN

![RNN_performance](https://user-images.githubusercontent.com/59036285/140618451-d3e5ccd2-7f26-417e-be6c-af5ac329fb35.png)

## Huggingface
![HuggingFace_performance](https://user-images.githubusercontent.com/59036285/140618439-2fdca539-357d-47dd-ac8a-08b239a48fac.png)
