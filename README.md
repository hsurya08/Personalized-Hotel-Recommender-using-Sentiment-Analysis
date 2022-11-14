Personalized Hotel Recommender using Sentiment Analysis
# Project Proposal
Proposal Video: https://www.youtube.com/embed/JXZaFI5LYqo

# Introduction
<div align ="justify"> One of the most basic human activity is travel. Finding quality lodging when traveling is the hardest part. According to data from travel reservations in 2018, there were around 148 million online bookings, of which 82% were made using an app or website [1]. This highlights how dependent individuals are on internet and applications to find lodging. Most of these websites and applications offer some sort of measure to assist customers in making hotel reservations, but frequently they don't focus on the user and don't take into consideration their unique needs. Many studies on this subject of hotel recommendation systems focus just on user preferences and ignore hotel reviews or fail to account for the important differences between various users [2]. The main goal of this project to provide user with personalized  hotel recommendation.
<br>
<br>
The dataset that we are using consists reviews of various hotels present in Europe. It contains features such as Hotel Address, Review Date, Average Score (Average of ratings for a single hotel), Hotel Name, Reviewer Nationality, Total Number of Reviews, Positive Review, Negative Review, Reviewer Score (raiting given to hotel by the customer), days since review.
</div>

# Problem Definition and Motivation
<div align ="justify"> When reserving a hotel, the most popular approach for making a good decision has been to read the ratings and reviews. But the main issue here is that these evaluations were made based on the viewpoint of one individual. A 5-star rating for one person may be a 2-star rating for another. Some people would select a hotel with a lower price over the ambiance, while others might do so regardless of cost. 
<br>
<br>
Instead of displaying a generic hotel rating, our goal is to help the customer by making more individualized hotel suggestions that consider their preferences for different factors like pricing, cuisine, atmosphere, etc. In turn, this facilitates a quicker and more effective process for the customer to choose the best hotel depending on their preferences.
</div>

# Methods
## Supervised Learning
<ol>
  <li>Multi-class Logistic Regression</li>
  <li>Naive Bayes</li>
  <li>Support Vector Machine (SVM)</li>
  <!--
  <li>Random Forest Classifier</li>
  -->
</ol>

## Unsupervised Learning
<ol>
  <li>Hierarchical Clustering</li>
  <li>GMM</li>
  <li>DBSCAN</li>
</ol>

## Dataset Cleaning
<div align ="justify"> The project we are developing uses the “515k-hotel-reviews-data-in-europe” dataset for our models training. The data was scraped from Booking.com. 515,000 people have evaluated and reviewed 1493 upmarket hotels from around Europe in this dataset. There are 17 feature columns in total, including Hotel Address, Review Date, Average Score, Hotel Name, etc. in the csv file. The dataset's unused columns have been removed because our model presently relies only on some columns of information from it.
<br>
<br>
Additionally, some of the data samples were just given with the overall ratings rather than a descriptive comments. In order to address such review samples, we have updated them with empty strings which ultimately increases the model's confidence on the dataset.
<br>
<br>
Screenshots of both the original and modified data sets are provided below.
</div>



### Original Dataset from Kaggle:
<img src="OriginalSnippet.jpg">
Original Dataset Drive Link: https://drive.google.com/file/d/1gHVqypEysmkC1uxz4siE0P8jhmtG9sDx/view?usp=share_link

### Processed Dataset:
<img src="CleanedDataFrame.jpg">
Cleaned Dataset Drive Link: https://drive.google.com/file/d/1AzyuTb1BVKKusaFd5LGhALzzqpmF7Unk/view?usp=share_link


# Potential Results

## Supervised Learning
<!--
<ul>
  <li>Build a Sentiment classifier to tag the reviews into positive, negative, and neutral categories with an accuracy of 60 – 70 %.</li>
  <li>Analyze it with different classification algorithms.</li>
