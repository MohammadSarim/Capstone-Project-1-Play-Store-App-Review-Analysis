# Capstone Project EDA (PlayStore App Review Analysis)

# **Project Summary -** 

**The purpose of our project** is to conduct an exploratory data analysis on the app reviews data from the Google Play Store. The project aims to Analyze the state of the Android app market and to uncover patterns, trends, and relationships in the data and identify factors that influence the popularity and success of the apps.

### **The following steps will be performed in the project:**

**Data collection**: Collect and gather all relevant data for analysis.

**Data cleaning**: Handle missing values, remove duplicates and handle outliers.

**Univariate Analysis**: Analyze each variable individually to understand its distribution, range, central tendency, and outliers.

**Bivariate Analysis**: Analyze the relationship between two variables and identify the relationship between them.

**Multivariate Analysis**: Analyze more than two variables together to identify complex relationships between variables.

**Data Visualization**: Use various visualizations such as histograms, box plots, scatter plots, etc. to represent the data and gain insights.

**Feature Engineering**: Transform and create new variables to improve the quality of the data.

**Report Writing**: Summarize the insights and findings from the analysis and communicate it effectively to the stakeholders.

# **Problem Statement**

1. What are the top five earning Category?
2. Top 5 earnings Apps
3. Total number of paid and free apps on playstore and it's ratio?
4. Total Number of user using free and paid Apps
5. Highest rating of apps in each genres.
6. Highest Installations according to month.
7. Top categories on playstore on the basis of number of apps.
8. Which category of Apps from the Content Rating column are found more on playstore ?
9. Top 5 best average rating category on playstore
10. Size distribution of apps in playstore
11. Review counts over the time.
12. Sentiment Percentage Analysis?
13. Apps with the highest number of positive reviews.
14. Apps with the highest number of negative reviews.
15. Analysing the user subjectivity.
16. Relationship between the sentiment_subjectivity and the sentiment_polarity.

#### **Business Objective**

The business objective of performing an exploratory data analysis on the app reviews data from the Google Play Store could be:

**Understanding the app market:** By analyzing the app review data, insights can be gained into the app market, including the popularity of different types of apps, the trends and patterns in the data, and the factors that influence the success of an app.

**Improving app development:** The insights from the EDA can help app developers make informed decisions about the development and marketing of their apps. For example, they can understand the features that users value the most and the common complaints and criticisms of their competitors' apps.

**Enhancing app marketing:** The results of the EDA can also be used to inform and guide app marketing strategies. For example, the insights can be used to target the right audience and improve the app's visibility on the Google Play Store.

# **Steps Involved**
 
## **1. About Dataset**

The Google Play Store dataset contains information about the various Android apps that are available for download on the platform.This information typically includes two files as 'Play Store Data.csv' and the other is 'User Reviews.csv'. **Dataset taken from Almabetter**

* **user_reviews.csv:** The User Reviews dataset has 64295 rows and 5 columns. There are 107457 mising values and 33616 duplicate values in the dataset.

* **playstore data.csv:** The User Reviews dataset has 10841 rows and 13 columns. There are 1487 mising values and 483 duplicate values in the dataset.

## **2. Understanding Variables**

**Let us first define what information the columns contain based on our inspection.**

**play_store dataframe** has 10841 rows and 13 columns. The 13 columns are identified as below:
1. **App** - It tells us about the name of the application with a short description (optional).
2. **Category** - It gives the category to the app.
3. **Rating** - It contains the average rating the respective app received from its users.
4. **Reviews** - It tells us about the total number of users who have given a review for the application.
5. **Size** - It tells us about the size being occupied the application on the mobile phone.
6. **Installs** - It tells us about the total number of installs/downloads for an application.
7. **Type** - IIt states whether an app is free to use or paid.
8. **Price** - It gives the price payable to install the app. For free type apps, the price is zero.
9. **Content Rating** - It states whether or not an app is suitable for all age groups or not.
10. **Genres** - It tells us about the various other categories to which an application can belong.
11. **Last Updated** - It tells us about the when the application was updated.
12. **Current Ver** - It tells us about the current version of the application.
13. **Android Ver** - It tells us about the android version which can support the application on its platform.

