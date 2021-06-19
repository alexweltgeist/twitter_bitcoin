# twitter_bitcoin

ZHAW Project to analyse whether we can identify a corralation between twitter sentiments on bitcoint tweets with the bitcoin price. For that an app was built on the Databricks environement (Community Edition) using Spark Streaming. Description of the overall project can be found in the powerpoint presentation: **BitcoinPreisundTweets_v03.pptx**

The Spark Streaming app consist of 3 parts:
* The producer notebook uses a Twitter API to stream messages onto a TCP IP socket: **Twitter_Project_Producer_v06.ipynb**
* The consumer notebook uses the spark streaming context to process the messages, apply sentiment, language detection and the bitcoin price and to store the relevant aggregated and windowed data in a parquet file: **Twitter_Project_Consumer_v12.ipynb**
* The displayer notebook uses Koala to consume and normalize the prepared data and to display it in a graph: **Twitter_Project_Displayer_v03.ipynb** 

Additionally we trained an own CNN as an alternative to the Textblob sentiment analysis. This also consist of 3 parts:
* The code to produce training data (configured for batches of 10'000): ** ** 

