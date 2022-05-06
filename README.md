# Bank-Term-Deposit - ML Project
- Problem- Statement:
The data is related with direct marketing campaigns at a banking institution. The marketing campaigns were based on phone calls. Often, more than one contact to the same client was required, in order to access if the product (bank term deposit) would be ('yes') or not ('no') subscribed.
"Just want to see some xchanges" 

- Goal:
The classification goal is to predict if the client will subscribe (yes/no) a term deposit (variable y).
- Data set has a 10 categorical variable and 10 Numerical Variable varibable

Categorical:
job, marital, education, default, housing , contact, month, poutcome, loan, day_of_week
     
Numerical: 
age, pdays, day, duration, campaign, previous, emp.var.rate, cons.conf.idx, euribor3m, employed
# Did your profile Subscribe versus unsubscribe very well?    
- most of the people age between 30 to 50 but students and retired are more likely to subscribe.
- Job attribute: we can see the count of 'admin is higher than the other. Also, the count for 'blue-collar' is noticeable, and blue-collar and white-collar(manager,admin) job type   people are more likely to subscribe.    
- A high proportion of non-defaulters corresponds to the total of term deposit takers. It seems that it makes good sense that people with credit do not want to subscribe to a new   bank offer.
- More people with higher education degrees were subscribed. Proportional relationship. More secondary profiles mean more term deposits were sold.
- Count of married and single clients were more and they were showing more interest in bank term deposits than divorced.
- The clients who don't have taken any personal loans have subscribed to a term deposit with more than 50% chances.
- Customers who previously accepted the deposit tends to accept the deposit.
- As days Distribution histogram skewed to the right, Most of the clients were not previously contacted those are considered to be new clients.
- The success of the previous marketing campaign is not noticeable as we can see in the graph. Poutcome doest not exist for most of the customers and previously have not been       contacted 
- All the Categories in each categorical variable have out of proportion 'yes' compared to 'no' for term deposits subscription.
  Previous campaign calls failed to get customers to subscribe to bank term deposits.
- In- months of March, September, October, and December, the client show high interest in depositing. In the month of may, records are high but the client interest ratio is very     less

# Data Prepration and Process:
 
- Dataset contains two datatypes: int64 (numerical), float64(numerical) and object, knowing datatype helps us with using correct                                     operations on correct data columns later on
- Null values:  There is no null value in NaN form  but it contains lots of unknown values and dulicate records.
- Drop dulpicate recods to clean and organize dataset.
- Replace all unknown with NaN value.
- Missing Value available in dataset :  0.8 % in job , 0.19 % in marital status , 4.19 % in education, and 20.87 % in default     column 
- As misssing value ration is very less compare to dataset, decided to replace with mode value(as all are categorical).
- from the visulization(boxplot) some outliers are found in Age, Duration, Pdays, campaign columns
- the contact variable and day_of_week are omitted because the contact method (cellular, telephone) does not provide much         relevant information. 

Feture Engineering: 
- Machine learning algorithms cannot work with categorical data directly.Categorical data must be converted to numeric
- convert all categorical fetures in to numeric using one hot encoding method.
- for job and education, I made cluster where same category combine together to avoid curse of dimensionality(Increasing the         number of features means that we might encounter cases of not having enough observations for each feature combination)
- Convert all categorical variable in to numeric variable with help of one hot encoding method. 

Build the model
- Given data is highly imbalance so, applied SMOTE oversamplaing Techniques.
- Build Logistic Regression and Decision Tree model.


# Final recommendation 
(From the Decision Tree Fetuare Importance)
- The most important features to determine is poutcome, if a new customer will accept the deposit who accepted it previously(>37%)
- Second most important feature is month. need to consider best season for the campaign promotion. For example, In given campaign, We saw that the month of highest level of marketing activity was the month of May. However, this was the month that potential clients tended to reject term deposits offers. For the next marketing campaign, it will be wise for the bank to focus the marketing campaign during the months of March, September, October and December.
- Third important feature is poutcome. one of the possibility is they have not been contacted previously. Those are considered new clients. Approaching them in proper way might lead to increase in the business.



