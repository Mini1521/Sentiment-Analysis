# REPORT-1 
### Preprocessing and Cleaning Datasets
First, we are preprocessing the data for stock market. We are creating a new csv file which has merged the company names to its shortform which is being used in the dataset. 
Now _“merged_data.csv”_, we convert the column _‘day_date’_ to a proper datetime format and filter out the year 2020 from it. Also filter and separate out data for companies like Microsoft (MSFT) and Tesla (TSLA), and drop rows with missing values. This is then saved as two separate .csv files: _“msft_2020.csv”_ and_ “tsla_2020.csv”_.


Next, we preprocessing the social media tweets dataset.
Again we start by merging the companies with tweets dataset. Then converting _‘post_date’_ column to a proper datetime format. The tweets are then filtered out based on the year being 2020 and companies being Microsoft (MSFT) and Tesla (TSLA). These are then saved into separate .csv files: _“msft_tweets_2020.csv”_  and _“tsla_tweets_2020.csv”_ .

Now we clean the text/posts uploaded by users in both  _“msft_tweets_2020.csv”_  and _“tsla_tweets_2020.csv”_. After loading the datasets, renaming some of the columns for easy access, any duplicate or missing values is dropped/removed. After this, text preprocessing is done, wherein the text is converted to lowercase, URL’s removed, mentions and hashtags are removed, numbers are removed. But at the same time it keeps some of the punctuations and tokenizes the text. This cleaned data is then saved as _“cleaned_msft_tweets.csv”_ and_ “cleaned_tsla_tweets.csv”_ .

Now we move on the preprocessing and cleaning the news articles dataset. 
The process is the same for both the Microsoft and Tesla news articles. 
First, we load the dataset and then convert the _“date”_ column to a proper datetime format. Then we filter out the year 2020 and drop rows with missing values. Then the text preprocessing function applies, wherein the text is converted to lowercase, removes URLs, removes mentions and hashtags, removes punctuations, removes numbers and removes extra spaces. This cleaned dataset is then saved as _“cleaned_msft_articles.csv” _and _“cleaned_tsla_articles.csv”_. 


### Sentiment analysis 
Again the process remains same for both Microsoft and Tesla. First we load the cleaned datasets. We start with sentiment analysis of tweets using VADER. and then do the sentiment analysis for news articles using TextBlob. This data is then stored into new .csv files : _“sentiment_msft_tweets.csv”_ ,  _“sentiment_msft_articles.csv” _, _“sentiment_tsla_tweets.csv”_ and _“sentiment_tsla_articles.csv”_

# REPORT -2 
### Using Traditional ML methods for Sentiment Analysis - Microsoft
Here we are training models like _Naive Bayes, SVM , Decision Tree and Random Forest Classifier_, to see which is best suited for sentiment analysis. Upon implementing the code, we see that **SVM** is the best model with _89%_ accuracy, followed by **Random Forest** with _85% _accuracy for tweets sentiment classification. For news sentiment classification,** Naive Bayes** and **SVM** both have an _accuracy of 60%_. 


### Using Traditional ML methods for Sentiment Analysis - Tesla
Again same code is applied for Tesla aswell.  Upon implementing the code, we see that SVM is the best model with 82% accuracy, followed by Random Forest with 79% accuracy for tweets sentiment classification. For news sentiment classification, **Naive Bayes** with and _accuracy of 58%_ and both **SVM** and **Random Forest** have an _accuracy of 55%_.


### Merging the datasets
When trying to merge all the datasets based on the common column _"date"_ a lot of the tweets were getting repeated for when there were multiple articles for the same day. Because of which I decided it was best to create two separate files. One which merges the stock data with tweets , and the other which merges the stock data with news articles. <ins> This is applied separately for Microsoft and Tesla. </ins>

### Stock Data Analysis
Feature for close_value of stock is created. The 5-day and 10-day moving averages of the close_value is calculated using the _rolling(window) function_. Volatility is computed and the standard deviation of the % changes in the close_value of the past 5 days. This data is then saved under _"MSFT_FEATURED_TWEETS.csv" and so on._
These newly saved .csv files are loaded and compiled and trained using LSTM models, which is later on saved. As we look through the output, we can see that over the rounds it makes training, the loss time decreases. Hence proving that it is learning and improving. This done for the both the tweets and news articles.


### Visualization
Graph showing the predictions vs Actual for Tweet Sentiment Model and Predictions vs Actual for News Sentiment Model. The more it is overlapping, the more accurate it is.


# REPORT - 3
### Using LSTM for Sentiment Analysis - Microsoft 
It loads the datasets and tokenizes it. Then two LSTM-based neural networks 
are built to classify sentiments into 3 categories for both the tweets and the news articles. Both LSTM-models are trained on the respective datasets using train-test split and validates them. Both models are evaluated using classification reports and confusion matrices.
_RESULTS_: 
For Tweets sentiment model, training performance achieved 90% accuracy.Model works well on neutral and positive tweets. While for News sentiment model, training performance achieved 59% accuracy. Positive class works well. 

### Using LSTM for Sentiment Analysis - Tesla
The same code is used for evaluating the datasets under Tesla. 
_RESULTS_: 
For Tweets sentiment model, training performance achieved 89% accuracy.Model works well on neutral tweets. While for News sentiment model, training performance achieved 58% accuracy. Neutral class works well with a score of F1-score.
