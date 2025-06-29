![image](https://github.com/user-attachments/assets/4c33dd75-4cde-47ac-8a5b-20b7fe42d4ba)# Capstone-Project Amazon-Review-Analysis

### 1. Project Overview
I'm working as a Junior Data Analyst at RetailTech Insights, A company that provides 
e-commerce analytics solutions to sellers on platforms like Amazon. My team has been 
tasked with analysing product and customer review data to generate insights that can 
guide product improvement, marketing strategies, and customer engagement. 

**Questions:** Use pivot tables and calculated columns where necessary to answer the following: 
1. What is the average discount percentage by product category? 
2. How many products are listed under each category? 
3. What is the total number of reviews per category?  
4. Which products have the highest average ratings? 
5. What is the average actual price vs the discounted price by category? 
6. Which products have the highest number of reviews? 
7. How many products have a discount of 50% or more? 
8. What is the distribution of product ratings (e.g., how many products are rated 3.0, 
4.0, etc.)? 
9. What is the total potential revenue (actual_price × rating_count) by category? 
10. What is the number of unique products per price range bucket (e.g., <₹200, 
₹200–₹500, >₹500)? 
11. How does the rating relate to the level of discount? 
12. How many products have fewer than 1,000 reviews? 
13. Which categories have products with the highest discounts? 
14. Identify the top 5 products in terms of rating and number of reviews combined. 


### 2. Data Description 
 The dataset contains information scraped from Amazon product pages
  -    Product details: name, category, price, discount, and ratings 
  -   Customer engagement: user reviews, titles, and content 
     Each row represents a unique product, with aggregated reviewer data 
stored as comma-separated values

Total Records: 1,465 

TotalFields: 16 columns 

Missing data: column M which is the Review_count column has two(2) missing cells
located at Product_id B0BQRJ3C47 & B0B94JPY2N


limitations: 


### 3. Data Cleaning Process
- making sure the dataset was duplicate free and checking and changing the formate
  of all number column to ensure they are in the right formate to avoid miscalculations
  and error. columns of such changies are column(I&L)
- splited the category colunm to ensure readerbility and the rest of the columns making use
  of the first column while dealing with category 
- For spliting the cell i used **"Convert Text to Column"** for the search bar, Table filters (**CRTL + T**)
  was applied to locate empty cells.


### 4. Analysis Approach
- I used **Bar Chart** to compare value among a few categories, **Pie and Doughnut Chart** to show
  proportion of a whole, **Scatter plot** to Show relationship Between set of values
- In performing analysis on my dataset i used MS Excel
- i used
  ```
  =large(array,k)
  ```
    - To find the highest average ratings then used filters (Ctrl + T) to find product.
    - To find the products having the highest number of reviews deployed a pivot table which is          below
      ================p1==============
     - In order to locate How many products having a discount of 50% or more i used the countif          function
  ```
  =COUNTIF(Table1[discount_percentage],">=50%")
  ```

    - To find how many products are rated 3.0, 4.0 e.t.c i used the function below
  ```
  =COUNTIF(L3:L1466,">3.0")
  ```

    - Finding total potential revenue (actual_price × rating_count) by category i had to create        a calculated column which is below
  ```
  =[@[actual_price]]*[@rating]
  ```
     - To find number of unique products per price range bucket (e.g., <₹200, ₹200–₹500, >₹500)         i had to create a calculated column which is below
  ```
  =IF([@[actual_price]]<200, "<₹200", IF([@[actual_price]]<=500, "₹200 - ₹500", ">₹500"))
  ```
     - To find categories having products with the highest discounts i used same method deployed in first description
     - to find the How many products that is having fewer than 1,000 reviews
  ```
  =COUNTIF(M3:M1463,"<1000")
  ```

     - The average discount percentage by product category **pivot table**
       =============p2===============

     - How many products are listed under each category **pivot table** below 
       ==============p3================

     - What is the average actual price vs the discounted price by category **pivot table**             below
       ===============p4=================

     - What is the total potential revenue (actual_price × rating_count) by category
       **pivot table **below
       ==================p5=============
     - What is the number of unique products per price range bucket (e.g., <₹200, 
       ₹200–₹500, >₹500) **pivot table**
       ================p6=====================

     - Identify the top 5 products in terms of rating and number of reviews combined                    **pivottable**
       ================p7=====================
  
  
  
  
  
  














  














