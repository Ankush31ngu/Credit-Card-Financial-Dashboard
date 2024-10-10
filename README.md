Power BI Dashboard Project:- Credit card transaction and customer weekly report



Objective:- To develop a comprehensive credit card weekly dashboard that provides real-time insights into key performance metrics and trends, enabling stakeholders to monitor.



Steps:- First clean the data and remove duplicates by power query. 

    Create a column AgeGroup, IncomeGroup, Revenue, Week_num2

                                     DAX Query

.AgeGroup = SWITCH(

    TRUE(),

    customer[Customer_Age] <30,"20-30",

    customer[Customer_Age] >= 30 && 'customer'[Customer_Age] < 40, "30-40",

    customer[Customer_Age] >= 40 && 'customer'[Customer_Age] < 50, "40-50",

    customer[Customer_Age] >= 50 && 'customer'[Customer_Age] < 60, "50-60",

    'customer'[Customer_Age] >= 60, "60+",

    "unknown"

)


.IncomeGroup = SWITCH(

    TRUE(),

    'customer'[Income] < 35000, "Low",

    'customer'[Income] >= 35000 && 'customer'[Income] <70000, "Med",

    'customer'[Income] >= 70000, "High",

    "unknown"

)


.Revenue = credit_card[Annual_Fees] + credit_card[Total_Trans_Amt] + credit_card[Interest_Earned]


.Week_num2 = WEEKNUM(credit_card[Week_Start_Date].[Date])




Insights:- •         Revenue increased by 28.8%, 

           •         Total Transaction Amt & Count increased by xx% & xx%

           •         Customer count increased by xx% Overview YTD:

           •         Overall revenue is 57M

           •         Total interest is 8M

           •         Total transaction amount is 46M

           •          Male customers are contributing more in revenue 31M, female 26M

           •         Blue & Silver credit card are contributing to 93% of overall transactions

           •         TX, NY & CA is contributing to 68%

          •         Overall Activation rate is 57.5%

          •         Overall Delinquent rate is 6.06%
