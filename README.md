# Capstone-Project Amazon-Review-Analysis

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


**limitations:** the dataset didn't include time(year,month,days) these would have help for a better analysis


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
    - To find the products having the highest number of reviews deployed a pivot table which is below

       ![p1](https://github.com/user-attachments/assets/56c2d3ab-732f-4cd8-a01d-1c60ee74d4ef)

     - In order to locate How many products having a discount of 50% or more i used the countif function
  ```
  =COUNTIF(Table1[discount_percentage],">=50%")
  ```

    - To find how many products are rated 3.0, 4.0 e.t.c i used the function below
  ```
  =COUNTIF(L3:L1466,">3.0")
  ```

    - Finding total potential revenue (actual_price × rating_count) by category i had to create a calculated column which is below
  ```
  =[@[actual_price]]*[@rating]
  ```
     - To find number of unique products per price range bucket (e.g., <₹200, ₹200–₹500, >₹500) i had to create a calculated column which is below
  ```
  =IF([@[actual_price]]<200, "<₹200", IF([@[actual_price]]<=500, "₹200 - ₹500", ">₹500"))
  ```
     - To find categories having products with the highest discounts i used same method deployed in first description
     - to find the How many products that is having fewer than 1,000 reviews
  ```
  =COUNTIF(M3:M1463,"<1000")
  ```

     - The average discount percentage by product category **pivot table**

       ![p2](https://github.com/user-attachments/assets/80b73a2a-102b-495e-82f4-63572581355d)


     - How many products are listed under each category **pivot table** below 

       ![p3](https://github.com/user-attachments/assets/6afa942d-e01c-4ff6-b277-e4f8049e4d4a)


     - What is the average actual price vs the discounted price by category **pivot table** below

       ![p4](https://github.com/user-attachments/assets/6bc95fbf-8f0e-4dea-8240-234955e02247)


     - What is the total potential revenue (actual_price × rating_count) by category
       **pivot table **below

       ![p5](https://github.com/user-attachments/assets/54fe8dba-22bb-4778-b8b2-eaf0ae3b6147)

     - What is the number of unique products per price range bucket (e.g., <₹200, 
       ₹200–₹500, >₹500) **pivot table**

       ![p6](https://github.com/user-attachments/assets/2d8018f3-e7b5-42bc-9cb0-74a856d09ec8)


     - Identify the top 5 products in terms of rating and number of reviews combined **pivottable**

       ![p7](https://github.com/user-attachments/assets/be1bda97-e652-415d-981e-b45601df9709)


  ### 5. Result interpertation

  1. Average discount percentage by product category: This chart shows that **HomeImprovement** Category has the highest discount with 58% while Computer&Accessories is the second highest discount, the Toys&Games is the lowest of all.

  2. How many products are listed under each category:** Electronics** 526 product which makes it the highest product under each category, we have **Computer&Accessoires** as the second highest which has 453 product, **Home&Kitchen** has 448 products, **officeProduct** has 31 product under it, **MusicalInstrument** and **HomeInprovemetent** has 2 product, then **car&Motorbike**,**Toys&Game**s and **Health&PersonalCare** has 1 product each.

  3. What is the total number of reviews per category: Car&Motorbike 1118, Computers&Accessories 7728689, Electronics 15778848, Health&PersonalCare 3663, Home&Kitchen 2991069, HomeImprovement  8566, MusicalInstruments 88882, OfficeProducts  149675, Toys&Games 15867       


   4. Which products have the highest average ratings: B0BP7XLX48, B0BQRJ3C47, B09ZHCJDP1
   5. What is the average actual price vs the discounted price by category: this show that Electronics has the highest actual price of 10127.31179 and highest discount price of 5965.887833
   6. which products have the highest number of reviews: B0BP7XLX48
   7. How many products have a discount of 50% or more: 751
   8. What is the distribution of product ratings (e.g., how many products are rated 3.0, 4.0,     etc.): 1454
   9. The highest total potential revenue is Electronic with 22210296.4
   10. Highest products per price range bucket is >₹500 having 1245 product 
   11. There is no upward or downward trend 
   12. How many products have fewer than 1,000 reviews: 324
   13. Which categories have products with the highest discounts : Computers&Accessories with 94%
   14. will be show at visualization 

- In respect to data giving to me, Electronic, HomeImprovement and Computers&Accessories always have a upward trend

  #### DASHBOARD

![Real Dash Board](https://github.com/user-attachments/assets/ce905c99-c73b-44be-b9ed-814bd82f74f4)

### 6. Insights
-	Discount of product do not improve higher rating or reviews the company should focus more on product quality rather than discount.
-	Too much discount can affect the company’s Revenue which is to say discount should be brought to maximum of 30-40%.
-	For product with low review and potential Revenue like Health&PersonalCare category should seek endorsement for clinic and order medical organization to strengthen trust from customers like an open advert from this organization.
-	Their should be more focus and improvement in this categories, Electronics, Computers&Accessories, Home&Kitchen 
-	More advert are to be made for other product having lesser review and the products quality should be inspected.
-	On the application suggestions of other products should be made to customer.
-	Instead of a general discount, discount should be made on product with less purchase and review.



# LINK TO SECOND PROJECT HERE
https://github.com/emmydynamics/Kultra-Mega-Stores-Inventory-EDA-with-SQL




 

  

  









  
  

  
  
  
  














  














