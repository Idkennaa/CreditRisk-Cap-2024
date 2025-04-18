# CreditRisk-Cap-2024
## Project Overview


In a flourishing economy, like Canada's, the maintainance of its credit system is quite important.  With the nation's residents accumulating credit worth over $2.3 trillion, nearly on par with its Gross Domestic Product (GDP) at $2 trillion, it is evident that the economy is largely driven by a credit/loan infrastructure.

The problem then arises for banks and financial institutions tomaintain such credit system and one of the biggest problems weakening the system is the default rates of debtors. Analysing the probability a debtor may default on their payments is quite necessary to these institutions. This project aims to create a model/models that predict a customer defaulting on their payment based on certain factors.

The model created would be very beneficial to financial institutions such as **banks, credit unions, peer to peer lenders & numerous lending organisations**. The model is designed to minimize losses to these companies proving the accessibility to these funds. The model would also benefit such institutions through
- Enhanced Informed Decision making
- Fair Treatment of Creditworthy borrowers
- Investor Confidence and Security


## Subject Data

The data been used is sourced from Nubank, A prominent brazilian digital bank and one of Latin America's biggest Fintech. The dataset sourced from this company was initially part of a competition created by the company on the topic of Credit Risk analysis. This dataset encompasses 43 features for 45,000 clients. Certain data fields, including customer ID, location (state & ZIP code), and Profile Tags, are hashed out to safeguard client privacy. The relevance of these data fields to the ML Model's training will be further assessed.


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
The K- Nearest Neighbor method is another technique that will be applied to this dataset. With the nature of this technique creating grounds for faster training, ease of implementation and irregular relationships between features( non - parametric feature felationships), it will be a suitabe method to create a model with. Few shortcomings of this technique, such as **handling of irrelevant features** and **lack of precision in handling Noisy Data**, will also lead to its pairing with another machine learning technique to select a suitable & efficient model


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
### A. Cleaning the Data

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



### B. Statistical Exploratory Data Analysis


#### Data Preparation

To begin with, we encoded the categorical data to ensure a suitable dataset for proper analysis. Encoding the categorical variables was a crucial step in the data exploration phase to understand the relationships between the independent variables and the dependent variable (Target_default).

#### Data Exploration
One effective way to visualize these relationships is by using a heatmap to display the correlation matrix. The correlation matrix shows the pairwise correlation coefficients between variables in the dataset. From the heatmap, we observed that the dependent variables are weakly correlated with the dependent variable.

### Key Observations
- The highest correlated variable to the dependent variable is 'facebook_profile_encoded', which is interesting compared to other independent variables.
- Features such as 'risk_rate' and 'score_3' (one of the credit scores) have low correlation with the dependent variable, despite expectations of significant impact. Only 2 out of the 6 scores have a relative significance to the dependent variable.
- 'Marketing Channel' has a higher impact on the dependent variables compared to other features.

#### Pair Plot Analysis

Key takeaways from the pair plot analysis include:

- No clear or distinct relationship between most features.
- The features appear to be categorical, which could explain the lack of apparent relationships.
- Notable relationships are observed between risk rates and credit scores, which intuitively makes sense as higher credit scores are positively correlated with lower risk rates.

#### Histogram Analysis
Examining the histograms of the features revealed several issues:

- Presence of Outliers: Notably in the 'income' and 'credit_limit' features.
- Skewness: Observed in several features, indicating asymmetric distributions.
- High Frequency of Zero Values: Found in certain features, reflecting the non-occurrence of specific events.

These issues were addressed in subsequent analyses. The skewness of the data has been accounted for, and features with outliers and high-frequency zero values have been analyzed and will be addressed in modeling.

#### Feature Relationships
##### Credit Limit and Income

To analyze relationships between key features, we examined the correlation between credit limit and income. Surprisingly, income does not significantly impact the credit limit, as higher income does not necessarily equate to a higher credit limit.

##### Credit Limit and Defaulted Loans

Next, we analyzed the relationship between credit limit, the number of defaulted loans, and reported income. It was observed that reported income does not significantly affect the credit limit, similar to the general income.

Additionally, the number of defaulted loans has little to no effect on the credit limit. Since about 99% of the loans are defaulted, this feature will be dropped.

### Conclusions from Exploratory Data Analysis

The preliminary data analysis reveals:

