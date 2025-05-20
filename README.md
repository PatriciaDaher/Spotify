# Project4-Spotify 
# Spotify Machine Learning Analysis and Problem Solving


## Project Overview

Something amazing about spotify******************
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
├── 3 Way Analysis Demographic Interaction Content.ipynb  # Jupyter notebook for demographic analysis
├── Spotify Feature Analysis.ipynb   # Jupyter notebook for feature analysis
├── Supervised Machine Learning and ETL.ipynb  # Jupyter notebook for ML and ETL processes
├── FeatureImportance.h5             # Saved model weights (HDF5 format)
├── subscribervsunsubscriber.h5      # Saved model weights (HDF5 format)
└── Willingnesstosubscribe.h5        # Saved model weights (HDF5 format)
```
## How to Use and Interact with the Project
Open each Jupyter notebook and click run all

## Technologies and libraries Used :


## Data Used 


## Data Sourse 
Kaggle: link ******************

## ETL 


2. **Data Cleaning and Transformation**: Used Word, Excel, Python and Pandas to create a clean csv:**************************
   - Cleaned csv by removing irrelevant lots, converting currency from HKD to USD, and Splitting the Estimate column into Lower Estimate and Higher Estimate. ​***********
   - Created a price category classifying sales as passed, below, within, or above estimate
3. **Database Creation**: Stored the cleaned DataFrame in a SQLite database****************


## Database
The Sqlite database contains auction data with information about lots number, brand, type, color, leather, hardware, year manufactured, estimates, and realized prices.**********


## Visualizations & Interactions  (HTML Content)   

2- **Analysis Dropdown Menu displaying a total of 9 charts**
Visualizations 1: General Sale Performance
b- Bar Chart 1 Lot Sales Relative to Estimates
c- Bar Chart 2 Top 10 Most Expensive Handbags
Visualizations 2: General Sale Results by BRAND
	a- Bar Chart 1: Total Sales By Brand 
	b- Bar Chart 2: Average Sales by Brand
Visualizations 3: Average prices by Brand and Year
	a- Plot Chart 1: Average Price Results by Brand per Year Manufactured
Visualizations 4: Price results by COLOR
	a- Bar Chart 1: Average Auction Price by Color
	b- Plot Chart 2: Price Realized for Each Bag by Brand Based on Color
	b- Plot Chart 3: Average Price Realized by Brand Based on Color
Visualization 5: Leather
   a- Bar Chart 1: Average Price by Leather type
*******************************************

## Ethical Considerations


Our project raises several ethical considerations related to data usage:

1. **Data Privacy**: We have been careful to  use publicly available anonymized Spotify consumer data that will not compromise the listener's privacy, ensuring no sensitive user information was exposed.

4. **Cultural Considerations**: Music consumption varies across cultures, and our analysis of this Spotify dataset may reflect regional preferences not representative of global trends. We've attempted to avoid cultural generalizations in our analysis.

We believe that transparent data analysis can help consumers and industry professionals make more informed decisions while being mindful of these ethical considerations.Bias Mitigation was addressed by critically evaluating data sources for fairness and transparency, and by cleaning the dataset in a considerate manner, minimizing skewed representations. Transparency was maintained by thoroughly documenting all processes, allowing for clear auditability and reproducibility.

## Key Insights
*************************************


## Technologies Used
- **Database**: **********
- **Backend**: **************
- **Visualization**: ********************
- **Frontend**: ****************

## Project Contributors
- Sade Beckles
- Patricia Daher
- Arisleyda Reyes

## Data Sources
Christie's Auction House website: 
Auction data specifically from Christie's Hong Kong March 2025 Handbags Online sale titled : Handbags Online: The Hong Kong Edit https://onlineonly.christies.com/s/handbags-online-hong-kong-edit/lots/3721)
**********************************************************

## References for Data and Code
All data in the csv files and database has been extracted from 

Christie's auction results for Christie's Hong Kong March 2025 Online Handbags sale titled : Handbags Online: The Hong Kong Edit  https://www.christies.com/en/results
*****************************************************************

All code in Spotify.jpynb has been extracted from ChatGbt and Deep Seek, tweeked by Deepseek, and adjusted by the project contributors.
Chat Gbt Website: https://chatgpt.com/
Deep Seek Website: https://chat.deepseek.com/sign_in









