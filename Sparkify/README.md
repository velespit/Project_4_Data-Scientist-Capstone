# Capstone Project: Sparkify


### Medium Blog Post
Here is the Medium blog post I have written regarding the project:


### Project Motivation
The project is centered on the issue of company churn. When a consumer discontinues using a service or downgrades their subscription, this is known as churn. Churn essentially reduces a company's subscribed user base, which is bad for profit.

Companies are looking for customers that could potentially leave and target them with special offers. This is why having a precise model for spotting churn is crucial. I define churn in the project, extract features from the dataset, and train a few different classification models.

I also attempt to provide answers to the following queries during the data exploration process:
“Who are the most popular artists and what are the most popular songs in the dataset?”
"In which hours in a day, the most number of songs are listened to?"


### Libraries
I use Python3. Here are the libraries I used in my Jupyter Notebook:
1. pyspark.sql
2. seaborn
3. matplotlib.pyplot
4. datetime


### Summary of The Analysis
I read the dataset into a Spark dataframe at the start of the project. I examined the dataframe's structure before performing any exploratory analysis. I discovered the number of columns, rows, and column names. I then began the "Data Cleaning" section here. I had to determine whether the dataset contained any missing values. I have to mark the churned users because this is a churn problem that I am supposed to model. As a result, I eliminated the rows where the "userId" column contained missing values.

There are 225 users in all, according to my examination of the dataset. There are 154 individuals who have "Downgrade," and 52 people who have "Cancellation Confirmation." Since the vast majority of users would then be labeled as Churn users, I did not prefer to add "Downgrade" users to Churn. Because of this, I included Churn as a user group in the dataset that had "Cancellation Confirmation."

After “Data Cleaning” part, I started to look deeper into the dataset and tried to understand the details of the dataset. This is the “Exploratory Data Analysis” part. Here I focused on answering some questions like the gender distribution of churn users, number of songs listened to by churn and no-churn users etc. But the main point here was to find some features that might be used for the churn model.

I began the "Feature Engineering" phase after the "Exploratory Data Analysis" phase. The "page" column, which provided information on the user's behaviors while using the Sparkify service, proved to be quite beneficial in this situation. I believe it's critical to comprehend the behaviors and actions of various users for a churn model. Additionally, I gathered data on each user's gender, level (free or paid subscription), and length of membership. After locating the features I wanted to use, I vectorized, scaled, and extracted the churn label from the features. (The users whose dataset entries included "Cancellation Confirmation").

Finally I used four different classification algorithms for churn model:

⦁ Random Forest Classification
⦁ Logistic Classification
⦁ Gradient-Boosted Tree Classification
⦁ Linear SVC Classification

The worst model (Linear SVC Classification) had an f1-score around 55 percent. But other three models have better performances and the highest performance is from logistic classification and random forest classification with an f1-score of around 76 percent.


### File Descriptions
1. sparkify.ipynb
This Jupyter Notebook file contains the Python code that loads the dataset, cleans the data, make explatory analysis. The notebook also contains feature extraction process and training different models with classification algorithms.


### Acknowledgement and References
The project and dataset belong to Udacity.
