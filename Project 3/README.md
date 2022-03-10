# Project 3 - Part 1 Web Scraping
by: Nah Wei Jie

## Overview
![images.png](../images/images.png)

FairPrice's [**Share-A-Textbook**](https://www.fairprice.com.sg/wps/portal/fp/csr/SAT/FAQ) (formerly known as FairPrice Used Textbooks Project) is NTUC FairPrice’s signature community project that is held annually.
First started in 1983 as the Used Textbooks Project, the project collects pre-loved textbooks and distributes them for free to needy students. The project was rebranded as FairPrice Share-A-Textbook in 2010.   

The objectives of the project is to:
1. Relieve the financial burden of families by providing free pre-loved textbooks 
2. Encourage the value of thrift
3. Promote a greener Singapore through recycling of pre-loved textbooks.

Since its inception, more than 5.5 million textbooks were collected to help over 280,000 students save on textbooks expenses. 

The project consists of: (a) Donation period and (b) Distribution period.  
#### Donation Period  
Annually, members of the public donate their pre-loved textbooks for the project at: 
- 77 FairPrice stores island wide, including Warehouse Club, FairPrice Xtra hypermarkets, FairPrice Finest stores, selected FairPrice supermarkets, and FairPrice Xpress stores at Esso service stations.  
The donation period will usually last a month before or during the major school holidays at the end of the year
. All books collected will be sent for sorting before distribution.