**User Reviews DataFrame** has 64295 rows and 5 columns. The 5 columns are identified as below:
1. **App** - It tells us about the name of the application with a short description (optional).
2. **Translated_Review** - It contains the Review on the app.
3. **Sentiment:** The overall emotional tone or attitude expressed in a review, such as positive, negative, or neutral.
4. **Sentiment polarity:** A numerical score that quantifies the sentiment of a review, where positive scores indicate positive sentiment, negative scores indicate negative sentiment, and neutral scores indicate neutral sentiment. This score can range from -1 (most negative) to 1 (most positive).
5. **Sentiment subjectivity:** A numerical score that indicates the degree to which a review expresses a personal opinion, as opposed to a factual statement. A score of 0 indicates a completely objective statement, while a score of 1 indicates a completely subjective statement.

## 3. **Data Wrangling**

### **Data Cleaning**

* **Handling Missing Values:**
Rating has 1474 null values which contributes 13.60% of the data. So, replaced the null values with the median.
Type has 1 null value which contributes 0.01% of the data. Content_Rating has 1 null value which contributes 0.01% of the data. Current_Ver has 8 null values which contributes 0.07% of the data. Android_Ver has 3 null values which contributes 0.03% of the data. As the number of null values are less, So Dropped the null values.
Also, In the User Review, Translated_Review has 26868 null values which contributes 41.79% of the data. Sentiment has 26863 null values which contributes 41.78% of the data. Sentiment_Polarity  has 26863 null values which contributes 41.78% of the data. Sentiment_Subjectivity has 26863 null values which contributes 41.78% of the data. Here, not possible to replace the null values as because Sentiment, Sentiment_Polarity and Sentiment_Subjectivity calculated by "Translated_Review" since the "Translated_Review" is also missing from there. So, dropped the null values.

* **Handling Duplicate Values**
There are 483 duplicate values in play store dataset and about 33616 duplicate values in the user reviews dataset. So, removed the duplicate values.

* **Transforming the Data format**
As all the columns except rating have the object data type but some of the columns like, reviews, size, installs and price have the numerical value. So, there is a need to transform them in proper data type and also remove the unwanted values from the numerical columns like ‘+’ and ‘,’ from installs and ‘$’ from price. In the size column we have some values in KB and some values in MB, so we transform all the values in MB.

* **Added columns**
Three columns added Month, Total_Earnings and Size_Interval:
Month added to check the maximum downloads according to the month.
Total_Earnings to check the highest earning categories and apps in the dataset.
Size_Interval to check the size distribution of apps.


## **4. Solution to Business Objective**
#### What do you suggest the client to achieve Business Objective ? 
Explain Briefly.
The solution to business objectives in the Playstore dataset Exploratory Data Analysis (EDA) would depend on the specific goals of the business. However, here are a few common approaches for analyzing Playstore data:

**App Trends:** Analyze the most popular and highly rated apps by categories and time, to understand user preferences and identify opportunities for new app development. Developing apps related to the least categories as they are not explored much. Like **Libraries_And_Demo and Events** .

**User Demographics:** Study the demographics of app users to understand their age, gender, location, and device preferences. Focusing more on content available for **Everyone** will increase the chances of getting the highest installs.

**Revenue Generation:** Analyze app pricing, in-app purchases, and advertising revenue to understand the most profitable business models and optimize pricing strategies. Most of the apps are Free, so focusing on **Free** app is more important.

**User Engagement:** Study user behavior, including app usage frequency, session duration, and retention rate, to understand how to improve user engagement and increase app adoption.So, need to focus on updating their apps regularly, so that it will attract more users.

**Competitor Analysis:** Compare the performance of your app against similar apps in the market to identify strengths and weaknesses and inform marketing and product development strategies.

# **Conclusion**

**Findings**
* Percentage of free apps = ~92%
* Percentage of Users using Free apps = 99.9%
* Most competitive category: Family
* Category with the highest earnings: Lifestyle
* Highest earning app:  I am rich
* Most of the genres having "5" rated app
* Most of the apps installed in the month: "JULY"
* Percentage of apps with no age restrictions = ~82%
* Average ratings of apps in each category lies between 4 to 5
* The size of the most apps on play store lies in the range of: "0-25" mb's.
* Most of the reviews happened in the month: "JULY"
* Helix Jump has the highest number of positive reviews and Angry Birds Classic has the highest number of negative reviews.
* Overall sentiment count of merged dataset in which Positive sentiment count is 64%, Negative 22% and Neutral 13%.

**Limitations:** The dataset may only include reviews from a limited time period, which may not accurately reflect the current market trends or user preferences.

**Recommendations:** Needs to focus on updating their apps regularly, so that it will attract more users. Most of the apps are Free, so focusing on free app is more important. Focusing more on content available for Everyone will increase the chances of getting the highest installs.

**Future Work:** Machine learning can help us to deploy more insights by developing models which can help us interpret even more better. We have left this as future work as this is something where we can work on.
