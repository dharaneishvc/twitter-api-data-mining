# Mining of Twitter API dataset

## Introduction
Twitter is a microblogging platform where millions of users share their opinions, thoughts, and ideas on various topics. The Twitter API provides access to this vast pool of data, allowing developers to analyze and extract valuable insights from it. This project aims to explore different mining techniques on Twitter data using the Twitter API.

## Problem Statement
The goal of this project is to analyze Twitter data to identify sentiment, recommend users to follow, find frequent item sets, identify influential users, filter data streams, detect communities, and identify popular topics. These insights can be used for various applications, such as marketing, brand management, opinion mining, and trend analysis.

### Sub-Problems
* Sentiment Analysis: Collect a large dataset of tweets and then perform sentiment analysis on the text using TF-IDF. This can help you identify the most commonly used words or phrases that people use when expressing positive or negative sentiment about a particular topic or brand.
* Recommendation System: Create a recommendation system that suggests Twitter users to follow based on their interests and the interests of other users they follow. This can be done using clustering algorithms to group similar users together and then recommending new users to follow based on those clusters.
* Trend Analysis: Use the Twitter API to collect a dataset of hashtags and then use the Apriori algorithm to identify frequent item sets of hashtags that are often used together. This can help identify Trends in tweets and marketing strategy. 
* Identify influential users: Use the Twitter API to create a graph of Twitter users and their followers. Then, use the PageRank algorithm to identify influential users on the platform. This can help identify popular accounts that are often retweeted or mentioned by other users.
* Identifying popular topics: Using MapReduce, you can count the frequency of each word in the tweet dataset and identify the most commonly used words. This can help identify popular topics or trends in the dataset.
*	Spam and Bot Detection: Use the Twitter API to collect a stream of real-time tweets and then filter out irrelevant or spammy tweets using a Bloom filter or machine learning classifier. This can help clean up noisy data streams and make it easier to extract meaningful insights from Twitter data.
*	Community Detection: Use the Twitter API to create a graph of users and their interactions (e.g. mentions, retweets, replies) and then use community detection algorithms to identify groups of users that are tightly connected. This can help identify sub-communities within a larger network and provide insights into the interests and behaviors of different user groups.

## How to collect the Twitter API dataset of tweets using the TwitterAPI:
1.	Sign up for a Twitter Developer account at https://developer.twitter.com/en/apply-for-access
2.	Create a new Twitter app and obtain your API keys and access tokens.
3.	Install the TwitterAPI library using pip or your preferred package manager.
4.	Use the TwitterAPI library to connect to the Twitter API and set up a stream to collect real-time tweets or search for historical tweets.
Here's some sample Python code to collect tweets in real-time using the TwitterAPI library:

```
from TwitterAPI import TwitterAPI

# Replace the placeholders with your own API keys and access tokens
consumer_key = 'your_consumer_key'
consumer_secret = 'your_consumer_secret'
access_token_key = 'your_access_token_key'
access_token_secret = 'your_access_token_secret'

# Set up a TwitterAPI instance with your credentials
api = TwitterAPI(consumer_key, consumer_secret, access_token_key, access_token_secret)

# Set up a stream to collect real-time tweets containing the word "Python"
stream = api.request('statuses/filter', {'track': 'Python'})

# Iterate through the stream and print each tweet
for tweet in stream:
    print(tweet)
```

This code sets up a stream to collect real-time tweets containing the word "Python" and prints each tweet to the console. Modify the track parameter to search for tweets containing other keywords or hashtags.
Also use the TwitterAPI to search for historical tweets by specifying a date range and other search parameters. 

Here's some sample Python code to search for tweets containing the word "Python" posted between January 1, 2022, and January 31, 2022:
```
from TwitterAPI import TwitterAPI

# Replace the placeholders with your own API keys and access tokens
consumer_key = 'your_consumer_key'
consumer_secret = 'your_consumer_secret'
access_token_key = 'your_access_token_key'
access_token_secret = 'your_access_token_secret'

# Set up a TwitterAPI instance with your credentials
api = TwitterAPI(consumer_key, consumer_secret, access_token_key, access_token_secret)

# Set up a search query to find tweets containing the word "Python" posted between January 1, 2022, and January 31, 2022
query = {
    'q': 'Python',
    'count': 100,
    'lang': 'en',
    'result_type': 'recent',
    'since_id': '20220101000000',
    'until_id': '20220131000000'
}

# Search for tweets using the query and print each tweet
r = api.request('search/tweets', query)
for tweet in r:
    print(tweet)
    
```

This code searches for tweets containing the word "Python" posted between January 1, 2022, and January 31, 2022, and prints each tweet to the console. You can modify the query parameters to search for tweets containing other keywords or hashtags and adjust the date range to search for tweets posted during a different time period.
After Collecting, Preprocess the tweet text by removing stop words, hashtags, mentions, URLs, and other non-essential information using natural language processing techniques.


