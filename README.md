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
