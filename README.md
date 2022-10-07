Personalized Hotel Recommender using Sentiment Analysis
# Introduction
<div align ="justify"> One of the most basic human activity is travel. Finding quality lodging when traveling is the hardest part. According to data from travel reservations in 2018, there were around 148 million online bookings, of which 82% were made using an app or website [1]. This highlights how dependent individuals are on internet and applications to find lodging. Most of these websites and applications offer some sort of measure to assist customers in making hotel reservations, but frequently they don't focus on the user and don't take into consideration their unique needs. </div>

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
