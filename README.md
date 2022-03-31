# Scraping Twitter Data and Perform Sentiment Analysis
To be updated...

Basic setup to get data from twitter with a keyword.

* A crawler that crawls the latest 200 tweets from a certain hashtag or username
* Word Cloud of lastest tweet

## Prerequisite to use
### Libraries
Use "pip install --" command to install the following libraries:

```
pandas
tweepy
sqlalchemy
datetime
OS
textblob
NLTK
itertools
collections
wordcloud
numpy
Matplotlib
PIL
```
### Twitter Authorisation
Get Twitter api key + secret, access token key + secret from (https://dev.twitter.com/oauth/overview/application-owner-access-tokens) and fill in the corresponding variables and save as `twitter-keys.env` local file.
```
consumer_key = "XXXXXX"
consumer_secret = "XXXXXX"
access_token = "XXXXX"
access_token_secret = "XXXXX
```
### SQL Authorisation
pgAdmin 4 v6 PostgreSQL is used to store tweets in this project.

You will need to insert your database connection parameters and save as `sql-keys.env` local file.

```
dbUser = "XXXXX"
dbPwd = "XXXXX" 
dbHost = "XXXXX"
dbPort = XXXXX
dbName = "XXXXX"
```
The following is the list of the connection parameters:
- *dbUser*: the username used to authenticate.
- *dbPwd*: password used to authenticate.
- *dbHost*: database server address e.g., localhost or an IP address.
- *dbPort*: the port number that defaults to 5432 if it is not provided.
- *dbName*: the name of the database that you want to connect.

To be updated...
