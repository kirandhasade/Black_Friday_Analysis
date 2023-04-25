# Project Name: Black_Friday_Analysis
## Project Objective
- A retail company “ABC Private Limited” wants to understand the customer purchase behaviour (specifically, purchase amount) against various products of different categories. They have shared purchase summaries of various customers for selected high-volume products from last month.
- The objective is to clean, prepare and analyse the Black Friday Sales dataset taken from Kaggle.
- Analyze the sales of an product in the retail store based on age, gender, marital status, occupation of the dataset. 


- Using Black Friday sales dataset tried to answer following questions.
 1. Which age group has purchased more number of products?
 2. How many males and females in dataset and what is the ratio of each?
 3. What is the age group of each male and females?How many males and females in each age group?
 4. Which product category  product has been sold most?
 5. Which city_category has more purchases? 
 6. What will be the purchases with respect to staying in current city?
 7. What average spend by gender?
 8. What average spend on each product of  product_categories?
 9. What average spend on each city?
 10. What average spend on each occupation?
 11. Top 10 most popular sold products?
 12. Top 10 most expensive sold products?
 13. How many products are sold by each city_category?
 
 ### Analysis Involve Phases:
  1. Data Collection
  2. Data Understanding
  3. Data Cleaning 
  4. Data Analyse

### Phase 1: Data Collection
#### Dataset information:
- The dataset used in this analysis contains information of transactions in a store on Black Friday includes:
      - Customers' Demographical:
            - age, gender, marital status, city type, stay in the current city 
      - Product details 
            - productid and product category 
      - Transaction details and
      - Total purchase amount from last month.
- The dataset comes from a competition hosted by Analytics Vidhya.
- The dataset has 783667 rows and 12 columns.

### Phase 2: Data Understanding
### Observation

  1. user_id
  - Represents unique_id of the customer.
  - It is of int datatype.
  
  2. product_id
  - Unique_id for each product.
  
  3. gender
  - Reprsents gender of the customer.
  - Categorical variable type.
  
  4. age
  - Represents age range of the customer.
  - Categorical variable type.
   
  5. occupation
  - Represents Occupation code of the customer.
  - It is of int datatype.
  - Categorical variable type. 
  
  
  6. city_category
  - Represents city of the customer where he is residing.
  - Categorical variable type.
  
  7. stay_in_current_city_years
  - Represents number of years of stay in city in years.
  
  8. martial_status
  - Represents martial status i.e customer married or not.
  - Boolean variable type.
  
  9. product_category_1
  - Represents category of product.
  - It is of int datatype.
 
  10. product_category_2
  - Represents category of product.
  - It has 245982 null values.
  - It is of float datatype.
  
  11. product_category_3
  - Represents category of product.
  - It has 545809 null values.
  - It is of float datatype.
  
  12. purchase
  - Represents purchasing amount of the customer.
  - It has 233599 null values.
  - It is of float datatype.

### Phase 3: Data Cleaning and Handling Null Values

#### Data cleaning
- Step 1: **Dropped user_id column** as we don't need for further analysis.
- Step 2: **Converted gender column into numeric value i.e. Female:0 and Male:1** as it is a categorical variable and we have to convert it into numerical variable.
- Step 3: **Converted age column and giving rank with respect to age** as it is a categorical variable and we have to convert it into numerical variable.
- <img width="726" alt="Screenshot 2023-03-28 at 16 00 51" src="https://user-images.githubusercontent.com/127043120/228280931-a1f7c6ae-2d14-4c73-8798-f5f16dae0bc0.png">

#### Handling null values
- Step 1 :Find out for **each product_id's how many values corresponding are in  product_category_1, product_category_2 and product_category_3.**
- <img width="503" alt="Screenshot 2023-03-26 at 18 31 44" src="https://user-images.githubusercontent.com/127043120/228299864-bfe15791-6a49-4fda-89cc-7459a2003982.png">.
- Step 2:  **We are not able to find corresponding values for null's in product_category_2 ,product_category_3** for each particular product_id hence why we are replacing  all nulls it with zero.
- Step 3: **Replaced null values with zero in product_category_2 column**.
- Step 4: **Replaced null values with zero in product_category_3 column**.
- Step 5: **Null purchase amount will be imputed or replace by mean value based on product_id** 
- <img width="897" alt="Screenshot 2023-03-28 at 17 24 03" src="https://user-images.githubusercontent.com/127043120/228305987-1f4769c9-17f2-4e4a-ac9e-f93d985e76c4.png">
- Step 6: **There are still 61 null values present in purchase column** eventhough after replacing purchase column with mean.
- Step 7: **Deleted 61 null record values** as there is no corresponding rows for purchased product_id in dataset to compute mean purchase_amount,as their corresponding purchase column contains null values. 
- Alternatively in real world scenarios, we try to get this puchase_amount null or incomplete information from accounts/sales department.

###  Phase 4:Data Analysis
#### Q.1 Which age group has purchased more number of products?
