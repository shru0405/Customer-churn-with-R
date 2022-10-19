# Customer-churn-with-R
Customer Churn Analysis in R: Logistic, Classification Tree, XGBoost, Random Forest

This analysis focuses on the behavior of bank customers who are more likely to close their bank account. The goal here is to identify the behavior of customers through Exploratory Data Analysis and later on use predictive analytics techniques to determine the customers who are most likely to leave.


   1.Preprocessing & Data cleaning
   
   2.Exploratory Data Analysis (EDA)
   
   3.Feature selection & Chi-square Test
   
   4.Predictive Models
    a.Logistic Model
    b.Decison Tree
    c.Random Forest
    d.XGBoost
    
   5.Comparing Models’ Performance
   
   6.Feature Importance
   
  
   
   

CONTEXT AND DATA:
This analysis focuses on the behavior of bank customers who are more likely to leave the bank (i.e. close their bank account). The goal here is to identify the behavior of customers through Exploratory Data Analysis and later on use predictive analytics techniques to determine the customers who are most likely to churn (leave).

a.EDA
- Credit Score: from 350 to 850
- Geography:France, Germany and Spain
- Age: from 18 to 92
- Tenure: how long customer has stayed with the bank
- Balance: the amount of money available for withdrawal
- NumOfProducts: number of products customers use in the bank
- IsActiveMember: 0,1 -> Inactive, Active
- EstimatedSalary: Customer’s annual salary
- Exited: whether the customer has churned (closed the bank account) where 0,1 -> Stay, Churn

b.No NA`s:

![image](https://user-images.githubusercontent.com/111205197/196767629-57d556fa-da0f-44e4-8f29-813f451fcc6f.png)


c.Target [ Stay (0), Churn/Leave(1) ]:

![image](https://user-images.githubusercontent.com/111205197/196767734-41d3bb1a-73bb-41d7-b6aa-3f6a798f7634.png)


d.Distribution - Continuous Variables:

![image](https://user-images.githubusercontent.com/111205197/196767793-2d275727-8cd6-4d45-8705-a71d35408359.png)



 1.Age is a bit right-skewed
 
 2.Balance is fairly normal distributed
 
 3.Most credit scores are above 600, it is possible that high quality customers will churn

e.Correlation Matrix:

![image](https://user-images.githubusercontent.com/111205197/196767929-f2e63212-f0a6-4552-b0a0-8fc6dceca183.png)


  No high correlation between the continuous variables (i.e. no multicollinearity)
  We will keep all of the continuous variables

f.Distribution - Categorical Variables:

![image](https://user-images.githubusercontent.com/111205197/196768004-3b10ecbc-7a62-45b4-827a-4c57029ba094.png)


    1.More male customers than females
    2.Customers are mostly from France
    3.Most customers have the bank’s credit card
    4.Almost equal number of active and non-active members, not a very good sign
    5.Most customers use one or two kind of products, with a very few use three or four products
    6.Almost equal number of customers in different tenure groups, except 0 and 10.

g.Variables Dive:
1.AGE

![image](https://user-images.githubusercontent.com/111205197/196768102-c057b186-0204-4b74-a3c6-d2544e492799.png)


    1.Non-churned customers have a right-skewed distribution (tend to be young).
    2.Outliers above 60 years old - perhaps our stable customers.
    3.Churned customers are mostly around 40 to 50. 
    4.Clear difference is visible between these two groups.

2.BALANCE

![image](https://user-images.githubusercontent.com/111205197/196768215-049df4db-18f4-409e-99a4-ae85fe0cbbff.png)


    Distribution of these two groups is similar
    Surprisingly some non-churned customers have lower balance than churned customers

3.CREDIT SCORE

![image](https://user-images.githubusercontent.com/111205197/196768283-f7433add-d817-4606-9ecf-ced2cb40d307.png)

    Similar distribution
    Some customers with extremely low credit score (on the left tail) as well as with high credit score also churned
    Indicates that really low and high quality customer can easily churn than the average quality customer

4.CUSTOMER ESTIMATED SALARY

![image](https://user-images.githubusercontent.com/111205197/196768379-cb79dbc2-d814-47de-bfcc-422340e9025e.png)


    Both groups have a very similar distribution
    Esimated Salary might not be a very important infomation to decide if a customer will churn or not

5.CATEGORICAL VARIABLES

![image](https://user-images.githubusercontent.com/111205197/196768456-c876f3ac-470a-4259-b7c2-19fbdc9e91e1.png)


    Female are more likely to churn than male
    Customers in Germany are more likely to churn than customers in France and Spain
    In-active customers are more likely to churn than active
    HasCrCard may not be a useful feature as we cannot really tell if a customer has credit card will churn or not
    Customers in different tenure groups don’t have an apparent tendency to churn or stay
    Customers who use 3 or 4 product are extremely likely to churn

Feature selection by using chi-square test:

![image](https://user-images.githubusercontent.com/111205197/196768531-49d8b0b8-581a-478e-aaf4-50d318729120.png)


h.Preprocessing & fixing Class Balance for Train data set:

  1.Split the data using a stratified sampling approach (70/30 ratio).
  
  2.Inspect target distibution.
  
  3.Our dataset is not balanced as we have 80% for Stay and 20% for Leave/Churn.
  
  4.We will perform oversampling & undersampling to balance the data set via "ovun.sample" function.
  
  5.Now the data set is balanced, however, you see that we’ve lost significant information from the sample.
  
  6.To fix this we will do both undersampling and oversampling on this imbalanced data via the method = “both“
  
  7.In this case, the minority class is oversampled with replacement and majority class is undersampled without replacement.

i.Build and Train Predictive Models:

    Logistic Model
    Decison Tree
    Random Forest
    XGBoost

j.Compare model perfomance via ROC:

![image](https://user-images.githubusercontent.com/111205197/196768819-3cceac5a-7c3a-4c64-b542-1d6de9654089.png)

![image](https://user-images.githubusercontent.com/111205197/196769062-c596db68-6f73-4f72-9d69-909b5c4f8b5a.png)



h.Feature Importance:

![image](https://user-images.githubusercontent.com/111205197/196769123-008602b3-5e0c-422b-a532-48ccdb480656.png)

a.Age has the highest impact on customer churn. The bank can come up with some preferential policies to engage with these older customers.
   
b.The number of products used by the customer has an impact on customer churn. As shown in the exploratory analysis, people who use more than two products are very likely to churn.
   
c. Customers from Germany are more likely to churn compared to customers in France and Spain.The marketing team should focus on retaining German customers.
