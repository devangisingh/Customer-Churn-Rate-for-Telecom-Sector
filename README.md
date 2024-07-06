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

## Methodlogy
   1. **Define Objectives:** The objectives of the churn prediction model should be defined and understanding what the business hopes to achieve, such as reducing churn, identifying key factors influencing churn, and targeting specific customer segments.
   2. **Data Collection:** Gather relevant data from various sources, including customer demographics, usage patterns, customer service interactions, and historical churn records.
   3. **Data Preprocessing:** Cleanse the data by handling missing values, outliers, and inconsistencies.
   4. **Exploratory Data Analysis (EDA):** Conducting exploratory data analysis to understand the characteristics of the dataset. Identify patterns, correlations, and potential variables that may influence churn.
   5. **Tools:** Microsoft Power BI, Microsoft Excel, Google Collab
   6. **Programming Language:** R Programming
   7. **Libraries:** Python (Pandas, MatplotLib, Seaborn), Random Forest

## Exploratory Data Analysis
1. Churn Distribution

   ![image](https://github.com/devangisingh/Customer-Churn-Rate-for-Telecom-Sector/assets/80507579/e576317e-f4f9-4569-a0c4-1ea530c6175c)

   - 26.54% customers have churned to another competitors & have stopped using the subscriptions.

3. Churn Distribution and Gender

   ![image](https://github.com/devangisingh/Customer-Churn-Rate-for-Telecom-Sector/assets/80507579/e31c2c69-edfa-43d2-923f-c8b62251cbe1)

   - Out of total 1869 customers churned, 939 are Female customers & 930 are Male customers

5. Churned Customers w.r.t Gender for Contract
   
   ![image](https://github.com/devangisingh/Customer-Churn-Rate-for-Telecom-Sector/assets/80507579/110bc9e5-f344-4654-a02a-da520998e3ad)

   - About 1655 (842 Female + 813 Male) out of 1869 churned customers with Month-to-Month Contact considered to move out or stop using the services. 

7. Churn Distribution and Payment Method

   ![image](https://github.com/devangisingh/Customer-Churn-Rate-for-Telecom-Sector/assets/80507579/107cff0a-d034-41d3-b12b-841252283dbe)

   - Customers who have churned more likely opted for Electronic Check as the Payment Method.

## Modeling Process

**Logistic Regression Model**:
   
Logistic Regression is a statistical method used for predicting the probability of a binary outcome. In the context of predicting customer churn in the telecom sector, the binary outcome typically represents whether a customer will churn or not. We performed univariate logistic regression, which involves examining the relationship between one predictor variable and the binary outcome variable (churn). We also tried creating a logistic model displaying summary of the model using different predictor variable and the binary outcome variable.

i) **Logistic Regression with summary of the model**
   
  Below is the summary of a logistic regression model (glm) that predicts customer churn based on TotalCharges and MonthlyCharges.
  
     glm(formula = Churn ~ TotalCharges + MonthlyCharges, family = binomial, data = tc_cleaned)
  
Summary:
   1. Churn is the dependent variable.
   2. TotalCharges and MonthlyCharges are the independent variables.
   3. The logistic regression model indicates that both TotalCharges and MonthlyCharges are significant predictors of customer churn.
   4. The model shows that higher TotalCharges are associated with a lower probability of churn, while higher MonthlyCharges are associated with a higher probability of churn. The significance codes indicate strong evidence against the null hypothesis (that the coefficients are zero), suggesting these predictors have a meaningful impact on the likelihood of customer churn.
      
  
ii) **Univariate Logistic Regression**

![image](https://github.com/devangisingh/Customer-Churn-Rate-for-Telecom-Sector/assets/80507579/d3d28eec-e505-4b4f-8961-36e805211137)

- **Interpretation:**
  
The curve indicates a positive relationship between Monthly Charges and the probability of churn. As Monthly Charges increases, the probability of churn also increases.
At lower values of Monthly Charges, the probability of churn is lower. As the monthly charges increase, the probability of churn rises significantly.
This suggests that customers with higher monthly charges are more likely to churn compared to customers with lower monthly charges.

- **Implications:**
   1. Cost Sensitivity: Customers with higher monthly charges might be more sensitive to costs and could be considering switching to cheaper alternatives.
   2. Targeting High Spend Customers: Efforts to reduce churn may need to focus more on customers with higher monthly charges, as they are at higher risk of leaving.
   3. Service Value: The company might need to ensure that higher monthly charges are justified by the value provided to these customers, potentially through enhanced services, benefits, or loyalty programs.
 
**Random Forest**

Random Forest is a powerful machine learning algorithm that can be effectively used for predicting customer churn rate in the telecom sector. Random Forest is an ensemble method that builds multiple decision trees and combines their predictions. It is known for its robustness, ability to handle non-linearity, and resistance to overfitting.

The output shows the "**Accuracy: 0.808329389493611**" which means that approximately 80.83% of the instances in validation set were predicted correctly by the random forest model. A higher accuracy generally indicates a better-performing model.

The below snapshot is a variable importance plot from a random forest model. This plot shows the importance of each variable in predicting the target variable, as measured by the mean decrease in the Gini impurity.

![image](https://github.com/devangisingh/Customer-Churn-Rate-for-Telecom-Sector/assets/80507579/da97b08f-7680-461e-bbf7-4730e737a5e9)

Interpretation:

In this plot, **TotalCharges** is the most important variable, followed by MonthlyCharges, tenure, and customerID. Variables like PhoneService, StreamingTV, and StreamingMovies have lower importance scores, indicating they are less critical for the model's predictions.

## Overall Outcome - Microsoft Power BI Dashboard 

Using Microsoft Power BI is used to create interactive visualizations, reports and dashboards for predictive analytics for customer churn in the telecom sector. Power BI offers a user-friendly interface, making it accessible to business users and analysts.

[TelecomChurnDashboard.pdf](https://github.com/user-attachments/files/16115826/TelecomChurnDashboard.pdf)

- **Conclusion:**

The above attached Power BI dashboard provides insights into customer churn for a telecom company. The dashboard displays various metrics and visualizations to help the company understand the factors contributing to customer churn and identify areas for improvement.

- **Key Metrics:**
  
i. Total Customers: 7,043

ii. Male Customers: 3,555

iii. Female Customers: 3,488

iv. Customers Churned: 1,869 (26.5% of total customers)

v. Total Revenue: $16.1 million

- **Customer Segmentation:**
   1. **Payment Method:** The chart shows the distribution of total customers across different payment methods (electronic check, mailed check, bank transfer & credit card). Customers prefer Electronic check payment mode more than other three payment methods. 
   2. **Contract:** The chart segments customers by contract type. Among those with contracts, 3.9k customers opted for Month-to-month contracts & have the highest churn rate (88.55%), followed by one-year contracts (8.88%) and two-year contracts (2.57%).
   3. **Internet Service:** The chart analyzes churn rate based on whether customers have internet service and its type (DSL, Fiber Optic). Customers with no internet service have the lowest churn rate (6.05%). Fiber Optic internet service has a higher churn rate (69.40%) compared to DSL (24.56%).
   4. **Monthly Charges:** The chart shows the relationship between monthly charges and churn where the reason for 55% of customer to churn is Monthly Charges.
   5. **Tech Support:** The chart suggests that customers who does not have tech support churn at a higher rate(41.4%).
   6. **Online Security:** Customers who does not use online security features seem to have a higher churn rate.

Overall, Power BI dashboard helps the telecom company identify several factors potentially affecting customer churn. By analyzing these metrics, the company can develop targeted strategies to reduce churn, such as offering better deals for payments, promoting long-term contracts with attractive benefits, focusing on improving customer satisfaction and potentially considering additional online security features.

## Recommendation

   1. **Service Customization:** Enhanced services and customer support to the mid-age group could further add up to the core customer base, as they represent a significant portion of the clientele.
   2. **Further Segmentation Analysis:** Segmenting the data further by gender in combination with other variables like age, service plan, and usage patterns could reveal deeper insights.
   3. **Targeted Interventions:** Develop targeted customer retention and intervention strategies for clusters with high churn probability, especially for age groups showing the highest churn risk.
   4. **Customer Loyalty Programs:** For clusters with a consistent churn probability, consider customer loyalty programs that increase customer stickiness and reduce the likelihood of churn.

## References
1.	https://www.kaggle.com/datasets/blastchar/telco-customer-churn
2.	Pandas Textbook


