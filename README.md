# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Data Science Projects
This repository showcases the projects that were done as part of my Data Science Immersive course at General Assembly. These entailed the various steps of the Data Science process, including: 
- Defining the business and data science problems
- Data collection
- Data exploration and visualization
- Modelling and evaluation
- Translating insights from data into solving the business problem
---

 - [Project 1: SAT Score Analysis](#Project-1:-SAT-Score-Analysis)
 - [Project 2: Ames Housing Price Prediction Model](#Project-2:-Ames-Housing-Price-Prediction-Model)
 - [Project 3: r/techsupport and r/pctechsupport subreddit classification](#Project-3:-r/techsupport-and-r/pctechsupport-subreddit-classification)
 - [Project 4: West Nile Virus Prediction in the City of Chicago](#Project-4:-West-Nile-Virus-Prediction-in-the-City-of-Chicago)
 - [Capstone: Sentiment Analysis and Topic Modelling of Steam game reviews](#Capstone:-Sentiment-Analysis-and-Topic-Modelling-of-Steam-game-reviews)

---
## Project 1: SAT Score Analysis
[(project Github page)](https://github.com/paralit-gh/dsiprojects/tree/main/project_1)

The new format for the SAT was released in March 2016. The ACT, which is the alternative standardized test used for college admissions, has been steadily gaining popularity as the test of choice amongst students in recent years. 

This project focused on data exploration and visualizations (histograms, scatter plots, box plots and bar plots) to investigate the changes in statewide SAT test participation rates and the factors influencing them, and to identify recommendations that could be taken by the College Board to boost SAT participation rates in the years ahead. 

---
## Project 2: Ames Housing Price Prediction Model

[(project Github page)](https://github.com/paralit-gh/dsiprojects/tree/main/project_2)

When it comes to buying and selling a house, homeseekers and homeowners alike are typically most concerned about one factor - that is, the price of the house. However, as houses come in all shapes and sizes, with a myriad of customizable options catering to individual preferences - such as the number of bedrooms; the size of the garage; or even the quality of the fireplace - it is difficult to perform an accurate valuation of a property.

This project made use of the Ames, Iowa housing dataset, which contained sale prices of residential properties from 2006 to 2010, in order to develop a price prediction model for homeseekers and homeowners to be able to estimate the sale value of their properties, allowing them to make better informed decisions.  Additionally, we investigated the specific features of a property that had a strong effect on the sale price, allowing home owners to strategically up-value and market their properties.

---
## Project 3: r/techsupport and r/pctechsupport subreddit classification

[(project Github page)](https://github.com/paralit-gh/dsiprojects/tree/main/project_3)

_r/pcgamingtechsupport_ and _r/techsupport_ are two well-frequented tech subreddits on reddit.com, where users often head to to seek advice for their tech-related problems. 

Given that  _r/pcgamingtechsupport_  is essentially a more specialized version of  _r/techsupport_, we would want to direct PC gaming users there instead, so they can obtain more personalized advice or faster responses from other PC gamers. At the same time, this allows for decluttering of  _r/techsupport_, which would aid its moderators in better managing the rest of the posts.

Using Natural Language Processing (NLP) techniques such as text cleaning using Regex, tokenization and lemmatization, a classification model was built to classify posts into the two subreddits, and to uncover which are some of the top words/themes around each subreddit.



---
## Project 4: West Nile Virus Prediction in the City of Chicago
[(project Github page)](https://github.com/paralit-gh/dsiprojects/tree/main/project_4)

West Nile Virus (WNV) is the leading cause of mosquito-borne disease in the continental United States. It is most commonly spread to people by the bite of an infected mosquito after it has fed off an infected bird. 1 in 5 people who are infected develop a fever and other symptoms. In more severe cases, about 1 out of 150 infected people develop a serious, and sometimes even fatal illness. Due to previous outbreaks occurring in Chicago in 2002, by 2004, the Chicago Department of Public Health (CDPH) had set up a comprehensive surveillance and control system, trapping mosquitos to be tested for the presence of WNV.

In this project, we built a fully predictive classification model to be used for proactive mosquito management, predicting whether WNV-positive mosquitoes would be found in a particular trap. A cost benefit analysis was also conducted to ascertain the overall benefit of spraying as a form of vector control, through calculating the annual cost projections for various levels of pesticide coverage and the effect of these various levels of pesticide coverage. Various datasets were fused together and feature engineering performed to improve the performance of our boosting models.

---
## Capstone: Sentiment Analysis and Topic Modelling of Steam game reviews
[(project Github page)](https://github.com/paralit-gh/dsiprojects/tree/main/capstone)

The video game market is a highly competitive one, and video gamers are often spoilt for choice as developers and publishers alike compete intensely to create and publish the next big hit. To help better discern the sentiment of users' reviews, so as to increase sales revenue and decrease the churn rate, 
- A classification model was built to predict if a particular game review was a _positive_ or _negative_ one
	-  A variety of models were used, including Logistic Regression, Naive Bayes, LSTM neural network
	-   The top predictive text features to determine if a review is  _positive_  or  _negative_ were investigated
- Topic modelling of the various reviews was performed using Latent Dirichlet Allocation (LDA), segregated by their actual sentiment
	-   _Positive reviews_  - understand what people enjoy, to release future content/expansions for existing games or develop new games that recreate these aspects
	-   _Negative reviews_  - understand what aspects to improve on, release patches/bug fixes to address these issues in order for player retention
	-   Topic classification of reviews to find out their dominant topic

This project involved various stages of the data science methodology, including data collection, extensive data cleaning and data preparation, modelling, and sifting out insights that could be used for the stakeholders to make data-driven decisions.
