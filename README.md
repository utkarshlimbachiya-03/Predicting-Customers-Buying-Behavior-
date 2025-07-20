**Predicting-Customers-Buying-Behavior**

This project aims to analyze airline customer booking behavior and predict the likelihood of booking completion using classification models.
The dataset includes demographic, travel-related, and preference-based features of airline customers.

**Objective**

To explore key behavioral and travel-related variables that drive extra baggage purchases, and build a predictive model that help airlines target the right customers with offers and upsell opportunities.

**Dataset Summary**

- *Source*: 'customer_booking.csv'
- *Records*: '50,000+'
- *Target Variable*: 'want extra baggage'

**Steps Performed**

**Exploratory Data Analysis (EDA)**
- Used IQR method to detect outliers in:
  - 'purchase lead'
  - 'length of stay'
- Removed or capped outliers by the upper bound. The outliers is being handled logically and statistically. Making sure that the datapoints as matched with the real-world booking system.

- Analyzed 100% of dataset structure, null values, and data types.
- Explored class imbalance on the target variable.
- Created new features like, 'urgency type' (To know the customer booking urgency) from the purchased lead and day type ( weekday and weekend flights).

**Feature Analysis**
- Used Hypothesis testing (Point-Biserial correlation for numerix feature (With binary features).
- Applied Ch-Square and Cramer's V for the categorical features.
- Identified the features with most related to the target variable (wants extra baggage).
- This ensured statistically significant features towards the target variable.

**Encoding pipelines based on Model-Specific**
*Logestic Regression*
- One Hot encoding is used to avoid implying any order between categories. And ensuring the model treats each category independently.
- Dropped dummy variables to prevent multicollinearity ( When two variables are highly correlated with each other). The Logisitic Regression estimates coefficients (weights) for each feature to explain the target, the dummy variable is being 'dropped'.

*Random Forest*
- In Random forest the tress don't suffer from multicollinearity and doesn't needto estimate coefficients it give best split in every features ( May because of non-linearity).

  **Evaluation**
  - Confusion Matrix and Classification Report.
  - Feature Importance visualization.
    
**Result**
*Logistic Regression:*
- Train Accuracy: 69.4%
- Test Accuracy: 68.7%

**Random Forest**
- Train Accuracy: 71.5%
- Test Accuracy: 69.6%

**Feature Insights**
*Logestic Regression*
The most important factors with coustomers wants extra baggage are:
1. Length of stay
2. Preferred seat
3. Number of passengers
4. In-fights meals
5. Some of routes
6. booking complete
7. booking from 'Japan'
8. Standard booking (Normal booking (1-3 months of duration).

*Random Forest*
The most important factors with coustomers wants extra baggage are:
1. Length of stay
2. In-fights meals
3. Preferred seat
4. Number of passengers
5. booking complete
6. booking from 'Japan'
7. booking from 'Malaysia'
8. some routes
 
**Tools Used**

- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
- Imbalanced-learn (for SMOTE)



**Key Findings**
- Random Forest is handling slightly better, Precision shows 83% indicating most predicted buyers will actually purchase baaggae. And 68% of Recall shows model captures a majority buyer but still need more to come.
- Long-stay travelers, group bookings, and premium customers (meals, seats) are most likely to purchase baggage.
- Airlines can target these customers with discounts or bundled baggage offers to increase revenue, especially during vacation seasons (summer).
