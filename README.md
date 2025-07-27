# 🔁 Banking Customer Churn Data Analysis Dashboard

This project showcases an interactive **Power BI dashboard** to analyze and visualize customer churn dynamics. The analysis highlights customer retention, churn trends, demographic patterns, and behavioral insights to support **data-driven strategies** for improving customer loyalty and reducing attrition.

<br/>

## 📊 Dashboard Overview

The dashboard is divided into **two main views**, focusing on churn behavior from different angles:



### 1. **Churn Overview and Exit Analysis**
- **KPIs:** Total, Active, Inactive, Exit, and Retained Customers
- **Customer Category Breakdown:** Credit Card vs. Non-Credit Card Holders
- **Churn Trend by Month:** Exit vs. Previous Month Exit
- **Customer Activity Over Years:** Active vs. Inactive Members
- **Churn by Gender**
- **Churn by Credit Score**
- **Churn by Customer Category**

**📖 Storyline:**  
This view helps business stakeholders understand **how many customers are exiting**, which customer groups are most affected (gender, credit score, membership), and when churn typically spikes. It supports proactive measures like **targeted retention campaigns** and **incentive adjustments** for at-risk customers.



### 2. **Demographics and Time-Based Analysis**
- **Exit and Retain Customers by Country**
- **Exit and Retain Customers by Age**
- **Churn Rate Table (2016–2019)** by Month

**📖 Storyline:**  
The second view focuses on **geographic and demographic** differences in customer churn. It also provides a **longitudinal view of churn percentages** across months and years. By understanding regional and age-based patterns, businesses can **customize regional marketing** and customer experience strategies.


<br/>

## 📌 Key Insights

- **Total Customers Analyzed:** 10,000  
- **Exit Customers:** 2,037 | **Retention Rate:** ~79.6%  
- **Majority of Churn:** Among **credit card holders** and **males**
- **Fair Credit Score segment** has the highest exit rate
- **France** shows the highest customer retention
- **Churn peaks between age 35–50**
- **Churn spikes observed in May, June, and October across multiple years**


<br/>

## 📈 DAX Measures 

1. Active Customer = CALCULATE(COUNT(Bank_Churn[CustomerId]),ActiveCustomer[ActiveCategory] = "Active Member")

2. Churn% = 
var EC = [Exit Customer]
var TC = [Total Customer]
var churnper = DIVIDE(EC,TC)
return churnper

3. Credit Card Holder = CALCULATE(COUNT(Bank_Churn[CustomerId]),CreditCard[Category] = "Credit Card Holder")

4. Exit Customer = CALCULATE(COUNT(Bank_Churn[CustomerId]),'Exit Customer'[ExitCategory] = "Exit")

5. InActive Customer = CALCULATE(COUNT(Bank_Churn[CustomerId]),ActiveCustomer[ActiveCategory] = "Inactive Member")

6. Non Credit Card Holder = CALCULATE(COUNT(Bank_Churn[CustomerId]),CreditCard[Category] = "non credit card holder")



7. Retain Customer = CALCULATE(COUNT(Bank_Churn[CustomerId]),'Exit Customer'[ExitCategory]= "Retain")

8. Previous Month Exit Customer = CALCULATE([Exit Customer],PREVIOUSMONTH('Date Master'[Date]))

9. Total Customer = COUNT(Bank_Churn[CustomerId])



<br/>

## 🖼️ Dashboard Snapshots

<br/>

<div align="center">
 <img width="777" height="471" alt="image" src="https://github.com/user-attachments/assets/71e22be5-6b2d-4d24-8092-d5b3d6dbfffd" />

</div>
<br/>

<div align="center">
  <img width="775" height="449" alt="image" src="https://github.com/user-attachments/assets/4bda3e94-6903-4445-bbf4-4a2319136b65" />

</div>
<br/>

