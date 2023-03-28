# Project Name: Black_Friday_Analysis
## Project Objective
- A retail company “ABC Private Limited” wants to understand the customer purchase behaviour (specifically, purchase amount) against various products of different categories. They have shared purchase summaries of various customers for selected high-volume products from last month.
- The objective is to clean, prepare and analyse the Black friday Sales dataset taken from Analytics Vidhya.
- We have to analyze and the sales of an product in the retail store based on age, gender, marital status, occupation of the dataset. 


- Using Black Friday sales dataset we will try to find out following questions answer.
 1. Which age group has purchased more number of products?
 2. Which product category has been sold most?
 3. Which city_category has more purchases? 
 4. What will be the purchases with respect to staying in current city?
 
 ### Analysis Involve Phases:
  1. Data Collection
  2. Data Understanding
  3. Data Cleaning 
  4. Data Analyse

### Phase 1: Data Collection
#### Dataset information:
- The dataset used in this analysis contains information of transactions in a store on Black Friday, including customers' demographical features (age, gender, marital status, city type, stay in the current city), product details (productid and product category) and transaction details also total purchase amount from last month.
- The dataset comes from a competition hosted by Analytics Vidhya.
- The dataset has 783667 rows and 12 columns.

### Phase 2: Data Understanding
### Observation

  1. user_id
  - Represents unique_id of the customer.
  - It is of int datatype.
  
  2. product_id
  - Represents unique_id of the product.
  - It is of Object data type.
  
  3. gender
  - Reprsents Sex of the customer.
  - It is of object datatype.
  - It is categorical type variable.
  
  4. age
  - Represents Age of the customer.
  - It is of Object datatype.
  - It is categorical type variable. 
   
  5. occupation
  - Represents Occupation code of teh customer.
  - It is of int datatype.
  - It is categorical type variable. 
  
  
  6. city_category
  - Represents city of the customer where he is residing.
  - It is of object datatype.
  - It is categorical type variable. 
  
  7. stay_in_current_city_years
  - Represents number of years of stay in city in years.
  - It is of object datatype.
  
  8. martial_status
  - Represents maritial status of customer.
  - It is of object datatype.
  
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
- <img width="400" alt="Screenshot 2023-03-28 at 15 41 39" src="https://user-images.githubusercontent.com/127043120/228275171-ab09d09c-d522-4093-9f2b-52aa6a63a964.png">
- Step 3: **Converted age column and giving rank with respect to age** as it is a categorical variable and we have to convert it into numerical variable.
- <img width="726" alt="Screenshot 2023-03-28 at 16 00 51" src="https://user-images.githubusercontent.com/127043120/228280931-a1f7c6ae-2d14-4c73-8798-f5f16dae0bc0.png">
- Step 4: **Replaced '4+' with 4 in stay_in_current_city_years column**.
- Step 5: **Converted  stay_in_current_city_years into int**.
- Step 6: **Converted city_category column in numeric value** i.e.0 for B, 1 for C, and B = 0 C = 1 means category A, hence removing 1 column. 
- Step 7: **Merged column B and C in final dataframe**.
- Step 8: **Converted column B and C into int**.
- Step 9: **Dropped city_category column**.

#### Handling null values
- Step 1 :Find out for **each product_id's how many values corresponding are in  product_category_1, product_category_2 and product_category_3.**
- <img width="503" alt="Screenshot 2023-03-26 at 18 31 44" src="https://user-images.githubusercontent.com/127043120/228299864-bfe15791-6a49-4fda-89cc-7459a2003982.png">.
- Step 2:  **We are not able to find corresponding values for null's in product_category_2 ,product_category_3** for each particular product_id hence why we are replacing it with zero.
- Step 3: **Replaced null values with zero in product_category_2 column**.
- Step 4: **Replaced null values with zero in product_category_3 column**.
- Step 5: **Null purchase amount will be imputed or replace by mean value based on product_id** 
- <img width="984" alt="Screenshot 2023-03-28 at 17 22 53" src="https://user-images.githubusercontent.com/127043120/228305804-5c9c8dd0-bd29-46bb-bb64-93dc45f2833e.png">
