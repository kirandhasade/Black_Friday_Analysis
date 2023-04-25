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
 11. Top 10 most popular sold products?<img width="647" alt="Screenshot 2023-04-25 at 11 37 15" src="https://user-images.githubusercontent.com/127043120/234252078-e4867782-c8bb-4b83-90b8-9d3bdb132f1d.png">

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

### Phase 4:Data Analysis
#### Q.1 Which age group has purchased more number of products?
 ![Screenshot 2023-04-25 at 10 50 12](https://user-images.githubusercontent.com/127043120/234240589-8ce4db11-c577-4ec7-9532-39867fdba7a1.png)
-  Most of the users who participate in the Black Friday Sale are from age group 26–35, 36–45 and 18–25.
-  As these customers are in the golden age of their life,they make more money than other age groups, and they also have more shopping needs comparing to other age groups.

#### Q.2.How many males and females in dataset and what is the ratio of each?
![Screenshot 2023-04-25 at 10 52 23](https://user-images.githubusercontent.com/127043120/234241117-b92de3b7-adbe-487d-9a45-03adc6745ce2.png)
- Male  gender consists of 75% of population in the entire dataset ,where as female gender only contains 25 % of population.
- Male customers shop more comparing to Female customers because the most worthwhile things to buy on the Black Friday are electrical appliances, small appliances, and game consoles.
- Apple products, especially iPad, the prices are the best in a year.Obviously such products are more popular with male customers.

#### Q.3. What is the age group of each male and females?How many males and females in each age group?
![Screenshot 2023-04-25 at 11 24 32](https://user-images.githubusercontent.com/127043120/234249152-44fbfa2e-26f4-41d8-8ff2-7fd73bcdf0d7.png)
-  Male count is more in age group 26-35 followed by 36-45 and 18-25.
- As male tends to shop more electronic gadgets and small electrical appliances on Black Friday sales.

#### Q.4 Which product category product has been sold most?

- ![Screenshot 2023-04-25 at 11 27 46](https://user-images.githubusercontent.com/127043120/234249886-88ffffaa-fba2-4934-b9ff-a08b5ec9f024.png)
- ![Screenshot 2023-04-25 at 11 28 16](https://user-images.githubusercontent.com/127043120/234249993-354dccdd-ad0d-4d4a-bee2-04586d68efd8.png)
![Screenshot 2023-04-25 at 11 28 44](https://user-images.githubusercontent.com/127043120/234250103-8b71f402-71c5-40bf-ad45-5a2f35c34ca3.png)
-  Following are the observations.
   - In product_category_1 5 product category has highest number of sales followed by 1 and 8 products.
   - In product_category_2 0.0 product category has highest number of sales followed by 8.0 and 14.0.
   - In product_category_3 0.0 product category has highest number of sales followed by 16.0 and 15.0.
   
- Most popular products may help the merchant adjust their business strategy and can prepare for the next shopping season better so that to increase revenue and profit.

#### Q.5 Which city_category has more purchases? 
 ![Screenshot 2023-04-25 at 11 29 59](https://user-images.githubusercontent.com/127043120/234250393-44bdd9ff-9b90-4c09-87b7-38f9d2731a8c.png)
- <img width="653" alt="Screenshot 2023-04-25 at 11 38 15" src="https://user-images.githubusercontent.com/127043120/234252317-8511290c-06d2-4edc-ad3e-b5def75dc9d5.png">
- B city_category has more number of counts hence it might represents the urban area where most of the population resides.
- City B might be larger than City A & Citi C and thus has a larger population.

#### Q.6 What will be the purchases with respect to staying in current city?
![Screenshot 2023-04-25 at 12 22 03](https://user-images.githubusercontent.com/127043120/234261612-1658da96-b7f0-4ec1-a6c8-7191a3369396.png)
- The tendency looks like the longest someone is living in that city the less prone they are to buy new things.
- Hence, if someone is new in town and needs a great number of new things for their house that they’ll take advantage of the low prices in Black Friday to purchase all the things needed.

#### Q.7 What average spend by gender?
![Screenshot 2023-04-25 at 12 23 04](https://user-images.githubusercontent.com/127043120/234261843-3cff6248-9578-463f-8ca2-fadde3ab318e.png)
 - Average spend of male and female is uniformely distributed but with a slight little difference.
 - Overall males are more in this dataset as compared to females.
 - This chart shows females spend more as compared to males on average.

#### Q.8 What average spend on each product of  product_categories?
- ![Screenshot 2023-04-25 at 12 24 09](https://user-images.githubusercontent.com/127043120/234262060-d1a60276-86bb-4109-84b5-b2fa686f7852.png)
- ![Screenshot 2023-04-25 at 12 24 42](https://user-images.githubusercontent.com/127043120/234262173-bacc8b14-a34a-437f-919d-8abed6ed180c.png)
![Screenshot 2023-04-25 at 12 25 04](https://user-images.githubusercontent.com/127043120/234262253-cfc3ad2c-22fd-4db7-942e-04e774f1be80.png)

- Average spend on highest product **(10)** in product_category_1 , lowest average product **(19)** is  and average medium product is **(17)**  whose prices are approximately **20,000 , 37, and 10,000 rupees** respectively.
 - Average spend on highest product **(10.0)** in product_category_2 , lowest average product **(7.0)** is  and average medium product is **(17.0)**  whose prices are approximately **15,000 , 6000, and 9,000 rupees** respectively.
 - Average spend on highest product **(3.0)** in product_category_2 , lowest average product **(0.0)** is  and average medium product is **(11.0)**  whose prices are approximately **14,000 , 8000, and 12,000 rupees** respectively.
 
 #### Q.9 What average spend on each city?
 <img width="672" alt="Screenshot 2023-04-25 at 12 27 55" src="https://user-images.githubusercontent.com/127043120/234262892-22659025-92ee-4ac7-8934-3673e15e8bfa.png">
-  Average spend of C city_category is the highest i.e. rupees 9708.52 followed by city_category B and city_category A.

#### Q.10 What average spend on each occupation?
<img width="1006" alt="Screenshot 2023-04-25 at 12 30 58" src="https://user-images.githubusercontent.com/127043120/234263548-9807e3a5-c796-4426-8893-da5ca9a448b7.png">
- Occupation 17 has highest average spend i.e. approxiately rupees 9804 followed by occupation 15 and occupation 12 i.e. approximately  9793 and 9791 respectively.

#### Q.11 Top 10 most popular sold products?
![Screenshot 2023-04-25 at 12 32 38](https://user-images.githubusercontent.com/127043120/234263920-d5b6bd38-4304-491a-ad8e-eaf9d3bfd612.png)
- P00265242 most sold products followed by P00025442 and P00110742.
- Most popular products may help the merchant adjust their business strategy and can prepare for the next shopping season better so that to increase revenue and profit.
 
#### Q.12 Top 10 most expensive sold products?
![Screenshot 2023-04-25 at 12 33 57](https://user-images.githubusercontent.com/127043120/234264205-919e843b-a97c-46aa-aef1-7fe64d445c37.png)
 - P00086242 product is the most expensive product of ruppes 21,256 rupees followed by P00085342 and P00200642 i.e. approximately 20,980 and 20,468 rupees respectively.
 
### Q.13 How many products are sold by each city_category?
![Screenshot 2023-04-25 at 12 35 05](https://user-images.githubusercontent.com/127043120/234264442-6342db44-24ee-4b68-935c-a0d6d5428e29.png)
- B city_category has purchased highest number of products i.e. 329720 followed by city_category C and city_category A which are 243666 and 2102220 respectively. 

