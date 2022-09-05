# Executive Summary
 ### Scenario
- You're fresh out of your Data Science bootcamp and looking to break through in the world of freelance data journalism. Nate Silver and co. at FiveThirtyEight have agreed to hear your pitch for a story in two weeks!
- Your piece is going to be on how to create a Reddit post that will get the most engagement from Reddit users. Because this is FiveThirtyEight, you're going to have to get data and analyze it in order to make a compelling narrative.

- As you are well aware trying to make a hot post with the right characterisitcs on reddit is difficult with so many factors yet just for a simple post, If only there was a way to gather data and predict a potential hot post to make.

- Oh! Luckily I so happened to have the solution. An api scraper that feeds data from reddit into a few machine learning models I created that predict important key words and subreddits that are in trending hot posts! 

- If interested I explain the steps how I made my hot post predicting models down below in Project Summary.

- The models show promise with the data collected in such a very short period, with more time and data collected I can tune the models and make them much more efficient and accurate for hot posts.

- I love contributing in new ways to better journalism spreading the news and reach as many people as possible. If your ready to increase your engagement and views of your media content then this is the product for you! 


---

### Description
- This project helps you practice webscraping, NLP, and classification models.
- Collecting data by scraping a website and then building a binary predictor.

---

# Problem Statement:
## To test and see what model will predict the best score.
- **I have chosen these models and will find the best score among them.**
- RandomForestClassifier
- KNeighborsClassifier
- LogisticRegressionCV
- GradientBoostingClassifier

---
### Project Summary



- 1) First, I made a while/for loop script with API webscraper from praw to collect as many hot posts available every 3 hours.

- 2) I import the scraped data into df's and perform cleaning(dropping emojis ect) & eda.

- 3) I create my X['features'] for the model while lemmatizing which makes multiples words to the base word(cat's & cats to cat), We Instantiate Tfid Vecotrizing: Common words are penalized, Rare words have more influence, Eliminate 'stop_words' to improve our analysis.   If you pass say, 5 to max_features, that would mean creating a feature matrix out of the most 5 frequent words accross text documents. Which is what the model will work with.
- X['features']: The title of the thread: 'title'.
- X['features']: The subreddit that the thread corresponds to: 'subreddit'.
- X['features']: The length of time it has been up on Reddit: 'time_posted'.

- 4) I join dfs while dropping columns.

- 5) Creating y['target'] baseline =  51.43%. y = num_comments + median of num_comments is above  51.43% is hot and below is not hot.

- 6) My models
- RandomForestClassifier
- KNeighborsClassifier
- LogisticRegressionCV
- GradientBoostingClassifier

- 7) Overall scores of each model
- RandomForest model correctly predicted 0.73% overall score of posts.
- GradientBoostingClassifier model correctly predicted 0.67% overall score of posts.
- KNeighborsClassifier model correctly predicted 0.71% overall score of posts.
- LogisticRegressionCV model correctly predicted 0.63% overall score of posts.

- 8) Then did Coefficients/Improtance of features in models Interpretations 

---

# Conclusion & Recommendations
- **Based on my problem statement and work, I have concluded, That my model predicts what words make a post that get above the baseline of comments which are hot subreddit posts.**
- **For future iteration  I will run Sigma(my data scrape script) alot longer as 1 day of scraping data isn't enough to use to train the model for scores.**
- **The model  score of Not Hot post are more accurate than the Hot post score, I think I need more data in order to improve the models overall.**
- **time_posted doesn't seem to effect the num_comments a post have from the data collected and interpretations.**
- **Hot post typically trends for around a day then gets pushed down by new hot posts which seems to not effect num_comments in contrary to age of post.**
- **With the findings I have with my model scores and trend can determine which subreddit post company's can template and use to make FiveThirtyEight get more views and interaction on each new post.**
