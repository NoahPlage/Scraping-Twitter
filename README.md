# Scraping Twitter Data and Perform Sentiment Analysis
### Situation
> “AP Photos: 1 Month: War in Ukraine Rages on; 3m Have Fled.” AP NEWS, The Associated Press, 23 Mar. 2022, https://apnews.com/article/russia-ukraine-putin-zelenskyy-europe-5095691ab6a2c0b12874aa4fa30e23cf. 

### Brief
Due to Russia’s unprovoked and unjustified war on Ukraine, media outlets have harsh and strong words on Russia. 

### Objective
We are using social media (Twitter) to understand the public’s sentiments of the war through: 
- Collecting Twitter data
- Developing data crawler
- Storing crawled data
- Performing sentiment analysis

## Table of Contents
- [Prerequisite to use](#prerequisite-to-use)
  - [Libraries](#libraries)
  - [Required files](#required-files)
  - [Twitter authorisation](#twitter-authorisation)
  - [SQL authorisation](#sql-authorisation)
- [Database Schema](#database-schema)
- [Contributers](#contributers)

## Prerequisite to use
### Libraries
Use "pip install --" command to install the following libraries:

```
pandas
tweepy
sqlalchemy
textblob
NLTK
wordcloud
numpy
Matplotlib
PIL
```
### Required file(s)
- Download `ukraine_map.png` into local folder as it will be used to Word Cloud analysis.
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

# Database Schema
The scraped data will be loaded and stored in a PostGreSQL database table:

**twitterDatabase:**
- Tweet ID
- Username
- User's display name
- User's location
- User's followers count
- User's follow count
- User's tweet
- Hashtags in user's tweet
- Tweet's polarity
- Tweet's subjectivity

# Contributers

- [Angela]https://www.linkedin.com/in/angela-p-171b30136/)
- [Brandon](https://www.linkedin.com/in/jinheng-lim/)
- [Mavis](https://www.linkedin.com/in/mavis-luo-3a5b76192/)
- [Soon Chye](https://www.linkedin.com/in/lim-soonchye/)
