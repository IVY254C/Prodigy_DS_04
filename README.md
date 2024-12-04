# Prodigy_DS_04: Sentiment Analysis on Social Media Data

## Overview

This project conducts sentiment analysis on social media data, specifically Twitter data, to uncover public opinions and attitudes toward specific topics or brands. The dataset contains tweets labeled with sentiment (Positive or Negative), and our goal is to explore, analyze, and visualize these sentiments to gain valuable insights into public perceptions.

## Objective

The aim of this project is to apply sentiment analysis to Twitter data, clean and preprocess the dataset, perform exploratory data analysis (EDA), and visualize the results to understand how various entities or topics are perceived by the public. This process will involve identifying trends in sentiment, visualizing sentiment distributions, and highlighting specific insights.

## Dataset

The dataset consists of two CSV files: one for training and another for testing. Each CSV contains the following columns:

- **Tweet ID**: A unique identifier for each tweet.
- **Entity**: The brand, topic, or subject mentioned in the tweet.
- **Sentiment**: The sentiment classification of the tweet, either "Positive" or "Negative".
- **Tweet Content**: The actual tweet text.

## 1. Data Preprocessing

In this step, we clean and prepare the data for analysis. The preprocessing involves several key tasks to ensure the data is in a usable format for analysis:

### Dropping Duplicates

We remove any duplicate rows in the dataset to ensure we work with unique data.

```python
df = df.drop_duplicates()
```

## 2.Exploratory Data Analysis (EDA)
This phase involves analyzing the dataset to uncover trends and patterns in tweet sentiments.

 ### Sentiment Distribution
We begin by analyzing the distribution of positive and negative sentiments in the dataset.

```python
import matplotlib.pyplot as plt
import seaborn as sns
```
### Sentiment by Entity
We explore how different brands or topics are perceived by analyzing the sentiment associated with their mentions.

## 2. Visualization
Visualization plays a crucial role in understanding the results of sentiment analysis. Below are the visualizations for sentiment trends and topic analysis.

### Top 5 Topics with Positive Sentiments
This visualization shows the top 5 entities or topics that are most frequently associated with positive sentiments.

```python
positive_sentiment_df = df[df['Sentiment'] == 'Positive']
top_positive_topics = positive_sentiment_df['Entity'].value_counts().head(5)
```

### Top 5 Topics with Negative Sentiments
Similarly, this visualization highlights the top 5 entities or topics with negative sentiments.

```python
negative_sentiment_df = df[df['Sentiment'] == 'Negative']
top_negative_topics = negative_sentiment_df['Entity'].value_counts().head(5)
```
### Heatmap of Positive and Negative Sentiments
We can create a heatmap to visualize the relationship between positive and negative sentiments across different entities or topics.

```python
sentiment_matrix = pd.pivot_table(df, values='Tweet ID', index='Entity', columns='Sentiment', aggfunc='count')
sns.heatmap(sentiment_matrix, annot=True, cmap='coolwarm', fmt='d')
plt.title('Heatmap of Positive and Negative Sentiments')
plt.show()
```
## 3.Conclusion
In this project, we successfully collected and preprocessed Twitter data for sentiment analysis. By cleaning and analyzing the data, we gained insights into how public sentiment fluctuates toward different topics or brands. The visualizations provided a clear understanding of the distribution of positive and negative sentiments, and the relationship between various topics and sentiments.

The results from this analysis can be used for marketing strategies, brand monitoring, and further research in sentiment analysis in the social media space. Future work could involve using machine learning models to predict sentiments and refine the analysis with more sophisticated techniques such as natural language processing (NLP) and deep learning models.