All textbooks in usable condition (i.e. no torn / missing pages and no scribbling) that are in the current syllabus are welcome.   
[**Click for list of books in current syllabus**](https://www.moe.gov.sg/education/syllabuses/approvedtextbook-list)

Aside from textbooks, story books and literary novels are also welcome. They will be sorted under the ‘Others’ category for collection.

Being a community project, it is fully ran and organised by a small group of full time planners and volunteers who sign up with us to participate. Volunteers typically support this project over three phases.

Before distribution, collected books go through a three step process aided by a small group of full-time coordinators and volunteers to sort/categorise donated books.

**1. Sorting**   
1. Sort through donated books and categorise them into various academic levels and subjects  
2. Filtering of books to ensure that donated books are in line with current syllabus and in good condition  
3. Ensure that recipients are able to obtain relevant titles to meet their needs more accurately
**2. Set-up**
- Wagons layout, queue management, stocking of wagons with books

**3. Distribution**
- Queue management, replenishment of books, sanitising collection zones and assisting recipients with book search

Receiving overwhelming support in recent years with donations and volunteers reaching all time highs, it has become increasingly difficult to scale the project given the duration to accomplish the project has remained the same or shortened as a result of Covid-19 while running the project.

One of the main bottlenecks identified by the project manager is the sorting phase which tend to take up bulk of the time. With increasing number of books donated and volunteers, the proportion of books which are incorrectly sorted/categorised is increasing as most volunteers are fairly new (first time volunteers) to these processes and definitions of books belonging to different categories might vary between staffs and volunteers.

## Business Problem

With these concerns surfaced as a planner in the same team with an analytics background, you are tasked to explore ways to alleviate these pain points and present your findings to your colleagues and small group of staff from NLB who serves as subject matter experts (peer reviewers) also interested in contributing to this project.

## Data Science problem/ Problem Statement

To create a text classification model to determine whether reddit posts(Proxy for book excerpts) belong to either of these two subreddits "FanFiction" (proxy for 'other' category) or "LifeAdvice" (proxy for 'textbooks'). We will be measuring the success of our classifier model by looking at several metrics, including accuracy, specificity, sensitivity and model scores. With the model we will also want to explore how the model can be generalized to solve our business problem.

## Executive Summary

To alleviate mentioned pain points, we explored scraping posts from Reddit to serve as proxies of book excerpts, given our problem statement we sought to build a model which was able to determine which subreddit a given post came from and leverage on our findings to be able to use our model to eventually categorise donated books on whether they are 'textbooks' or 'others'.

Analyses relating to excerpts were of utmost importance to us as they give us a gauge on how they can help our business problems.  

![image2.png](../images/image2.png)
From our analysis, the LifeAdvice subreddit tend to have longer character lengths and word counts in its posts with higher medians for both of them in a right-skewed distribution.

![image3.png](../images/image3.png)
 The most common words ```just```,```like```,```don```,```really``` and ```know``` appear in both subreddits, there are also differentiating words which appear in one but not the other:
- FanFiction:   ```Writing```, ```Character```, ```Story```
- LifeAdvice:   ```Job```, ```Work```, ```Time```
Bigrams were also similar across subreddits, with ```feel like```, ```don know``` and ```don want``` appearing in both subreddits. There were also differentiating bigrams.

- FanFiction:   ```harry potter```, ```main character ```, ```word count```
- LifeAdvice:   ```mental health```, ```high school```, ```year old```  

We also observed that there is an imbalance of the most frequent words, which we tried to balance using `TF-IDF` vectorization.

![image4.png](../images/image4.png)

**Modelling (Classification Model)**

To process our posts for modelling, we removed punctuation, numbers, commonly used words (stopwords) and lemmatized our words as we are interested in the meaning of the words after analysis, we chose to lemmatize them as stemming tend to strip words of their meaning.

There are a few libraries that we can choose to perfom pre-processing. In particular, we considered both the [```Spacy```](https://spacy.io/) and [```NLTK```](https://www.nltk.org/) libraries. 

The ```Spacy```( library stopwords list has more stopwords compared to ```NLTK```, we decided to go with the Spacy stopwords instead and included additional words identified during EDA to be included.

To decide which library to leverage on for lemmatization, we timed the performance of both ```Spacy``` and ```Wordnet``` in lemmatization. We have selected ```Spacy``` as it was twice as fast.

After performing train test split, we ran our training data through 4 sets of pipelines which used `TF-IDF` vectorization coupled with a model. Models used for training were `Logistic Regression`, `Multinomial Naive Bayes`, `K-Nearest Neighbours` as well as `Random Forest Classifier`.   
![image5.png](../images/image5.png)
As we are most interested in the decreasing the number of false negatives of our classifier in predicting the subreddit a given post belongs to, we want to look at the models that have high sensitivity scores (`Multinomial Naive Bayes`). 

![image6.png](../images/image6.png)

Another benefit of selecting the `Multinomial Naive Bayes` model allows us to iterate in a more intuitive manner as we are able to see the impact of each feature (words) as it specifies coefficients to each word, and use such analyses to further improve our model. 
  
Optimize for `sensitivity` by analysing our co-efficients helped us further increase its test score as well as `sensitivity`, relating to our business problem such a model would be able to, by nature of reducing incorrectly categorised books and increasing the number of correctly categorised books.


**Conclusion/Recommendations**

Looking back at our problem statement and business problem, we managed to come up with a text classification model to determine whether reddit posts(Proxy for book excerpts) belong to either of these two subreddits "FanFiction" (proxy for 'other' category) or "LifeAdvice" (proxy for 'textbooks'). Measuring the success of our classifier model by looking specificity and plotting our coefficients we managed get a model that is also interpretable.  

With a good classifier, we would be able to free up manpower and re-allocate them to assist other phases of the annual project, ultimately benefitting these primary and secondary stakeholders:

**Primary stakeholders**  
Recipients of donated books (Financial burden, inculcating a value of thrift)

**Secondary stakeholers**  
Environment (More books recycled)  
Volunteers (Increased satisfaction for volunteering --> More inclined to volunteer in future)

**Limitations**:  

- For the purposes of this project, we managed to collect a balanced dataset, keeping in mind our problem statement, there is a very high chance that new data (documents/books/text) will not be balanced.  

As we have no control over what categories the books will be donated, a production model might need to be able to better handle imbalanced data  or be unaffected by imbalanced data.

With a long history of running this project, we might be able to refer to older datasets or have external datasets which are objective (PSSST NLB :)) to serve as a better dataset for model training.

- As we only scraped approximately 1000 posts per subreddit, I believe our model could be more accurate if we increase the number of posts in our training dataset so that the model can learn more through existing data.



## Data Dictionary


|Feature|Data Type|Description|
|-------|---------|-----------|
|selftext|str|Post body|
|title|str|Post title|
|id|str|Unique id of post|
|subreddit|str|Name of subreddit|
|author|str|Author name|
|score|int|Total post score|
|upvote_ratio|float|Ratio of upvote of all upvotes and downvotes|
|total_awards_received|int|Total number of awards|
|num_comments|int|number of comments|
|permalink|str|URL to post|
|created_utc|timestamp|Timestamp UTC|
|subreddit_cat|int|Mapped category for subreddits (1: LifeAdvice, 0: FanFiction)|
|timestamp|datetime-object|Timestamp for US EST|
|day_posted|datetime-object|Date posted|
|month_posted|int|Month posted|
|weekday_posted|int|Day of the week mosted (starts at 0 for Monday)|
|hour_posted|int|Hour posted|
|all_text|str|Combined title and post body text|
|wordcount_all_text|int|Number of words in all text|
|length_all_text|int|Chareacter Length in all text|
|all_text_cleaned|str|Processed text for model|









----
