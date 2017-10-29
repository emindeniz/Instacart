# Instacart-Kaggle-Competition

How to use:

These are the scripts I used during Instacart Market Basket Analysis Kaggle competition. `Doc2vec` scripts are used to create embeddings for users and products using gensim library. However, I have already included the results of these script as `product2vec.model` and `user2vec.model`files.Then, `Instacart_Competition_Main_Script.ipynb` is run used to generate all the other features and create a probabilities files to be submitted to the competition.Example submission file `test_submit.csv` is included.


Summary of the competition from the website:

Whether you shop from meticulously planned grocery lists or let whimsy guide your grazing, our unique food rituals define who we are. Instacart, a grocery ordering and delivery app, aims to make it easy to fill your refrigerator and pantry with your personal favorites and staples when you need them. After selecting products through the Instacart app, personal shoppers review your order and do the in-store shopping and delivery for you.

Instacart’s data science team plays a big part in providing this delightful shopping experience. Currently they use transactional data to develop models that predict which products a user will buy again, try for the first time, or add to their cart next during a session. Recently, Instacart open sourced this data - see their blog post on 3 Million Instacart Orders, Open Sourced.

In this competition, Instacart is challenging the Kaggle community to use this anonymized data on customer orders over time to predict which previously purchased products will be in a user’s next order.


https://www.kaggle.com/c/instacart-market-basket-analysis

My performance:

Overall, I finished 97th and won a silver medal.

https://www.kaggle.com/emindeniz

Data Description

The dataset for this competition is a relational set of files describing customers' orders over time. The goal of the competition is to predict which products will be in a user's next order. The dataset is anonymized and contains a sample of over 3 million grocery orders from more than 200,000 Instacart users. For each user, we provide between 4 and 100 of their orders, with the sequence of products purchased in each order. We also provide the week and hour of day the order was placed, and a relative measure of time between orders. For more information, see the blog post accompanying its public release.
File descriptions
Each entity (customer, product, order, aisle, etc.) has an associated unique id. Most of the files and variable names should be self-explanatory.


aisles.csv
```
 aisle_id,aisle  
 1,prepared soups salads  
 2,specialty cheeses  
 3,energy granola bars  
 ...
```
departments.csv
```
 department_id,department  
 1,frozen  
 2,other  
 3,bakery  
 ...
 ```
order_products__*.csv

These files specify which products were purchased in each order. order_products__prior.csv contains previous order contents for all customers. 'reordered' indicates that the customer has a previous order that contains the product. Note that some orders will have no reordered items. You may predict an explicit 'None' value for orders with no reordered items. See the evaluation page for full details.
 
 ```
 order_id,product_id,add_to_cart_order,reordered  
 1,49302,1,1  
 1,11109,2,1  
 1,10246,3,0  
 ... 
 ```
orders.csv
This file tells to which set (prior, train, test) an order belongs. You are predicting reordered items only for the test set orders. 'order_dow' is the day of week.
 ```
 order_id,user_id,eval_set,order_number,order_dow,order_hour_of_day,days_since_prior_order  
 2539329,1,prior,1,2,08,  
 2398795,1,prior,2,3,07,15.0  
 473747,1,prior,3,3,12,21.0  
 ...
```
products.csv
```
product_id,product_name,aisle_id,department_id
1,Chocolate Sandwich Cookies,61,19  
2,All-Seasons Salt,104,13  
3,Robust Golden Unsweetened Oolong Tea,94,7  
...
```
sample_submission.csv

```
order_id,products
17,39276  
34,39276  
137,39276  
...
```

