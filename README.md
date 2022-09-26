# Customer-churn-with-R
Customer Churn Analysis in R: Logistic, Classification Tree, XGBoost, Random Forest

This analysis focuses on the behavior of bank customers who are more likely to close their bank account. The goal here is to identify the behavior of customers through Exploratory Data Analysis and later on use predictive analytics techniques to determine the customers who are most likely to leave.


   1.Preprocessing & Data cleaning
   
    a.Split the data using a stratified sampling approach (70/30 ratio)
    b.Inspect target distibution.
    c.Dataset is not balanced as we have 80% for Stay and 20% for Leave/Churn.
    d.Performing oversampling & undersampling to balance the data set via "ovun.sample" function.
    e.Balanced dataset has lost significant amount of information while sampling.
    f.To fix this,undersampling and oversampling needs to be done on this imbalanced data via the method = "both".
    g.In this case, the minority class is oversampled with replacement and majority class is undersampled without replacement.

   2.Exploratory Data Analysis (EDA)
   
   3.Feature selection & Chi-square Test
    
   4.Predictive Models
   
    a.Logistic Model
    b.Decison Tree
    c.Random Forest
    d.XGBoost
    
   5.Comparing Models’ Performance
    
   6.Feature Importance
   
   Feature Importance is similar based on the two approaches:
   
   a.Age has the highest impact on customer churn. The bank can come up with some preferential policies to engage with these older customers.
   
   b.The number of products used by the customer has an impact on customer churn. As shown in the exploratory analysis, people who use more than two products are very likely to churn.
   
   c. Customers from Germany are more likely to churn compared to customers in France and Spain.The marketing team should focus on retaining German customers.

