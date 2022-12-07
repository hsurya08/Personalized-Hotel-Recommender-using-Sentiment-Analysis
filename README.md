Personalized Hotel Recommender using Sentiment Analysis
# Project - Midterm Report
<iframe
  src="https://www.youtube.com/embed/JXZaFI5LYqo"
  style="width:100%; height:500px;"
></iframe>

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
  <li>Multi-normial Naive Bayes</li>
  <li>Support Vector Machine (SVM)</li>
  <!--
  <li>Random Forest Classifier</li>
  -->
</ol>

## Unsupervised Learning
<ol>
  <li>Hierarchical Clustering</li>
  <li>K-Means</li>
  <!--
  <li>GMM</li>
  <li>DBSCAN</li>
-->
</ol>

## Dataset Collection and Cleaning
<div align ="justify"> The project makes use of the “515k-hotel-reviews-data-in-europe” dataset for training the models. The data was scraped from Booking.com. The data comprises of reviews evaluated by 515,000 people for 1493 upmarket hotels in Europe. There are 17 feature columns in total, including Hotel Address, Review Date, Average Score, Hotel Name, etc., in the csv file. The unused columns in the dataset were removed because they don't have significant contribution to the model.
<br>
<br>
Additionally, some of the data samples were just given with the overall ratings rather than a descriptive comments. Since the project concentrates on the user preferences rather than quantitative review value, such data is replaced with an empty string.
<br>
<br>
Screenshots of both the original and modified data sets are provided below.
</div>



### Original Dataset from Kaggle:
<img src="OriginalSnippet.jpg">
<a href="https://drive.google.com/file/d/1Rn9bwG32V87wDp4VuS63RZMwhIngSae3/view?usp=share_link">Download Original Dataset</a>

### Processed Dataset:
<img src="CleanedDataFrame.jpg">
<a href="https://drive.google.com/file/d/1AzyuTb1BVKKusaFd5LGhALzzqpmF7Unk/view?usp=share_link">Download Cleaned Dataset</a>

## Data Preporcessing:

The Preprocessing step includes tokenization, tagging parts of speech, removing stop words, stemming, noun extraction and noun filtering. Tokenization mainly focuess on detecting words. Then the words get tags that determine their syntactic role (such as verb, adjective, etc.) in the sentence. The stop words like "a", "an", "the", "that", "of", "from" are deleted. Then the suffix and prefix of the words are deleted and the stem of the word is retained.
<br>
<br>
The stemming process helps to reduce all derivatives of a word, which are not semantically different, into a common concept. For example, if a document contains words like ‘‘eating’’ and ‘‘eaten’’, they are all considered as ‘‘eat’’. As we are looking for preferences of the user that are usually in the form of nouns, the words that have received the noun tag are extracted. Since the number of these nouns may be very large, unrelated nouns are filtered.

# Results and Discussions:

## Supervised Learning
<!--
<ul>
  <li>Modeled a Sentiment classifier to tag the reviews as positive, negative, or neutral categories with an accuracy of 60 – 70 %.</li>
  <li>Analyzed it with different classification algorithms.</li>
</ul>
-->
### Approach:
<div align ="justify"> For the purpose of categorizing our data into classes of positive, negative, and neutral information, we use the supervised learning methods like Multi-class Logistic Regression, Multinomial Naive Bayes, and Support Vector Machine. For training and testing, the data was split in an 80:20 ratio.
<br>
</div>
 <div align ="justify"> The cleaned and analyzed raw datset has uncategorized reviews. To categorize them, we use a library called <strong>Vader Sentiment Analyzer</strong> which will calculate the sentiment score for each review in the dataset. The range of Sentiment Score varies between -1 and +1. In order to classiy them into the buckets of negative, neutral and positive, a threshold is fixed. The classification of the reviews based on the sentiment score is as follows:
</div>
  <ul>
    <li> Define the class as Negative, if the sentiment score is between -1 and -0.25 </li>
  
   <li> Define the class as Neutral, if the sentiment score is between -0.25 and +0.25 </li>
  
   <li> Define the class as Positive, if the sentiment score is between +0.25 and +1. </li>
 </ul>
<div align ="justify"> This classificaion of data from the Vader Semtiment Analyzer is assumed to be the ground truth labels of the data. With data split of 80:20 as train and test samples, Supervised learning algorithms are applied to classify the data. Further, the model's performance is evaluated by various metrics such as F1 score, Accuracy, Precision, Recall, and ROC-AUC. 
  </div>
  
### Implementation:
<div align ="justify">
Multinomial Naive Bayes, Logistic Regression and Support Vector Machine were utilized to classify the reviews into the positive, negative and neutral. 
<br>
The confustion matrix for all the models are as follows:
</div>
## Naive bayes (Confusion Matrix):

<img src="NB.jpeg">

## Logistic regression (Confusion Matrix):

<img src="LR.jpeg">

## Support Vector machine (Confusion Matrix):
  
<img src="SVM.jpeg">
  
## Evaluation Metrics:
  
Based on the confusion matrix above, Precision, Recall and F1 Score for all the three models are computed and and tabulated below:

