# Customer Churn Rate for Telecom Sector

## Introduction
- Customer churn, also known as customer attrition, is the process where customers stop doing business with a company or service.
- In the context of the telecom industry, customer churn refers to subscribers discontinuing their service with a telecom provider, either by switching to another provider or by stopping the service altogether.

- Reasons that may results for Churn:

   1. Customer Service: Poor customer service can lead to dissatisfaction and drive customers to switch providers.
   2. Competitive Offers: Competitors offering better pricing, improved service quality, or attractive packages can lure customers away.
   3. Network Quality: Poor network coverage or frequent service disruptions can lead to customer dissatisfaction.
   4. Billing Issues: Inaccurate billing or perceived overcharging can prompt customers to leave.
   5. Technological Advancements: Customers may switch to providers offering the latest technology (e.g., 5G services).

- Statistics and Facts:

   1. Churn Rate: The global average churn rate for telecom companies ranges from 1.5% to 3% per month. This means that annually, 18% to 36% of customers may leave.
   2. Cost of Churn: It is estimated that acquiring a new customer can cost 5 to 25 times more than retaining an existing one. For telecom companies, this underscores the importance of minimizing churn.
   3. Customer Loyalty Programs: Many telecom companies implement loyalty programs to reduce churn. For instance, offering discounts, exclusive offers, or reward points can help retain customers.

## Objective
- Analyze the reasons behind customer churn to gain a comprehensive understanding of why customers leave.
- Identify patterns and trends in churn behavior through data analytics.
- Finding the most suitable model to predict customer churn.

## Dataset 
- We obtained the data from https://www.kaggle.com/datasets/blastchar/telco-customer-churn
- Each row represents a customer, each column contains customer’s attributes described on the column Metadata. The data set includes information about:
   1. Customers who left within the last month – the column is called Churn
   2. Services that each customer has signed up for – phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV and movies
   3. Customer account information – how long they’ve been a customer, contract, payment method, paperless billing, monthly charges, and total charges
   4. Demographic info about customers – gender, age range, and if they have partners and dependents

## Exploratory Data Analysis
1. Churn Distribution

   ![image](https://github.com/devangisingh/Customer-Churn-Rate-for-Telecom-Sector/assets/80507579/e576317e-f4f9-4569-a0c4-1ea530c6175c)

   - 26.54% customers have churned to another competitors & have stopped using the subscriptions.

3. Churn Distribution and Gender

   ![image](https://github.com/devangisingh/Customer-Churn-Rate-for-Telecom-Sector/assets/80507579/8df6ec1c-925e-4dfc-8da2-e3de4fa05e9b)

   - Out of total 1869 customers churned, 939 are Female customers & 930 are Male customers

5. Churned Customers w.r.t Gender for Contract
   
   ![image](https://github.com/devangisingh/Customer-Churn-Rate-for-Telecom-Sector/assets/80507579/ab8fe3a6-5d37-45a6-9116-0162d7f64165)

   - About 1655 out of 1869 churned customers (i.e.89% 

7. Churn Distribution and Payment Method

   ![image](https://github.com/devangisingh/Customer-Churn-Rate-for-Telecom-Sector/assets/80507579/b24a45f7-56ed-4a96-a6f0-cf4c1f8ff9ca)


## Modeling Process Used

- Logistic Regression with summary of the model
  Below is the summary of a logistic regression model (glm) that predicts customer churn based on TotalCharges and MonthlyCharges.
  
  **glm(formula = Churn ~ TotalCharges + MonthlyCharges, family = binomial, data = tc_cleaned)**
  
Summary:
   1. Churn is the dependent variable.
   2. TotalCharges and MonthlyCharges are the independent variables.
   3. The logistic regression model indicates that both TotalCharges and MonthlyCharges are significant predictors of customer churn. The model shows that higher TotalCharges are associated with a lower probability of churn, while higher MonthlyCharges are associated with a higher probability of churn. The significance codes indicate strong evidence against the null hypothesis (that the coefficients are zero), suggesting these predictors have a meaningful impact on the likelihood of customer churn.
  
- Logistic Regression Model
Logistic Regression is a statistical method used for predicting the probability of a binary outcome. In the context of predicting customer churn in the telecom sector, the binary outcome typically represents whether a customer will churn or not. We performed univariate logistic regression, which involves examining the relationship between one predictor variable and the binary outcome variable (churn). We also tried creating a logistic model displaying summary of the model using different predictor variable and the binary outcome variable.

![image](https://github.com/devangisingh/Customer-Churn-Rate-for-Telecom-Sector/assets/80507579/d3d28eec-e505-4b4f-8961-36e805211137)

- Interpretation:
  
The curve indicates a positive relationship between Monthly Charges and the probability of churn. As Monthly Charges increases, the probability of churn also increases.
At lower values of Monthly Charges, the probability of churn is lower. As the monthly charges increase, the probability of churn rises significantly.
This suggests that customers with higher monthly charges are more likely to churn compared to customers with lower monthly charges.

- Implications:
   1. Cost Sensitivity: Customers with higher monthly charges might be more sensitive to costs and could be considering switching to cheaper alternatives.
   2. Targeting High Spend Customers: Efforts to reduce churn may need to focus more on customers with higher monthly charges, as they are at higher risk of leaving.
   3. Service Value: The company might need to ensure that higher monthly charges are justified by the value provided to these customers, potentially through enhanced services, benefits, or loyalty programs.
 

