# Project 3: Web APIs, NLP and Classification 

### Contents:
- [Purpose of this Study](#Purpose)
- [Executive Summary](#Executive-Summary)
- [Conclusions](#Conclusions)
- [References](#References)

## Purpose

The purpose of this project was to utilize a web API to gather text data, process with NLP tools for text classification, then to gain insight into the differences (if any) between two groups. This study focused on the gaming communities for **Call of Duty** and **Dungeons and Dragons**. 

## Executive Summary

Understanding game communities is a key piece in understanding the popularity and longevity of any game. In this study, the online forum 'reddit' was used as a source of information about the communities for two games: **Call of Duty** and **Dungeons and Dragons**. 

Initially, 4000 posts made to each of the subreddits

**/r/CallOfDuty**    
       and   
**/r/DnD**

over the coure of 2 to 3 weeks in May 2020 were gathered using [Pushshift's](https://github.com/pushshift/api) API and then analyzed by Natural Language Processing (NLP) machine learning models.

Four base models, consisting of 
1. CountVectorizer + LogisticRegression
2. TfidfVectorizer + LogisticRegression
3. CountVectorizer + MultinomialNB. (Naive Bayes)
4. TfidfVectorizer + SVC (Support Vector Machine Classifier) 

were tuned and evaluated. All 4 models were able to classify a new post as coming from either Call of Duty or from Dungeons and Dragons with 92% accuracy, which is significantly higher than the baseline of 50% accuracy achieved by guessing one of them -- "It's Call of Duty!" -- every time.

**Summary of predictions on test data**   

|Model| Sensitivity|Specificity|Precision|Accuracy|
|---|---|---|---|---|
|Baseline model|1.0000|0.0000|0.5021|0.5021|
|Best CountVec - LogReg|0.8786|0.9670|0.9642|0.9226|
|Best TfidfVec - LogReg|0.8969|0.9361|0.9341|0.9165|
|Best CountVec - MultiNB|0.9214|0.8373|0.8511|0.8795|
|Best TfidfVec - SVC|0.8908|0.9331|0.9307|0.9118|

Once the model had reached this level of accuracy, the features used by the model to make these predictions were further explored. The terms with the greatest predictive power for each group are shown below.

![NLP top predictive vocab](assets/NLP_top_predictive_vocab.png)


There are a couple of possible conclusions from these lists. Unforunately, the NLP models used to classify these posts are not the right tools to take this analysis to the next stage. 

### Next Steps

A follow-up study could be designed to explore questions such as these:
- Do most community discussions center around game mechanics? Is this true for other games and for other online communities outside of reddit?   
  - Call of Duty: warzone, lobby, mission, etc.   
  - Dungeons and Dragons: dice, dm (dungeon master), oc (original character), etc.
- Does the non-game-mechanic vocabulary indicate how the community sees their interaction with the game?
  - Call of Duty: 
    - 'remastered' --> waiting for new content
    - 'opinion' --> evaluating the game as an observer / consumer
  - Dungeons and Dragons:
    - 'art' --> appreciating provided artwork and/or generating new artwork
    - 'homebrew' --> making contributions and/or actively engaging in creating the game experience   
   
_Note: 'homebrew' is a term akin to 'fan fiction' that indicates assets or creative content made by players rather than by the original game designers._

## Conclusions

Based on the ability of the model to accurately classify 92% of posts, it is clear that these two communities have unique discussion topics and vocabulary. 

Based on some of the highly predictive terms -- 'remastered' for Call of Duty and 'homebrew' for Dungeons and Dragons -- both communities are highly engaged and interest remains high in both games. 

Finally, the fact that over 4000 posts were made to each of these subreddits in less than a month indicates that both communities are very active, and an investment in understanding and supporting these communities may pay valuable dividends by encouraging continued interest.

## References

[Presentation Materials](presentation/NLP-DnD-CoD.pdf)  

[Pushshift's API](https://github.com/pushshift/api)    
   
[Call of Duty subreddit](https://www.reddit.com/r/CallOfDuty/)     
[Dungeons and Dragons subreddit](https://www.reddit.com/r/DnD/)    
