# CS 7641 Machine Learning Project
ML Based User-Centric Hotel Recommendations System

# Introduction
<div align ="justify"> Traveling is one of the most fundamental of human activities. While traveling, finding good accommodation is the most challenging part. Based on the statistics of 2018 travel booking, there were about 148 million online travel bookings, out of which 82% were via an app or website [1]. This draws attention to the reliance of people on websites and apps for finding accommodation. Most of these websites and apps have one or other metrics to help users to book hotels, however oftentimes they lack being user-centric, taking into account different variables for each user. Lot of work on this topic of hotel recommendation systems, takes just the user preference and not hotel reviews or doesn’t compute the difference of importance for different users [2]. </div>

# Problem Definition and Motivation
<div align ="justify"> Checking the ratings/reviews had been the most commonly used method for identifying a suitable choice while booking a Hotel. However, the major concern here is that these ratings were given based on the unique perspective of a single user. One person's 5-star rating can be another person's 2-star rating	. Some people might prefer a low price over the ambiance, while others might choose the hotel with better ambiance irrespective of the price. 

Our aim is to aid the user by providing more personalized hotel recommendations by considering his preference of various aspects such as price, food, ambiance, etc rather than showing a general rating of the hotel. This in turn helps the user in identifying the most suitable hotel based on his choice, more efficiently and quickly.
</div>

# Methods
## Supervised Learning
<ol>
  <li>Multi-class Logistic Regression</li>
  <li>Support Vector Machine (SVM)</li>
  <li>Random Forest Classifier</li>
</ol>

## Unsupervised Learning
<ol>
  <li>Hierarchical Clustering</li>
  <li>GMM (K-means for initialization)</li>
  <li>DBSCAN</li>
</ol>

# Evaluation Metric
<ul>
  <li>F Measure </li>
  <li>Recall </li>
  <li>Precision</li>
  <li>Silhouette</li>
  <li>Beta-CV</li>
  <li>METEOR</li>
</ul>

# Potential Results
## Unsupervised Learning
<ul>
  <li>Words with comparable meanings are placed in categories by the Hierarchical clustering algorithm.</li>
  <li>Examine it with various clustering techniques.</li>
</ul>

## Supervised Learning
<ul>
  <li>Based on the Sentiment component, Classify the reviews into good, negative, and neutral categories.</li>
  <li>Try out different classification techniques to identify the best model.</li>
</ul>

# Goal
The Ultimate goal of this project is to recommend a list of hotels to the user based on their customized preferences.

# Team Responsibilities
<ul>
  <li>Sunil Ravilla - Supervised Learning, Data collection and Cleaning</li>
  <li>Prasanth Bathala - Supervised Learning, Data collection and Cleaning</li>
  <li>Nigam Katta - Unsupervised Learning, Exploratory Data Analysis</li>
  <li>Hemanth Sai Surya Kumar Tammana - Unsupervised Learning, Evaluation Metrics</li>
  <li>Sahaj Jha - Unsupervised Learning, Evaluation Metrics</li>
</ul>


# References
[1] https://www.stratosjets.com/blog/online-travel-statistics/

[2] K. Takuma, J. Yamamoto, S. Kamei and S. Fujita, "A Hotel Recommendation System Based on Reviews: What Do You Attach Importance To?," 2016 Fourth International Symposium on Computing and Networking (CANDAR), 2016, pp. 710-712, doi: 10.1109/CANDAR.2016.0129.
