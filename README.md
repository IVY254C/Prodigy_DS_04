# Prodigy_DS_04

# Sentiment Analysis on Social Media Data

This project performs sentiment analysis on social media data (Twitter data in this case) to understand public opinion and attitudes toward specific topics or brands. The dataset contains tweets along with their associated sentiment (Positive, Negative), and the goal is to explore and visualize these sentiments.

## Table of Contents
1. [Introduction](#introduction)
2. [Data Collection](#data-collection)
3. [Data Preprocessing](#data-preprocessing)
    - [1. Lowercasing the Text](#1-lowercasing-the-text)
    - [2. Removing Punctuation](#2-removing-punctuation)
    - [3. Removing Stop Words](#3-removing-stop-words)
    - [4. Tokenization](#4-tokenization)
    - [5. Lemmatization](#5-lemmatization)
    - [6. Dropping Duplicates](#6-dropping-duplicates)
4. [Exploratory Data Analysis](#exploratory-data-analysis)
5. [Visualization](#visualization)
    - [1. Top 5 Topics with Positive Sentiments](#1-top-5-topics-with-positive-sentiments)
    - [2. Top 5 Topics with Negative Sentiments](#2-top-5-topics-with-negative-sentiments)
    - [3. Heatmap of Positive and Negative Sentiments](#3-heatmap-of-positive-and-negative-sentiments)
6. [Conclusion](#conclusion)

## Introduction

This project uses **Sentiment Analysis** to determine the public sentiment towards various topics or brands discussed on Twitter. We will clean and preprocess the dataset, analyze the sentiment, and then visualize the results using various techniques such as bar charts and heatmaps.

## Data Collection

- **Social Media APIs**: The data was collected from Twitter using the Twitter API, specifically filtering tweets based on hashtags and keywords.
- **CSV Files**: We have two CSV files: one for training and another for testing, containing the following columns:
    - **Tweet ID**: Unique identifier for each tweet.
    - **Entity**: The brand or topic mentioned in the tweet.
    - **Sentiment**: The sentiment of the tweet, either Positive or Negative.
    - **Tweet Content**: The actual tweet text.

## Data Preprocessing

In this step, we clean and prepare the data for analysis. This includes several sub-steps:

### 1. Lowercasing the Text
We convert all the tweet text to lowercase to standardize the data and make the analysis case-insensitive.

```python
# Convert text to lowercase
twitter_training['lowercase'] = twitter_training['Tweet Content'].apply(lambda x: ''.join(word.lower() for word in x.split()))
