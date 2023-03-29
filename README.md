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
- <img width="897" alt="Screenshot 2023-03-28 at 17 24 03" src="https://user-images.githubusercontent.com/127043120/228305987-1f4769c9-17f2-4e4a-ac9e-f93d985e76c4.png">
- Step 6: **There are still 61 null values present in purchase column** eventhough after replacing purchase column with mean.
- Step 7: **Deleted 61 null record values** as there is no rows in dataset to compute mean as their corresponding purchase column contains null values. 
- Alternatively in real world scenarios we might ask accounts team to check the records and give information on purchase column and replace it with correct records.

###  Phase 4:Data Analysis
#### Q.1 Which age group has purchased more number of products?
- 1. Age and Purchase graph has a uniform distribution.
- 2. Purchasing of men is slightly more in age-group 51-55.
- <img width="665" alt="Q 1 screenshot" src="https://user-images.githubusercontent.com/127043120/228579128-dddc577e-0f38-463e-952d-3b20494c7cd3.png">

#### Q.2 Which product category has been sold most?
- product_category_1 has been purchased more than product_category_2 and product_category_3.
- <img width="645" alt="Q 2_a screenshot" src="https://user-images.githubusercontent.com/127043120/228579484-6788ca23-d793-4c6b-9b4d-ff2bd5a78178.png">

- <img width="670" alt="Q 2_b screenshot" src="https://user-images.githubusercontent.com/127043120/228579578-7cb1cd66-d18d-4759-940a-5749cee85225.png">
- <img width="665" alt="Q 2_c screenshot" src="https://user-images.githubusercontent.com/127043120/228579652-6f1990dd-c8b6-444f-bf18-c0ffb67b4b00.png">

#### Q.3 Which city_category has more purchases? 
- B city_category has more number of counts hence it might represents the urban area where most of the population resides.
<img width="659" alt="Q 3 screenshot" src="https://user-images.githubusercontent.com/127043120/228580235-922eb730-87de-47df-b2c4-6be23414f78c.png">

#### Q.4 What will be the purchases with respect to staying in current city?
- The tendency looks like the longest someone is living in that city the less prone they are to buy new things.
- Hence, if someone is new in town and needs a great number of new things for their house that they’ll take advantage of the low prices in Black Friday to purchase all the things needed.
- <img width="696" alt="Q 4 scrrenshot" src="https://user-images.githubusercontent.com/127043120/228581107-bb67f389-b243-4a42-b1e8-34d7ab2cd532.png">
