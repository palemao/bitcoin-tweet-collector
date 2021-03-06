# bitcoin-price-prediction


## Variable 1 - Twitter BTC price sentiment 

### Collecting Tweets (Tweepy)

*streaming_with_error.py* file collects tweets, number of likes on each tweet, number of retweets on each tweet and datetime of tweet.  

    twitterStream.filter(track=["Bitcoin", "Ethereum", "Tezos", "Stellar", "Cardano", "Neo", "Tron", "Quant", "DigiByte"])
Tweets containing these key words are collected, but these can be changed to anything you want.
      
    on_error(self, status)
 Error handling function: This function allows us to reconnect in 5 seconds automatically if connection drops (i.e. if  too many api calls).

### twitter feed downtimes 

Tweets were collected on personal laptop so it was difficult to keep laptop on for 3 months consistently therefore there will be gaps in the dataset recorded in *Recorded downtimes.docx* 

## Finding Labelled data for training
Labeled data with positive, negative and neutral sentiment assigned to BTC tweet: https://data.world/mercal/btc-tweets-sentiment

"cleaning tweets data.py" This file removes emojis, "@" symbols and URLs from tweets, ensurng useful and interpretable information is provided to the Neural Network. Duplicate tweets were removed aswell. 

The Neural Network that trained on just 2 classes (neutral and positive) were significantly more accurate than training on 3 classes (positive, neutral and negative), moreover negative sentiment made up less than 10% of tweets in the dataset. See *Unique-Tweets.csv* for cleaned labelled dataset

### Caveats and important points
The dataset is only made up of tweets from an **hour period on a single day**, therefore model trained on this dataset may not generalise well with my dataset. I still need to test this dataset on other labelled data at different time periods to see if it generalises well

I do not fully agree with the sentiment labels, I believe some labels to be neutral when they are positive, I think for a more accurate dataset I would have to manually label data, but I am resource constrained and don't have time to manual label data. 

I removed tweets that were repeated to prevent overfitting to this dataset. See *Unique-Tweets.csv* for cleaned labelled dataset.


### Neural Network

*BTC tweet sentiment.ipynb* shows step by step methododlogy of how I trained the Neural Network. 