| Naive Bayes |  Precision | Recall | F1 Score
| ------------- | ------------- | ------------- | ------------- |
| Negative     | 0.62  | 0.66 | 0.64  |
| Neutral      | 0.65  | 0.54 | 0.59  |
| Positive     | 0.70  | 0.78 | 0.74  |

<br>

| Logistic Regression |  Precision | Recall | F1 Score 
| ------------- | ------------- | ------------- | ------------- |
| Negative     | 0.70  | 0.67 | 0.68  |
| Neutral      | 0.69  | 0.68 | 0.69  |
| Positive    | 0.81  | 0.84 | 0.82  |

<br>

| Support Vector Machine |  Precison | Recall | F1 Score 
| ------------- | ------------- | ------------- | ------------- |
| Negative     | 0.65  | 0.71 | 0.68  |
| Neutral    | 0.68  | 0.65 | 0.66  |
| Positive   | 0.82  | 0.78 | 0.80 |

<br>
Based on the Precision, Recall and F1 Score calculated above, The metrics like Macro-average Precision, Weighted Average Precision, Macro Average Recall, Weighted Average Recall, Macro Average F-1 Score, Weighted Average F-1 Score and accuracy are computed and tabulated below.
  
  | Evaluation Metrics  | Macro Average Precision | Weighted Average Precision  | Macro Average Recall | Weighted Average Recall | Macro Average F-1 Score | Weighted Average F-1 Score | Accuracy |
| ------------- | ------------- | ------------- | ------------- | ------------- |------------- |------------- |------------- |
| Naive Bayes    |  0.66 | 0.65 | 0.66 | 0.66 | 0.65 | 0.65 | 0.65 |
| Logistic Regression    | 0.73 | 0.73 | 0.73 | 0.73 | 0.73 | 0.73  | 0.73 |
| Support Vector Machine | 0.72  | 0.72 | 0.71 | 0.71 | 0.71 | 0.71   | 0.71 |

  From the above metrics, it is observed that Logistic Regression performs the best in classifying the reviews into positive, negative and neutral followed by the Support Vector Machine and Naive Bayes. 
  
  Further, to complement the justification, Receiver Operating Characteristic (ROC) Curves for all the models were plotted. 


## ROC Graphs for our implementations:
  
  
## Naive bayes (ROC Curve):
  <img src="NBROC.jpeg">
  
## Logistic Regression (ROC Curve):
  <img src="LRROC.jpeg">
  
  
## Support Vector Machine (ROC Curve):
  <img src="SVMROC.jpeg">
  
  From the ROC curves, it is justified that the logistic Regression performs better than the Support Vector Machine and Naive Bayes.
  
## Unsupervised Learning :
    
  <!--
      <ol>
      <li>Build a Hotel Recommendation system based on the categories of the reviews.</li>
      <li>Ability to provide the best hotels based on the user preferences.</li>
      <li>Examine it with various clustering Techniques.</li>
      </ol>
  -->
   
### Approach:
  <div align ="justify">
  <!--
  We plan to use Hierarchial clustering to cluster the similar words. The goal of this Hierarchical clustering is to identify the key attributes in a collection of reviews. For that, we group the words with similar meanings. Once the dendogram obtained from the hierarchical clustering have been disected into clusters, we assign each of the cluster with an appropriate aspect name. -->
  We implemented both Hierarchial and K-means clustering for forming clusters of the aspects generated. In doing so we employ different library implementations. We first use a pyABSA library to extract a lot of aspects (nouns) throughout different reviews. This is done using the aspect_extractor function of pyABSA. For each hotel, each review within it, is parsed which then undergoes the aforementioned supervised learning algorithms to give sentiment to the aspects. A confidence factor is also generated using the pyABSA. It uses BERT to perform aspect extraction. During generation of large number of aspects with different confidence scores, a multiplicative operation is performed. Positve one is multiplied to the confidence score of assigned sentiment 'positve', negative 1 is multiplied to the confidence score of assigned sentiment 'negative' and zero in case of 'neutral' to generate the aspect score. 
<br>  
<br>
  Further, with each review the repititive aspects aren't added but their confidence score modified according to the sentiment. Atlast a huge dictionary of aspects with sentiment and it's score is generated. We then use BERT embeddings and spaCy to find similar words (in terms of numeric values). After that unsupervised learning algorithms are used to make clusters. These clusters are manually labelled and we finally narrow down to 7/8 clusters.
  </div>
    
### Steps:
  <ol>
  <li>Firstly, we create a noun vector from each review. Ex: [ ‘Food’, ‘Noodles’, ‘room’] </li>
  <li>After the noun vector is formed, we use the Spacy library to determine how similar each word is with other word in the vector. A matrix of size (words x words) with similarity values is generated.</li>
    
  <li>The Coorelation matrix for a single example is as shown below:</li>
       
  <img src="correlation.png">
  
  <li>The dendogram obtained from Hierarchial clustering is dissected into clusters.</li>
  <img src="hierar.png">
  </ol>
<!--

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
-->

# Proposed Timeline
<a href="Ganntchart.xlsx" download>
  <img src="gannt.png">
</a>

# Team Contribution
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
