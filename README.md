# Project4-Spotify 
# Spotify Machine Learning Analysis and Problem Solving


## Project Overview

Spotify was founded on April 23, 2006, by Swedish entrepreneurs Daniel Ek and Martin Lorentzon, Spotify has grown into one of the world’s leading platforms for audio streaming and media services. Available across mobile, tablet, and laptop devices, Spotify offers users seamless access to a vast library of digital audio content — including music, podcasts, and recently, audiobooks. As of December 2024, Spotify reported over 678 million monthly active users, of which 268 million were paying subscribers, reaffirming its position as a dominant force in the global audio streaming market.

- Analyzing data from 520 spotify users to understand what customer behaviors are indicators that lead to a Free User becoming a paid subscriber.
We tackle this problem in three different ways:
1- By creating and optimizing general supervised machine learning models to identify willingness to subscribe and  feature importance 
2- By Compartmanalizing the data into three different categories to explore the Demographics of its users, Their Interaction with the app, as well as the content of most interest to them. 
3- By zooming in on certain features such as mood 

The factors we have explored throught this project include: age, gender, Spotify usage, prefered listening content, music time slots, music influential mood, music listening frequency.

We conduct these measurments in a variety of methods, involving unsupervised machine learning such as K-means, clustering, PCA and comparing graphs. We also applied suppervised machine learning such as neural networks and random forrest to understand willing subscriber groups as well as important features to consider. 

## Repository Contents
```
Spotify Analysis Project
├── README.md                        # Project overview and documentation
├── Resources/                       # Folder containing data and additional resources
│   ├── refined_numbered_data.csv    # Processed dataset
│   └── Spotify_data.csv             # Original dataset
├── SpotifyPowerpoint.pdf            # Powerpoint Presentation
├── 3 Way Analysis Demographic Interaction Content.ipynb  # Jupyter notebook for demographic analysis
├── Spotify Feature Analysis.ipynb   # Jupyter notebook for feature analysis
├── Supervised Machine Learning and ETL.ipynb  # Jupyter notebook for ML and ETL processes
├── FeatureImportance.h5             # Saved model weights (HDF5 format)
├── subscribervsunsubscriber.h5      # Saved model weights (HDF5 format)
└── Willingnesstosubscribe.h5        # Saved model weights (HDF5 format)
```
## How to Use and Interact with the Project
Open each Jupyter notebook and click run all

## Technologies and libraries Used:
1. Data Handling : Pandas, NumPy, Pathlib
2. ML: Scikit-learn (preprocessing, RF), TensorFlow/Keras (NN)
3. Evaluation:	Confusion matrices, accuracy/loss metrics, permutation_importance: Feature analysis, silhouette_score: Cluster validation
4. Storage:	CSV (input/output), HDF5 (model saving)
5. Visualization: Matplotlib (plt): Basic plotting, Seaborn (sns): Statistical visualizations, Holoviews (hv) + HvPlot: Interactive dashboards, Bokeh (via hv.extension('bokeh')): Web-based interactivity
6. Preprocessing: OneHotEncoder/LabelEncoder: Categorical data handling, MultiLabelBinarizer: Multi-category encoding, StandardScaler/MinMaxScaler: Feature scaling,ColumnTransformer: Mixed data type pipelines
7. Modeling: RandomForestClassifier: Supervised learning, KMeans: Clustering, PCA: Dimensionality reduction
8. Workflow Tools: train_test_split: Data splitting, Pipeline: Streamlined ML workflows

### Data Source 
exported Spotify data from Kaggle into a CSV file. Uploaded CSV file including 520 entries.

### Data Features 
1- Age
2- Gender
3- spotify_usage_period
4- spotify_listening_device
5- spotify_subscription_plan
6- premium_sub_willingness
7- preffered_premium_plan (Note: "Preferred" is misspelled as "Preffered")
8- preferred_listening_content
9- fav_music_genre (Short for "Favorite Music Genre")
10- music_time_slot
11- music_Influencial_mood (Note: "Influential" is misspelled as "Influencial")
12- music_lis_frequency (Short for "Music Listening Frequency")
13- music_expl_method (Short for "Music Exploration Method")
14- music_recc_rating (Short for "Music Recommendation Rating")
15- pod_lis_frequency (Short for "Podcast Listening Frequency")
16- fav_pod_genre (Short for "Favorite Podcast Genre")
17- preffered_pod_format (Misspelled as "Preffered")
18- pod_host_preference
19- preffered_pod_duration (Misspelled as "Preffered")
20- pod_variety_satisfaction

