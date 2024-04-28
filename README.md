# Project Overview 📊
Analysis made over "Consumer Behavior and Shopping Habits" dataset (CC0: Public Domain) using Power BI. The original dataset was obtained from [Kaggle](https://www.kaggle.com/datasets/zeesolver/consumer-behavior-and-shopping-habits-dataset/data).
> The Consumer Behavior and Shopping Habits Dataset provides a detailed overview of consumer preferences and purchasing behaviors. It includes demographic information, purchase history, product preferences, and preferred shopping channels (online or offline).

This is an exploratory analysis project to identify some of the shopping trend behaviors of people, as well as some of other aspects such as season effects on sales, suscriptions, and products.

## Interpreting Data ℹ️
**Customer ID**: Unique customer identifier number.  
**Age**: Age of the customer.  
**Gender**: Gender of the customer.  
**Item purchased**: Precise item bought by the customer.  
**Category**: The category to which the purchased item belongs.  
**Purchase Amount**: Price of the purchased item in dollars.  
**Location**: Where the purchase was made.  
**Size**: Size of the item purchased.  
**Color**: Color of the item purchased.  
**Season**: Season of the year when the purchase was made.  
**Review Rating**: Satisfaction of the client.  
**Subsciption Status**: Indicates subscription participation.  
**Shipping Type**: Method of delivery chosen.  
**Discount Applied**: There was any adjustment in the price of the product?  
**Promo code used**: There was any promotion code used in this purchase?  
**Previous Purchases**: Number of previous transactions.  
**Payment Method**: How the purchase was made.  
**Frequency of purchase**: Rate of customers transactions.  

## Tools 🧰
* Python - Data verification and cleaning.
* Power BI - Data Analysis and Visualization.

## Data Cleaning/Preparation:
* Loading and inspecting the data: I used Python to inspect for null values, duplicated values, and outliers.  
![imagen](https://github.com/ZunigaGarcia/Shopping_behaviors_analysis/assets/168041126/8fee3098-c401-4cc5-b380-f3f7d258c85b)  
No null values.  
![imagen](https://github.com/ZunigaGarcia/Shopping_behaviors_analysis/assets/168041126/2a132063-7904-4f8b-bdfe-ae40abb39c5c)  
No duplicated values.  
![imagen](https://github.com/ZunigaGarcia/Shopping_behaviors_analysis/assets/168041126/0ca09ef5-4944-43ba-92eb-c8c25b448f69)  
No outliers at sight.  
This meant that I was free to continue with pure analysis.  

## Exploratory Data Analysis Questions ❔
* What are the most sold products, are they oriented for male or female population?
* How is the use of different payment methods distributed?
* How does the season impact incomes?
* Which places sells the most?

## Data Analysis 📝
The following can be found in the Power BI file I left on this repository, you can even interact with it, but I want to show you my notes about what I found, supported by graphics.  
![imagen](https://github.com/ZunigaGarcia/Shopping_behaviors_analysis/assets/168041126/64795c80-7183-4c34-b122-8a663a809110)  
**Code of the calculated field**:  
```
Subscribed Women = IF(ISBLANK(CALCULATE(COUNT(shopping_behaviors[Customer ID]),
                    AND(shopping_behaviors[Gender] = "Female",
                    shopping_behaviors[Subscription Status] = "Yes"))), 0)
```
![imagen](https://github.com/ZunigaGarcia/Shopping_behaviors_analysis/assets/168041126/659d0134-36cd-42f2-b44b-f9d378853af2)  

**Calculated field used to display the percentage of the sales in each column**  
```
Percentage of the total = DIVIDE([Total Sales], CALCULATE(([Total Sales]), ALL(shopping_behaviors)))
```  
You can see a pair of data segmentations so you can watch the sales at each season, or whether the customer had a discount or not. If you do, you can observe the findings I wrote at the bottom of the page, for example:
  
![imagen](https://github.com/ZunigaGarcia/Shopping_behaviors_analysis/assets/168041126/2f9b3b73-be56-4cb8-a079-9f7590318218)  
  
Next, I wondered about the payment methods used.  
  
![imagen](https://github.com/ZunigaGarcia/Shopping_behaviors_analysis/assets/168041126/ae0f48c1-bf00-463e-a510-d0ec283a9c6c)  
  
Finally, I wanted to see the amount of items purchased and what they were.  
  
![imagen](https://github.com/ZunigaGarcia/Shopping_behaviors_analysis/assets/168041126/d2bc0d3f-51ed-490e-9d3b-e1bf7cc25d56)  

## Dashboard 📋
You can find this in the Power BI file on this repository.  
![imagen](https://github.com/ZunigaGarcia/Shopping_behaviors_analysis/assets/168041126/67094d15-2793-4465-a2c7-f0487baac9df)  

## Results/Findings 🔎
1. There are no customers that are both women and subscribed.
2. Around 2/3 of the customers were men, but, at the same time, 3 out of 5 of the most sold items were for women.
3. Young people are the most spenders, and people in their 30's are the most frugal.
4. While cash is getting less popular than other methods, it is indeed a very used paying method among young people.
5. There is some heap of the second least popular item (Gloves), and the last one, (Jeans).
6. Season does not affect the sales.
7. Despite being at low positions of the most purchased items, T-shirts, boots, and shoes are some of the most profitable items.
8. Montana, Illinois, California, Idaho, and Nevada, are the states that sell the most.
9. Clothing are, by a big difference, the category that sells the most.

## Recommendations 📄
* Research why are there no women subscribed and boost subscriptions among them.
* Retaining young buyers and driving sales among adults in their 30s and 50s.
* Retain and drive sales of clothing for women.
