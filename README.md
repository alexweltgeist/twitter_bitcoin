# twitter_bitcoin

ZHAW Project to analyse whether we can display a connection between twitter sentiments on bitcoint tweets with the bitcoin price. For that an app was built on the Databricks environement (Community Edition) using Spark Streaming. Description of the overall project can be found in the powerpoint presentation: [**BitcoinPreisundTweets_v03.pptx**]  (https://github.com/alexweltgeist/twitter_bitcoin/blob/main/BitcoinPreisundTweets_v03.pptx)

The Spark Streaming app consist of 3 parts:
* The producer notebook uses a Twitter API to stream messages onto a TCP IP socket: **Twitter_Project_Producer_v06.ipynb**
* The consumer notebook uses the spark streaming context to process the messages, apply sentiment, language detection and the bitcoin price and to store the relevant aggregated and windowed data in a parquet file: **Twitter_Project_Consumer_v12.ipynb**
* The displayer notebook uses Koala to consume and normalize the prepared data and to display it in a graph: **Twitter_Project_Displayer_v03.ipynb** 

Additionally we trained an own CNN as an alternative to the Textblob sentiment analysis. This exercise is done on Google Colab and also consist of 3 parts:
* The first part contains the code to produce training data based on Textplob Sentiment: **Create_Trainingset_v03.ipynb** 
* The second file is the training set with the labled Tweets: **all_tweets_with_lable_final.csv**
* And the third part finally contains the CNN model and the evaluation thereof: **Sentiment_Analysis_with_CNN_v04.ipynb** 

Note: there are still things not working as desired. 
* Saving the stream of aggregated windows in parquet is still an issue
* the bitcoint price only updates continuously when not using aggregated windows
* CNN performance is still biased (many false negatives), the version **Sentiment_Analysis_with_CNN_v05.ipynb** is adding more training data but still needs more adjustments (do not use, yet!)


