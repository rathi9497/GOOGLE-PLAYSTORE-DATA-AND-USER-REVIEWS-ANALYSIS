# GOOGLE-PLAYSTORE-DATA-AND-USER-REVIEWS-ANALYSIS
I am going to do EDA and Visualisaion on playstore data and its user reviews dataset.

# Input Files:
Play Store Data.csv - It contains the basic details of the app like number of user reviews, ratings, etc.

User Reviews.csv - It contains the user reviews and its sentiment score for the respective app.

App performance analysis: The performance of an app on the Play Store can be analyzed by tracking metrics such as downloads, ratings, reviews, and user retention. This data can be used to understand the popularity and user engagement of an app, and to identify areas of improvement.

App Store Optimization (ASO): ASO is the process of optimizing app metadata such as app title, description, keywords, and images to improve the visibility and ranking of an app on the Play Store. App analysis tools can help in identifying the right keywords and optimizing the metadata to increase app visibility.

User behavior analysis: Understanding user behavior on the Play Store can help in improving app engagement and retention. This can be done by analyzing user reviews, ratings, and feedback, and by identifying the most popular features of the app.

Market trends analysis: App analysis tools can help in identifying market trends such as popular app categories, user demographics, and app revenue. This information can be used to make informed decisions about app development and marketing strategies.

We have a dataset of playstore and other dataset of its user reviews . in playstore dataset we have RangeIndex: 10841 entries, 0 to 10840 Data columns (total 13 columns)

# Introduction :

The Play Store Apps dataset is a comprehensive collection of information on the mobile applications available on the Google Play Store. It includes information such as the app's name, description, category, developer, rating, number of downloads, and reviews.

Reviews analysis of the Play Store Apps dataset involves examining and analyzing the reviews left by users on the platform. This analysis provides valuable insights into user opinions and sentiments about the app, which can be used to identify areas for improvement and to develop better apps.

The dataset contains millions of reviews in multiple languages, which presents both opportunities and challenges for analysis. Researchers and data scientists can use natural language processing techniques to extract meaningful insights from the reviews, such as sentiment analysis, topic modeling, and text summarization.

Reviews analysis of the Play Store Apps dataset has numerous applications. For example, it can be used by app developers to identify and fix bugs, add new features, and improve the user experience. It can also be used by businesses to understand user preferences and develop targeted marketing strategies. Additionally, it can be used by researchers to study user behavior and preferences, as well as to develop new machine learning algorithms for app recommendations and discovery.

# Content of dataset :

The Play Store dataset typically includes a wide range of information about the mobile applications available on the Google Play Store. The exact content of the dataset may vary depending on the source, but some common attributes of the dataset include:

1.App: It contains the name of the app with a short description (optional).
2.Category: This section gives the category to which an app belongs. In this dataset, the apps are divided among 33 categories.
3.Size: The disk space required to install the respective app.
4.Rating: The average rating given by the users for the respective app. It can be in between 1 and 5.
5.Reviews: The number of users that have dropped a review for the respective app.
6.Installs: The approximate number of times the respective app was installed.
7.Type: It states whether an app is free to use or paid.
8.Price: It gives the price payable to install the app. For free type apps, the price is zero.
9.Content rating: It states which age group is suitable to consume the content of the respective app.
10.Genres: It gives the genre(s) to which the respective app belongs.
11.Last updated: It gives the day in which the latest update for the respective app was released.
12.Current Ver: It gives the current version of the respective app.
13.Android Ver: It gives the android version of the respective app.

The contents of User Reviews are:

App: It contains the name of the app with a short description (optional). Translated_Review: It contains the English translation of the review dropped by the user of the app. Sentiment: It gives the attitude/emotion of the writer. It can be ‘Positive’, ‘Negative’, or ‘Neutral’. Sentiment_Polarity: It gives the polarity of the review. Its range is [-1,1], where 1 means ‘Positive statement’ and -1 means a ‘Negative statement’. Sentiment_Subjectivity: This value gives how close a reviewer’s opinion is to the opinion of the general public. Its range is [0,1]. Higher the subjectivity, closer is the reviewer’s opinion to the opinion of the general public, and lower subjectivity indicates the review is more of a factual information.

# What is EDA ?

Exploratory Data Analysis (EDA) is an approach to analyzing and understanding data in order to extract meaningful insights and patterns. It involves a variety of techniques and methods to explore the data, such as statistical methods, visualization tools, and data mining algorithms.

The main goal of EDA is to gain a better understanding of the data, identify patterns and relationships among variables, and generate hypotheses for further analysis. This is typically done through the use of summary statistics, visualizations, and other exploratory techniques.

EDA involves a number of steps, including data cleaning, variable selection, summary statistics, and visualization. During the data cleaning step, the data is checked for errors, missing values, and outliers. In the variable selection step, relevant variables are selected for further analysis based on their importance and relevance. Summary statistics are then calculated to describe the distribution of the data, such as the mean, median, and standard deviation.

Visualization is a key component of EDA, as it allows for the data to be visualized in various ways, such as scatter plots, histograms, and heat maps. These visualizations can help identify patterns and relationships among variables, as well as highlight potential outliers or anomalies.

Overall, EDA is a crucial step in the data analysis process, as it helps to uncover potential issues with the data and generate hypotheses for further analysis. By understanding the patterns and relationships in the data, researchers and analysts can make more informed decisions and develop more accurate models and predictions.