## Data Transformation
### Step 1: Feature Selection
Removed Irrelevant Columns:
Dropped podcast-related and overly specific columns (e.g., preffered_pod_format, pod_host_preference).
Kept core features like Age, Gender, spotify_usage_period, music_recc_rating, etc.

### Step 2: Categorical Encoding & Feature Engineering
A. Ordinal Encoding
spotify_usage_period:
Mapped to numerical values (e.g., "Less than 6 months" → 0, "More than 2 years" → 3).

B. Multi-Label Binarization for several columns 
- Split comma-separated entries (e.g., "Smartphone, Laptop").
- Applied MultiLabelBinarizer() to create binary columns for each device.
- Cleaned inconsistent entries (e.g., "Classical and melody" → "Classical, Melody").
- Applied MultiLabelBinarizer() to split multi-value entries.

C. One-Hot Encoding using pd.get_dummies() for Categorical columns 

D. Numeric Conversion
Converted to a count of exploration methods per user.

### Step 3: Data Loading
Final Refined Dataset:
Dropped intermediate variety columns (e.g., music_genre_variety).
Saved as refined_numbered_data.csv for model training.

## Analysis of Spotify User Behavior Models and Visualizations 
### A.SUPERVISED MACHINE LEARNING ETL
1- Model1: Subscriber vs Non-Subscriber Classification neural network model
2- Model2: Willingness to Subscribe Among Free Users Classification neural network model
3- Model3: Feature Importance for Willingness to Subscribe via the Random Forest classifier 
### B. 3 WAY ANALYSIS DEMOGRAPHIC INTERACTION CONTENT MAINLY UNSUPERVISED
#### Demographic Models
- Model1: Random Forest Classifier (Premium vs. Free) to Predict subscription status (binary) using demographics (age, gender, willingness).
- Model2: K-Means Clustering (Demographic Segments) to Group users into clusters based on demographic features.
#### Interaction Models
- Model3: Random Forest Classifier (Behavior-Based Premium Prediction) to Predict premium subscriptions using interaction features (usage period, devices, listening frequency).
- Model4: K-Means Clustering (Behavioral Segments)
Purpose: Segment users based on app interaction patterns (e.g., device usage, listening habits).
#### Content Models
- Model5: K-Means Clustering (Content Preferences) to  Group users by music genres, moods, and listening content.
- Model6: Random Forest Classifier (Willing vs. Resistant Free Users) to Predict willingness to subscribe among free users using content preferences (genre variety, mood diversity).





### C. SPOTIFY FEATURE ANALYSIS MAINLY UNSUPERVISED
1- 

## Ethical Considerations

1. **Data Privacy**: We have been careful to  use publicly available anonymized Spotify consumer data that will not compromise the listener's privacy, ensuring no sensitive user information was exposed.

4. **Cultural Considerations**: Music consumption varies across cultures, and our analysis of this Spotify dataset may reflect regional preferences not representative of global trends. We've attempted to avoid cultural generalizations in our analysis.

We believe that transparent data analysis can help consumers and industry professionals make more informed decisions while being mindful of these ethical considerations.Bias Mitigation was addressed by critically evaluating data sources for fairness and transparency, and by cleaning the dataset in a considerate manner, minimizing skewed representations. Transparency was maintained by thoroughly documenting all processes, allowing for clear auditability and reproducibility.

## Key Insights
Key Insights from Spotify Clustering Analysis
Target Demographics
- The majority of users fall within the 25–35 age range, making them a core segment for engagement and subscription strategies.
- Women make up the largest user group, but users identifying as Gender "Other" also represent a notable share and should be considered in inclusive marketing efforts.
Interaction Behavior
- Evening and night-time listening is the most common, suggesting opportunities to push content during off-peak hours.
 - Users who stream on devices other than smartphones (e.g., smart speakers, laptops) show a higher likelihood of becoming premium subscribers.
- Streaming during workouts, travel, or relaxation strongly correlates with subscription intent, suggesting these contexts drive value perception.
Content Consumption
- Music is the dominant content type, with far more engagement than podcasts.
- The genre "Melody" ranks highest in popularity among users across all clusters.
- There’s a strong case for offering exclusive music or playlist features to paying subscribers to boost satisfaction and retention.

