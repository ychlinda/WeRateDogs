# WeRateDogs
## Clean, Analyze and Visualize WeRateDogs tweets data
### Data Wrangling Report

**Step 1: Gather data**

I first downloaded the `twitter_archive_enhanced`.csv mannually and saved it in the desired folder. Then I used Python requests library to download the image predictions programmatically as `image_predictions.tsv`.Finally, I pulled and stored each tweet's JSON data in a text file with tweepy library after authenticating the twitter API.

**Step 2: Assess data**

I loaded the data into pandas dataframes and assessed them one by one.

**`image_predictions`**

This dataset requires less work than the other two. I checked the statistics of the confidence level and eyeballed the dog breeds. Not all dog breeds follow the same convention so they have to be cleaned up. The column names are not very informative and we probably don't need to analyze all three predictions.Last but not least, the datatype for tweet_id should be string not integer.

**Twitter API data**
There are many columns and I will need to decide which is relevant to my analysis and extract the information.

**`twitter_archive_enhanced`**

There dataset is quite messy and untidy. There are a number of errors in name, dog stages, ratings etc which are important to the analysis.I listed all the problems in the summary below. 

>**Summary of data quality and tidiness issues**

>**Quality**

>`twitter_archive_enhanced`

>- Timestamp and Retweet timestamp should be datetime, not object. All ids should be string not float. 
>- Remove the retweets.
>- Remove the columns irrelevant to the analysis.
>- Correct the wrongly captured names and remove those that cannot be fixed.
>- Correct the wrongly captured numerator and denominator ratings and remove those that cannot be fixed.
>- Source information needs to be cleaned up. It should show which application/device people used to access twitter.
>- Dog stages are wrongly captured.

>`image_predictions`
>- Some breeds with the first letter capitalized, others not. Change all breed names to lowercase and remove the "-" dash in between.
>- tweet_id should be string not integer.
>- Column names 'p1','p2','p3','p1-dog','p2-dog',and 'p3-dog' are not informative. Rename them.

>`tweets`
>- Ids should be string not integer.

>**Tidiness**

>`twitter_archive_enhanced`
>- Dog stages should be one column with 5 possible outcomes (4 stages and None). Data type for the new column "stage" should be categorical.

>- All three datasets should be merged into one on twitter_id.

**Step 3: Clean data**

I adopted the "define-code-test"process and cleared every issue on the list. In the end, I merged all the clean data into a single table and save it as a master CV file.


```python

```
