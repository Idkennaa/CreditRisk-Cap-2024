# CreditRisk-Cap-2024
## Project Overview


In a flourishing economy, like Canada's, the maintainance of its credit system is quite important.  With the nation's residents accumulating credit worth over $2.3 trillion, nearly on par with its Gross Domestic Product (GDP) at $2 trillion, it is evident that the economy is largely driven by a credit/loan infrastructure.

The problem then arises for banks and finalncial institutions tomaintain such credit system and one of the biggest problems weakening the system is the default rates of debtors. Analysing the probability a debtor may default on their payments is quite necessary to these institutions. This project aims to create a model/models that predict a customer defaulting on their payment based on certain factors.

The model created would be very beneficial to financial institutions such as **banks, credit unions, peer to peer lenders & numerous lending organisations**. The model is designed to minimize losses to these companies proving the accessibility to these funds. The model would also benefit such institutions through
- Enhanced Informed Decision making
- Fair Treatment of Creditworthy borrowers
- Investor Confidence and Security


## Subject Data

The data been used is sourrced from Nubank, A prominent brazilian digital bank and one of Latin America's biggest Fintech. The dataset sourced from this company was initially part of a competition created by the company on the topic of Credit Risk analysis. This dataset encompasses 43 features for 45,000 clients. Certain data fields, including customer ID, location (state & ZIP code), and Profile Tags, are hashed out to safeguard client privacy. The relevance of these data fields to the ML Model's training will be further assessed.


## Proposed Solution

There will be three primary machine-learning techniques that will be applied to this dataset to create a model for prediction. The deign is seen to be aclassification problem as opposed to a regression problem therefor classifciation machine learning techniques will be employed. These techniques are seen to be:

- Logistic Regression method
- K - Nearest Neighbor method
- Decision Trees method

 #### 1. Logistic Regression
The logistic Regression Model will be suitable for the design of this model as it handles classification precisely, especially a bi-result classification such as this. The main problems with a Logistic regression model would be 
1. **Its feature of creating only hard decision boundaries**, 
2. **Its insensitivity to outliers and**  
3. **Its difficulty with working with interdependent featutes as most of the features used in the dataset may be interdependent**.
Due to these boundaries, other models will also be taken into consideration


 #### 2. K - Nearest Neighbor Method
The K- Nearest Neighbor method is another technique that will be applied to this dataset. With the nature of this technique creating grounds for faster training, ease of implementation and irregular relationships between features( non - parametric feature felationships), it will be asuitabe method to create a model with. Few shortcomings of this tecnique, such as **handling of irrelevant features** and **lack of precision in handling Noisy Data**, will also lead to its pairing with another machine learning technique to select a suitable & efficient model


 #### 3.  Decision Tree Method
 This is another Machine learning method that can be applied on this dataset for efficient results. Its interpretability and efficieny in high dimensional spaces would be reason for its selection during this analysis.


All three methods would be primarily analysed and the most efficient method will be selected.


## Benefits of Prediction Model
Leveraging machine learning and predictive modelling to assess creditworthiness and establish credit scores stands as a valuable asset for financial institutions engaged in credit product offerings. Studies indicate that implementing such models can result in a significant reduction of approximately 25% in losses associated with delinquent customers for banks. This would highly benefit these financial instutions as not only do they recuperate losses but it provides opportunity to venture into various other investment spaces witch current resources that have been saved.

## Dataset Description

The dataset is a sizeable amount of data having about 45,000 entries and 43 features. The data dictionary seen to explain the current features of the existing dataframe. The data was cleaned and irrelevant features were dropped to create a clean & releevant set of data to work on. Features that were dropped include :
- Channel
- Profile phone number
- Target fraud
- last amount borrowed
- ok since
- External data provider credit checks of last 2 years
  
Further Exploratory Data Analysis would be conducted on the data to create more insights.


## Exploratory Data Analysis

It was seen that the data had no duplicate values but only presence of null values so the null values were accounted for. The features;
- 'Target_fraud'
- 'Last_amount_borrowed'
- 'Last_borrowed_in_months'
- 'external_data_provider_credit_checks_last_2_year' &
- 'ok_since'

all have more than 50% of their features missing and were eventually dropped. 

We also see that the **'external_data_provider_credit_checks_last_2_year'** has only one value being 0. Therefore this would not impact the decisions made by the model and would provide more grounds why this feature has to be dropped. 

Other actions that were taken upon the data were:

- The 'lat_lon column" feature would then be broken into latitude(lat) and longitude(lon) seperate features and the exist lat_lon feature would be dropped
- The column 'Channel' is seen to have just one unique value and would therefore have no effect on our model so it would be dropped.
- The columns 'Id' and 'Profile Phone number' would also have no relevance to our dataset, with phone number not providing any intrinsic value to the model and id's being a unique identifier and not providing intrisic value as well, therefore it would be dropped as well.
-  The presnent infinite values, and the outliers, were replaced with a null value.
- An imputer function was applied to the null values to fill  the most occuring value for the categorical columns and the median values for the numerical columns.

The dataset was then concluded to be clean having a sixe of **45,000 entries and 36 features**






