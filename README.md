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
- [Analysis Results](#analysis-results)
  - [Words Frequency](#words-frequency)
  - [Word Cloud](#word-cloud)
  - [Sentiment Analysis](#sentiment-analysis)
- [Challenges](#challenges)
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

# Analysis Results
Here we showcase some of our data visualisations.

## Words Frequency
<img src="https://user-images.githubusercontent.com/102339940/161910738-447b9973-e1bd-445d-a307-fdd644ba69b4.png" width=65% height=65%>

## Word Cloud
![MicrosoftTeams-image](https://user-images.githubusercontent.com/102339940/161911640-06346350-39b0-4400-8626-0e0024b14368.png)

## Sentiment Analysis
<img src="https://user-images.githubusercontent.com/102339940/161911805-55c0dfc7-bc89-4c29-8bb5-f41096450395.png" width=35% height=35%>

# Challenges

### Sentiment Analysis is difficult

- **False Negative Data** - The tweet below is a **positive statement** but polarity shows negative.
```
Tweet ID:1508339978610393089
Username:GPCinEnglish
Display Name:Garry Patrick Cooke
Location:
Follower Count:83
Following Count:598
Tweet Text:A wartime leader who orders the unjustifiable destruction of homes and hospitals, shops and schools, factories and libraries, etc., commits war crimes.  Therefore, such a leader is a war criminal.  #StandWithUkraine
Hashtags Used:['StandWithUkraine']
Polarity:-0.2
Subjectivity:0.53
```

- **Inaccuracy** - Below is another tweet that has **strong** comment but polarity and subjectivity is calculated as ZERO.
```
Tweet ID:1508334256107438083 
Username:J_arnd_75 
Display Name:_J.nex 🇺🇦💪 
Location: 
Follower Count:9 
Following Count:116 
Tweet Text:Invaders must die! #StopRussia #StopRussianAgression https://t.co/6kaj4GA9Kh 
Hashtags Used:['StopRussia', 'StopRussianAgression'] 
Polarity:0.0 
Subjectivity:0.0
```
### Limitations
  -  Twitter API not able to pull data that are more than 7 days
  -  Analysis and charts can varies widely due to the dynamic data

# Contributers
Hello World!

- [Angela](https://www.linkedin.com/in/angela-p-171b30136/)
- [Brandon](https://www.linkedin.com/in/jinheng-lim/)
- [Mavis](https://www.linkedin.com/in/mavis-luo-3a5b76192/)
- [Soon Chye](https://www.linkedin.com/in/lim-soonchye/)