</ul>
-->
<div align ="justify"> For the purpose of categorizing our data into classes of positive, negative, and neutral information, we use the supervised learning methods like Multi-class Logistic Regression, Naive Bayes, and Support Vector Machine. For training and testing, the data are split in an 80-20 ratio. The algorithms are assessed using many metrics, which are listed below. This makes it easier to compare them.
<br>
<br>
<div align ="justify"> We utilize Vader Sentiment Analyzer to calculate a sentiment score for each review after cleaning and analysing the data. Thus, we receive scores ranging from -1 to 1. Then, we determine thresholds for negative (less than -0.25), neutral (between -0.25 and 0.25) and positive data (more than 0.25). These will function like the real deal. We also divide the data 80-20 between training and testing. After that, we run the Supervised algorithms and do the metric evaluation.
  
  
## Unsupervised Learning (Future Work)

  <!-- <li>Build a Hotel Recommendation system based on the categories of the reviews.</li>
  <li>Ability to provide the best hotels based on the user preferences.</li>
  <li>Examine it with various clustering Techniques.</li>
  -->
  <div align ="justify">  Usage:
  The goal of this Hierarchical clustering is to identify the key themes in a collection of reviews. For that, we group the words with similar meanings             
  together.Once the results of the hierarchical clustering have been reduced to the most advantageous dendrograms, we assign the cluster with an appropriate aspect 
  name.
  <li>Firstly, we create a noun work vector from each review. Ex: [ ‘Food’, ‘Noodles’, ‘room’] </li>
  <li>After the noun vector is formed, we use the Spacy library to determine how similar each word is with other word in the vector. A size of words x words similarity   matrix is generated.</li>
  <ol>
  <img src="correlation.png">
  </ol>
  <li>The Hierarchical clustering receives this similarity matrix as a correlation matrix.</li>
  <ol>
  <img src="hierar.png">
  </ol>
  <li>Hierarchical clustering output is dissected into dendrograms.</li>


# Evaluation Metric
  
## Supervised Learning
  
<ul>
  <li>F Measure </li>
  <li>Recall </li>
  <li>Precision</li>
  <li>Accuracy</li>
  <li>Support</li>
 </ul>
 
  <div align ="justify"> The classification report of all 3 supervised algorithm gives us various scores. The overall accuracy among all three is comparable, that being around 70%. 
  
 ## Unsupervised Learning 
 <ul>
  <li>Silhouette</li>
  <li>Beta-CV</li>
  <li>METEOR</li>
</ul>

# Proposed Timeline
<a href="Ganntchart.xlsx" download>
  <img src="gannt.png">
</a>

# Team Responsibilities
<ul>
  <li><strong>Sunil Ravilla</strong> - Supervised Learning, Data collection and Cleaning</li>
  <li><strong>Prasanth Bathala</strong> - Supervised Learning, Data collection and Cleaning</li>
  <li><strong>Nigam Katta</strong> - Unsupervised Learning, Exploratory Data Analysis</li>
  <li><strong>Hemanth Sai Surya Kumar Tammana</strong> - Unsupervised Learning, Evaluation Metrics</li>
  <li><strong>Sahaj Jha</strong> - Unsupervised Learning, Evaluation Metrics</li>
</ul>


# References
[1] https://www.stratosjets.com/blog/online-travel-statistics/

[2] K. Takuma, J. Yamamoto, S. Kamei and S. Fujita, "A Hotel Recommendation System Based on Reviews: What Do You Attach Importance To?," 2016 Fourth International Symposium on Computing and Networking (CANDAR), 2016, pp. 710-712, doi: 10.1109/CANDAR.2016.0129.

[3] Abro, Sindhu, et al. "Aspect Based Sentimental Analysis of Hotel Reviews: A Comparative Study." Sukkur IBA Journal of Computing and Mathematical Sciences 4.1 (2020): 11-20.

[4] Schouten, Kim, and Flavius Frasincar. "Survey on aspect-level sentiment analysis." IEEE Transactions on Knowledge and Data Engineering 28.3 (2015): 813-830.
Abro, Sindhu, et al. "Aspect Based Sentimental Analysis of Hotel Reviews: A Comparative Study." Sukkur IBA Journal of Computing and Mathematical Sciences 4.1 (2020): 11-20.

[5] Musto, Cataldo, et al. "A multi-criteria recommender system exploiting aspect-based sentiment analysis of users' reviews." Proceedings of the eleventh ACM conference on recommender systems. 2017.

[6] Pathuri, Siva Kumar, N. Anbazhagan, and G. Balaji Prakash. "Feature Based Sentimental Analysis for Prediction of Mobile Reviews Using Hybrid Bag-Boost algorithm." 2020 7th International Conference on Smart Structures and Systems (ICSSS). IEEE, 2020.
