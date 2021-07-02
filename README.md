# Online_store_prediction



## Introduction

Predicting sales is one of the most important business problems for any retail entity. If business can predict the how much of each item it will sell in each month, week or year, it can manage its inventory better. Sales predictions also help in directing the marketing efforts in right direction to increase the chances of sale. The project aims to extract insights with business value for an online retailer using Jupiter notebook and Sklearn library. A large part of the analysis consists of data cleaning and fundamental exploratory analysis, as usually is the case with data science projects. After those basic steps, I employ machine learning algorithms to predict the total sales of company. 

## Who might care?

It is helpful for sellers because it tells you what features of the item matter froe the sale price. Sometimes certain features don't cost too much but can be game-changer in the negotiation and bring much more profit than its costs. 

## Context of Data 

The dataset consists of transactional data with customers in different countries who make purchases from an online retail company based in the UK that sells unique all-occasion gifts. 
* Company: the UK based and registered non-store online retail
* Product for selling: Mainly all occasion gifts
* Customers: Most are wholesalers around the world
Transactions Period: 12/1/2010 to 12/9/2011

Understanding each variable means:
* InvoiceNo: A number assigned to each transaction 
* StockCode: Product code
* Description: Product name 
* Quantity: Number of products purchased for each transaction 
* Invoice date: Timestamp for each transaction
* UnitPrice: Product price per unit 
* CustomerID: Unique identifier each customer
* Country: Country name

## Data Wrangling 


**Missing values**


![image](https://user-images.githubusercontent.com/43426359/124316560-a186af80-db2a-11eb-976b-2ae559e849ea.png)

There are about 13600 missing values in our dataset

**Descriptive statistics**


![image](https://user-images.githubusercontent.com/43426359/124316697-db57b600-db2a-11eb-9cf7-ba9653fb1c1a.png)

There are two things are interesting.
1. Quantity has negative values
2. Unit price has zero values

If unit price is zero, is this item FREE?


## Exploratory Data Analysis

Now we want to see how much money is spent for different customers.  


![image](https://user-images.githubusercontent.com/43426359/124317223-aac44c00-db2b-11eb-8abd-0684dba46c3a.png)

**Money spent by Country**


![image](https://user-images.githubusercontent.com/43426359/124317282-c62f5700-db2b-11eb-847e-2b56aaa2327a.png)


**Number of orders by month**


![image](https://user-images.githubusercontent.com/43426359/124317366-e95a0680-db2b-11eb-8a43-aa983aa61dc3.png)


**Money spent by month**

![image](https://user-images.githubusercontent.com/43426359/124317407-faa31300-db2b-11eb-99bd-737ca6f1c05e.png)



**Orders for different countries with or without UK**


With UK



![image](https://user-images.githubusercontent.com/43426359/124317844-a9dfea00-db2c-11eb-956e-e0a035453cb2.png)



Without UK



![image](https://user-images.githubusercontent.com/43426359/124318008-e14e9680-db2c-11eb-86ec-5d2bef6b7d90.png)



## Modeling

One measure is  𝑅2 , the coefficient of determination. The linked Wikipedia articles gives a nice explanation of how negative values can arise. This is frequently a cause of confusion for newcomers who, reasonably, ask how can a squared value be negative?

Putting it into words, it's one minus the ratio of the residual variance to the original variance. Thus, the baseline model here, which always predicts  𝑦¯ , should give  𝑅2=0 . A model that perfectly predicts the observed values would have no residual error and so give  𝑅2=1 . Models that do worse than predicting the mean will have increased the sum of squares of residuals and so produce a negative  𝑅2 .


**Linear regression model’s output.**
Mean Squared Error: 329.623112
R Squared: -0.084346721


![image](https://user-images.githubusercontent.com/43426359/124319018-68503e80-db2e-11eb-9bf7-4f28009e9e19.png)



**Random forest model output.**

Mean Squared Error: 329.62311233205
R squared: -0.08434672177180![image](https://user-images.githubusercontent.com/43426359/124319036-756d2d80-db2e-11eb-96cc-9051217287e4.png)


Arima model output.
Mean Squared Error: 62.772805353
R squared: -0.19728854830


![image](https://user-images.githubusercontent.com/43426359/124319091-8e75de80-db2e-11eb-8b07-267558ae1077.png)





## To sum up


Based on performance, LinearRegression, Arima, and RandomForest models perform not well. The biggest reason is features are doesn’t have any effect on the total sales except for the quantity. The next step is to focus on the customers and countries more. Which country can buy more products and work on customers are in the middle of the pack and bring them up to top buyers. Also, investigate more on why there are many cancellations.






