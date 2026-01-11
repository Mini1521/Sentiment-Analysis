# Sentiment-Analysis : Social Media Influence on Stock Market Prediction

## Project Overview:
This project investigates the influence of ublic sentiment extracted from social media (Twitter) and financial nws articles on stock price movements of Microsoft and Tesla. The study applies traditional machine learning and deep learning techniques to perform sentiment classification and integrates sentiment signals with historical stock data to predic stock prices using LSTM models.

The project forms parts of an undergraduate dissertation in Computer Science (Data Science) and aims to evaluate whether sentiment-driven features can improve financial forecasting performance.

## Research Motivation:
Financial markets are increasingly influenced by real-time public opinion shared through social media platforms and onlince news resources. While previous studies often focus on a single sentiment source, this project addresses a research gap by combining both tweet-based and news-based sentiment with technical stock indicators to assess their collective impact on stock pricw preddiction.

## Dataset Used:
1. **STOCK MARKET DATASET:** 
https://www.kaggle.com/datasets/omermetinn/values-of-top-nasdaq-copanies-from-2010-to-2020
2. **TWEETS DATASET:**
https://www.kaggle.com/datasets/omermetinn/tweets-about-the-top-companies-from-2015-to-2020/data
3. **NEWS ARTICLES DATASET:**
https://www.kaggle.com/datasets/journeyyouyeonkim/microsoft-tesla-finance-news-articles2020-2024?select=tsla_articles.csv

## Methodology:
### Text Preprocessing:
Text data from tweets and news articles was cleaned using standard NLP techniques, including noise removal, tokenization, and lemmatization. For traditional ML models, texts was converted into numerical features using TF-IDF vectorization, while sequence-based representations were used for DL models.

### Feature Engineering
Financial features such as 5-day and 10-day movinng averages and price volatility indicators were derived from historical stock prices. These technical indicators were combined with sentiment features to form the final input for prediction models.

### Sentiment Classification
Sentiment classification was performed using:
- Traditional ML models: Naive Bayes, SVM, Decision Tree, Random Forest.
- Deep Learnign models: ANN, LSTM

### Stock Price Prediction
LSTM models were trained using combined sentiment and financial features to predict stock closing prices. Model performance was elevated using MAE, RMSE, and R<sup>2</sup> score. 

## Results:
### Sentiment Classification Performance:
LSTM models consistently outperformed traditonal ML approached due to theri ability to capture contextual and sequential patterns in text.
- Microsoft Tweets: 90% accuracy
- Microsoft News: 59% accuracy
- Tesla Tweets: 89% accuracy
- Tesla News: 58% accuracy
Tweet-based sentimetn achived higher accuracy that news sentiment, indication the stronger real-time influence of social media.

### Stock Price Prediction Performce (LSTM)
- Microsoft:
- _ R<sup>2</sup> = 0.9996
  _ RMSE = 0.0046
- Tesla:
  _ R<sup>2</sup> = 0.9384
  _ RMSE = 0.0533
Predictions using tweet-based sentiment consistently produced lower error rates that those using news-based sentiments.