- Weak correlations between the target variable and other features.
- Many features exhibit low correlations with the target variable.
- An unbalanced class distribution, with almost 90% of the data in one class.
- Some features, such as social media tags and latitude, show unexpectedly high correlations with the dependent variables.
- Existing independent features exhibit irregularities that need to be addressed.
- Surprisingly, certain variables appear as the most correlated ones.
- The number of defaulted previous loans significantly influences the credit limit.
- Higher reported and regular incomes do not necessarily lead to higher credit limits.
- The variable "Number of issues" appears important, but its exact influence remains unclear without a deeper understanding of its definition and impact.




## Machine Learning Model

### A. Model Building

We then proceed to building models using the data for thorough analysis and prediction. From the feature importances shown below, we can identify the features that contribute most to the target variable.


[0.0290253,  0.02872985, 0.02914402, 0.02838829, 0.03196067, 0.02728252,
 0.0277374,  0.01034964, 0.00148517, 0.0273988,  0.02743799, 0.03106131,
 0.02553168, 0.01706916, 0.0302387,  0.02824109, 0.00148684, 0.03040322,
 0.03598842, 0.03860559, 0.02846503, 0.03730605, 0.02977799, 0.02916212,
 0.0190344,  0.02885388, 0.02895327, 0.0,        0.03029725, 0.01777521,
 0.03341823, 0.02265902, 0.02944051, 0.02635683, 0.0438085,  0.02835187,
 0.03034965, 0.02842452]

 
### B. Feature Selection
To focus on the most impactful features, we created a dataset that includes the top 20 features with the highest importances. This step will help streamline our analysis and improve model performance.

### C. Addressing Class Imbalance
To mitigate class imbalance observed in the EDA section, we employed random undersampling to achieve a balanced class distribution. Subsequently, we visually examine the distribution of the sampled data to ensure proper representation.

### D. Model Evaluation
We used a function designed to evaluate recall scores for different machine learning models. These scores reflect how well each model identifies all true positives of the target default variable. We'll use this function to analyze the performance of the following models:

Random Forest Classifier
Decision Tree Classifier
SGD Classifier
Logistic Regression Classifier
XGB Classifier
LGBM Classifier
This evaluation will provide insights into how effectively each model can correctly identify instances of the target variable, assessing their overall performance in this specific context.


      
RandomForestClassifier     0.096292
DecisionTreeClassifier     0.261855
SGDClassifier              0.000000
SVC                        0.000000
LogisticRegression         0.000000
XGBClassifier              0.149473
LGBMClassifier             0.144327

### E. Model Selection and Optimization
After evaluating different modeling techniques to determine their performance scores, we selected the Decision Tree classifier, which achieved the highest recall score. Next, we refined its settings using grid search to find the optimal configuration.

### F. Accuracy Assessment
Given the dataset's imbalance, the metrics generated may not accurately reflect real-world performance. Therefore, it's crucial to proceed with assessing the model's accuracy as a straightforward evaluation metric.



## Conclusion & Findings

### Performance Report
From the classification results, the following insights were derived from the model:

- Class 0 (Non-Default): The model exhibited higher precision and accuracy but lower recall, indicating that while it correctly identified non-defaults most of the time, it missed some actual non-defaults.
- Class 1 (Default): The model demonstrated lower precision but higher recall, suggesting that it more comprehensively identified defaults but also incorrectly labeled some non-defaults as defaults.
- Macro Average: Provided equal weight to both classes.
- Weighted Average: Considered the support (number of instances) for each class.
The model was more accurate in predicting non-credit defaults with a score of 69%, compared to accurately predicting credit defaults with a score of 57%.

### Model Selection
Among the models tested, the Decision Tree Classifier emerged as the optimal choice based on the dataset's metrics.

### Model Enhancement
The model could have been enhanced through various adjustments such as exploring different encoding techniques, experimenting with alternative data balancing methods, and engaging in feature engineering. These steps underscored the complexity of the problem and highlighted the substantial effort required to achieve optimal performance.

### Future Work
While the initial baseline was surpassed and satisfactory results were achieved for this project, there was still considerable room for improvement. The model occasionally approved credit for individuals who may not qualify while also rejecting deserving applicants. This highlighted the ongoing challenge of achieving a more accurate and fair credit decision process.