### 3 WAY ANALYSIS DEMOGRAPHIC INTERACTION CONTENT MAINLY UNSUPERVISED
Key Insights from Models
Demographics Matter: Age and gender significantly influence subscription status.
Behavioral Patterns: Premium users tend to use more devices and have longer usage histories.
Content Drives Conversion: Users with diverse music preferences ("mood_variety") are more likely to convert to premium.

## Analysis
### 1. Spotify User Behavior Models - SUPERVISED MACHINE LEARNING ETL
## Overview
We built three machine learning models to understand Spotify user behavior, focusing on subscription patterns and willingness to pay for premium services. The models were trained on a dataset of 520 Spotify users with various demographic and usage characteristics.
This analysis provides Spotify with actionable insights to improve conversion rates and better understand their user base's subscription dynamics.

#### Model 1: Subscriber vs Non-Subscriber Classification
Accuracy: The neural network achieved approximately 75% accuracy in distinguishing between premium and free subscribers.
Key Findings:The model effectively learned patterns that differentiate paying subscribers from free users.
The 75% accuracy suggests there are clear behavioral and demographic differences between these groups.
The relatively high accuracy indicates the selected features (usage patterns, device types, music preferences) are good predictors of subscription status.
Business Implications:
Spotify can use this model to identify free users who exhibit characteristics similar to paying subscribers for targeted conversion campaigns.
The model helps understand what behaviors correlate with premium subscriptions, allowing Spotify to emphasize these features in marketing.
Further optimization needs to take place to decrease loss and increase accuracy

#### Model 2: Willingness to Subscribe Among Free Users
Accuracy: The model predicting willingness to subscribe among free users achieved about 82% accuracy.
Key Findings:
The model successfully identified patterns distinguishing willing from unwilling free users.
The slightly lower accuracy compared to Model 1 suggests willingness is more nuanced than actual subscription status.
Analysis of incorrect predictions could reveal interesting edge cases where user behavior contradicts their stated willingness.
Business Implications:
This model helps identify the most promising free users for conversion efforts with an accuracy of 77% . further optimization could be done to achieve decreased loss and increased accuracy.
Understanding characteristics of willing users allows for more precise targeting in marketing campaigns.
The model can help design incentives tailored to specific user segments.

#### Model 3: Feature Importance for Willingness to Subscribe
The Random Forest classifier identified these top predictors of willingness to subscribe:
Age Groups:

Top predictors of willingness to subscribe:
                       feature  importance
0            music_recc_rating    0.098509
17       Sadness or melancholy    0.056573
3                   Smartphone    0.045902
29                leisure time    0.041039
26             While Traveling    0.039487
41      spotify_usage_period_1    0.038576
28             Workout session    0.036329
5            number_of_devices    0.035398
25                 Study Hours    0.035255
19  Uplifting and motivational    0.031535

Based on these results, I would aproach understanding cunsumer behavior through ratings as a primary feature, second customer segments who prefer sadness or melancholy as genre, third, smartphone users, as well as those who listen during leisure time and while traveling. 

#### Recommendations for Spotify
Targeted Conversion Campaigns:
Focus on free users who match the "willing" profile identified by Model 2
Offer time-limited trials to users showing behaviors similar to paying subscribers
Product Development:
Enhance features popular among paying subscribers
Develop functionality that appeals to high-potential free users
Marketing Messaging:
Emphasize aspects valued by willing users in advertising
Create device-specific campaigns (e.g., smartphone-focused ads)

#### Limitations
The dataset (520 entries) is relatively small for deep learning models
Some categories had to be simplified during cleaning
The models don't account for external factors like pricing changes or competitor offerings
Cultural/regional differences weren't analyzed in this study

## Project Contributors
- Sade Beckles
- Patricia Daher
- Arisleyda Reyes

## Data Sources
 Kaggle Website: https://www.kaggle.com/code/arvindkhoda/spotify-user-behavior-dataset

## References for Data and Code

All code in Spotify.jpynb has been extracted from ChatGbt and Deep Seek, tweeked by Deepseek, and adjusted by the project contributors.
Chat Gbt Website: https://chatgpt.com/
Deep Seek Website: https://chat.deepseek.com/sign_in