# Steps Involved:

Data Cleaning: Data cleaning is the process of identifying and correcting errors, inconsistencies, and inaccuracies in a dataset. It is an important step in data preparation, as the quality of the data directly impacts the accuracy and reliability of any analyses or models that are built using the data.

Data cleaning typically involves several steps, including:

Removing duplicates: Identifying and removing any duplicate records in the dataset. Handling missing data: Dealing with any missing values in the dataset, either by imputing them with a sensible value or by removing the record altogether. Correcting errors: Identifying and correcting any errors or inconsistencies in the data, such as misspellings, typos, or incorrect values. Standardizing data: Ensuring that the data is in a consistent format and that any units of measurement are standardized across the dataset. Handling outliers: Identifying and handling any outliers in the data, either by removing them or by transforming them into more appropriate values. The data cleaning process is iterative, and may involve going back and forth between different steps as new issues are discovered and addressed. The goal is to ensure that the data is as accurate and complete as possible, and that any issues that may impact the validity of the analysis or model are addressed.

Overall, data cleaning is a critical step in the data analysis process, and can help to ensure that the insights and conclusions drawn from the data are robust and accurate.

Our data set contains a large number of null values in the rating column, so we drop them. Some of the columns have a smaller number of null values, so we replace the null values in these columns with the mode value of that particular column. Our data set also contain the duplicate rows for a single application. We also drop the duplicate rows because the rows contain the identical data. Also drop the rows, which have rating greater than 5.

Data Transforming From the information of data frame, we can see that all the columns except rating have the object data type but some of the columns like, reviews, size, installs and price have the numerical value. So, we have to transform them in proper data type and also remove the unwanted values from the numerical columns like ‘+’ and ‘,’ from installs and ‘$’ from price. In the size column we have some values in KB and some values in MB, so we transform all the values in MB.

Exploratory Data Analysis After establishing a good sense of each feature, we proceeded with plotting a pairwise plot between all the quantitative variables to look for any evident patterns or relationships between the features. There is a high variance in the number of installs and in number of reviews. To overcome this problem, we add two new columns to the data frame named: log_installs and log_review, which contain the logarithmic values of installs and review columns, respectively.

Single Variate Analysis After that we analysis all the columns one by one to examine whether the particular column contain some useful information or not:

Category We breakdown the apps by category and observe that family and game categories have the maximum number of apps in the play store. Weather, house and home, comics, events, beauty, and parenting are the categories which have a few numbers of apps.

# Data Wragling:

Data wrangling, also known as data munging or data preprocessing, refers to the process of transforming and cleaning raw data into a format that is suitable for analysis. This involves a variety of tasks, such as combining multiple datasets, cleaning and formatting data, and selecting relevant variables for analysis.

The main goals of data wrangling are to ensure that the data is consistent, complete, and usable for analysis. This process typically involves the following steps:

Data acquisition: Collecting the raw data from various sources, such as databases, spreadsheets, or APIs. Data cleaning: Identifying and correcting errors, inconsistencies, and inaccuracies in the data, as well as handling missing data and outliers. Data integration: Combining multiple datasets and ensuring that they are aligned properly. Data transformation: Converting data into a consistent format and creating new variables or features as needed. Data reduction: Selecting relevant variables for analysis and reducing the size of the dataset as needed. Data formatting: Ensuring that the data is properly formatted and organized for analysis, such as converting dates and times into a standardized format.

# Installs:

We analysis the install column to observe the effect of size, price, rating, content rating, android version on app installation number. We can analysis that for each and every category number of app installation does not depend on the size. The free apps installed mostly. The apps which can be used by everyone is more installed than the apps which can be used by a particular age group. Rating of mostly installed apps is between 4 and 5.

# Conclusion:

Most of the apps are free so developers should focus on creating free apps to have a huge customer base. If developing paid apps then apps size should not be greater than 40mb. More Apps should be in the category like Events,Beauty,Parenting as they have not been explored much but still quite popular with huge installations. Apps belonging to Game and Family Category have high negative reviews therefore they should be developed carefully. These are some of the aspects that the developer should research before proceeding with the app development. By conducting a simple exploratory data analysis (EDA) on the play store dataset, we not only eliminate avoidable risks of failure, but we may also be able to provide better ideas for building the app.

® Percentage of free apps = ~92% ® Percentage of apps with no age restrictions = ~82% ® Most competitive category: Family ® Category with the highest number of installs: Game ® Category with the highest average app installs: Communication ® Percentage of apps that are top rated = ~80% ® There are 20 free apps that have been installed over a billion times ® Minecraft is the only app in the paid category with over 10M installs. This app has also produced the most revenue only from the installation fee. ® Category in which the paid apps have the highest average installation fee: Finance ® Most popular app in the Play Store based on the number of reviews: Facebook ® The median size of all apps in the play store is 12 MB. ® The apps whose size varies with device has the highest number average app installs. ® The apps whose size is greater than 90 MB has the highest number of average user reviews, i.e., they are more popular than the rest. ® Helix Jump has the highest number of positive reviews and Angry Birds Classic has the highest number of negative reviews.

Play Store app analysis is an essential process for app developers and marketers to improve app performance, user engagement, and revenue. By leveraging the right tools and resources, developers can gain valuable insights into app performance and user behavior, and make informed decisions about app development and marketing strategies.

# Credit :
Contact me for Data Science Project Collaborations. email - prathameshrathi7949@gmail.com
