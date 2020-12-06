# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Web APIs & Classification

 - [Executive Summary](#Executive-Summary)
 - [Recommendations](#Recommendations)
 - [Conclusion](#Conclusion)
 - [Data Dictionary](#Data-Dictionary)
 - [Data Sources](#Data-Sources)

---
## Executive Summary
**INTRODUCTION**

*r/pcgamingtechsupport* and *r/techsupport* are two well-frequented tech subreddits on reddit.com, where users often head to to seek advice for their tech-related problems. 

Our aim is to build a classification model that is able to classify posts into the two subreddits, and to uncover which are some of the top words/themes around each subreddit. 

Given that *r/pcgamingtechsupport* is essentially a more specialized version of *r/techsupport*, we would want to direct PC gaming users there instead, so they can obtain more personalized advice or faster responses from other PC gamers. At the same time, this allows for decluttering of *r/techsupport*, which would aid its moderators in better managing the rest of the posts.

The classification model will be scored on its accuracy, i.e. the proportion of posts that it was able to classify correctly into the two subreddits.

**METHODOLOGY**

- Datasets was scraped from each subreddit using reddit's API and the `requests` library, and loaded into pandas DataFrames.
- Data cleaning was performed to remove rows with null values in the `selftext` and `title` columns, as well as duplicate values in `selftext`. Stickied posts were also removed to reduce their influence on the model. The `selftext` and `title` columns were combined, and Regex was used to trim any special characters and hyperlinks in the combined text.
- Exploratory data analysis was carried out to investigate trends in the time range, frequency of posts and distribution of word counts. Word clouds for each subreddit were generated. Stop words were removed and lemmatization was performed.
- The data was passed into pipelines, combining `TfidfVectorizer` (used to transform the corpus of words into tf-idf vectors for modelling) and various classification algorithms (`LogisticRegression`, `MultinomialNB`, `SVC`) to yield accuracy scores on the training and test sets.
- The final production model was selected based on the best accuracy score on the test set, as well as its high degree of interpretability.

**KEY TAKEAWAYS AND FINDINGS**

The final `LogisticRegression` model yielded an accuracy of **0.866** on the training set and **0.740** on the test set, with an ROC-AUC score of **0.82**.

The themes related to each subreddit are as follows:

**r/techsupport**
- laptop
- computer
- phone
- windows 10
- tv
- router
- google
- audio
- disk
- chrome
- file
- ethernet

These terms tended to be more general, with a mix of everyday tech hardware (laptop, computer, phone, tv) as well as software terms (Windows 10).

**r/pcgamingtechsupport**
- game
- gaming
- ram
- gpu
- ryzen
- rtx
- motherboard
- 2060
- play
- headset
- card
- fan
- mobo

These terms tended to relate to graphics cards (rtx, 2060, card, gpu), processors (ryzen) and motherboards, which are frequently associated with improving computer gaming performance.

---
## Recommendations 

The `LogisticRegression` model may be used to classify posts into either *r/pcgamingtechsupport* or *r/techsupport*. This could potentially aid users who are seeking tech advice in deciding which is a more appropriate subreddit to post to, prior to submitting their posts. 

In doing so, posts which are more pertinent to PC gaming can be directed to *r/pcgamingtechsupport*, allowing the user to obtain more specific and relevant advice from other users. This also helps to declutter the *r/techsupport* subreddit as other non-gaming posts would receive greater visibility.

Ultimately, users can also choose to continue posting in the subreddit that they are more familiar with, as long as the topic is still relevant.

--- 
## Conclusion

Through a data science methodology comprising data collection, data cleaning, exploratory data analysis, modelling and model iteration, a **Logistic Regression** model was created that is able to classify posts from either *r/techsupport* or *r/pcgamingtechsupport* into their respective subreddits. This would aid users with tech issues in deciding which is a more pertinent subreddit to solicit help from, allowing quicker response times to their queries.

*r/techsupport* tended to contain posts with more general tech issues, while *r/pcgamingtechsupport* saw more posts regarding graphics cards, RAM and processor issues.

Further refinements to improve our model include:
- Do more hyperparameter tuning
- Use other NLP libraries such as spacy for POS tagging to see if there are any other trends
- Scrape more posts from each subreddit to obtain more data
- Use other features in the posts (e.g. number of upvotes, scrape comment data) 
	- *Note: mainly retroactive in nature*

--- 
## Data Dictionary


|Feature|Type|Dataset|Description|
|:-:|:-:|:-:|:--|
|**selftext**|*object*|combined.csv|The main body of the post.|
|**clean_text**|*object*|combined.csv|Pre-processed  main body and title of the post (removal of special characters, hyperlinks, stop words and lemmatization).|
|**target**|*int*|combined.csv|The subreddit which the post comes from (0 - *r/techsupport*, 1 - *r/pcgamingtechsupport*)|

---
## Data Sources
The source of the datasets used in this analysis: 
- https://www.reddit.com/r/techsupport/
- https://www.reddit.com/r/pcgamingtechsupport/