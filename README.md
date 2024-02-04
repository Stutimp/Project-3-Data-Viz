# Project-3 (Data Visualization Track)

## Project Overview

### Regarding Dataset

For the project - 3, I picked the data visualization track. Here, as per the project requirements, I have picked a dataset from kaggle, the link for my dataset is as following:
https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset

This dataset is which is in csv form is a scrapped data collection from the amazon websites consisting different electronic goods. For my project, I have  picked two different kinds of categories. One consists of our everyday electronic items, such as Cables. I have explored different kinds of Cables from the dataset and did some exploratory data analysis on them.

## Data cleaning and exploration 
- Note: I have done my initial data exploration inside the jupyter notebook called as, 'Initial Data Analysis of Amazon data through python.ipynb' (inside Code_Amazon folder).
My original dataset contained 1465 rows and 16 columns. I did some preliminary data exploration in the jupyter notebook named as, 'Initial Data Analysis of Amazon data through python' (inside the Amazon_code folder), using .nunique(), .dtypes(), .info() functions.  For the successful query functions, I need my columns to be readable by the codes I will create.However, initially my data columns were all at string formats, hence for the sake of data cleaning and further data exploration, I did some required data type formatting. I changed the data types of the columns [discounted_price, actual_price, discount_percentage, rating and rating_count] from string format to numerical format. For this, first I removed the rupee symbol (Indian currency sign ,'₹') and any other non-numeric characters such as, (% ) except the decimal point, converting the columns to numeric, coercing errors to NaN (in case there are any non-numeric values left). After dropping all columns with missing values /Nan values, data type conversions, and also dropping the duplicated data points, we are now left with 16 columns and 1462 data points with 2 floats, 3 integers and rest of all are in string formats. The dataset info is as following:

<class 'pandas.core.frame.DataFrame'>
Index: 1462 entries, 0 to 1464
Data columns (total 16 columns):
 #   Column               Non-Null Count  Dtype  
---  ------               --------------  -----  
 0   product_id           1462 non-null   object 
 1   product_name         1462 non-null   object 
 2   category             1462 non-null   object 
 3   discounted_price     1462 non-null   int32  
 4   actual_price         1462 non-null   int32  
 5   discount_percentage  1462 non-null   float64
 6   rating               1462 non-null   int32  
 7   rating_count         1462 non-null   float64
 8   about_product        1462 non-null   object 
 9   user_id              1462 non-null   object 
 10  user_name            1462 non-null   object 
 11  review_id            1462 non-null   object 
 12  review_title         1462 non-null   object 
 13  review_content       1462 non-null   object 
 14  img_link             1462 non-null   object 
 15  product_link         1462 non-null   object 
dtypes: float64(2), int32(3), object(11)
memory usage: 177.0+ KB

- Finally the clean dataset is saved externally inside the Clean_Data_Resources folder as 'amazon_cleanData.csv'.
- Note: - Because of the size, the 'Resources' folder containing the original Amazon dataset and the 'Clean_Data_Resources' folder containing the cleaned dataset both are uploaded into google drive and the link is provided as following:


## Data analysis with interactive Visualizations using Plotly

- Note : The database that I have decided to use to house my cleaned dataset is, MongoDB,  where I will make some indepth queries and try to extract some relevant results from the dataset for the data analysis purpose. 

I have used following command to import my cleaned dataset into MongoDB database for the data analysis and visualizations:
 mongoimport --type csv -d Clean_Data_Resources -c amazon_cleanData --headerline --drop amazon_cleanData.csv

- First I imported all required dependencies.
- I created an instance of Mongoclient, and confirmed having my amazon new database using, print(mongo.list_database_names()) function.
- I assigned the Clean_Data_Resources database to a variable name 'db' and reviewed my collection. - After that I assigned the collection, 'amazon_cleanData' to a variable name 'amazon' and reviewed documents inside my collection.
- The made some interesting queries and tried to get some indepth insights of my dataset.
- I created some dataframes, and made some interesting interactive visualizations using Plotly and saved externally inside the 'output_Viz' folder.

## Findings of the project
After making some queries, following are the findings I found from my dataset:
- My amazon dataset has total 231 computer USB cables. 
- **Product id "B086JTMRYL"** **ESR USB C to Lightning Cable,** is the most popular computer USB Cables in the dataset (rating counts: 19,763) which has discounted price greater than equal to 100 Indian rupees (discounted price = 1519 INR) and have rating score greater than equal to 4. 
- 
- 
- 

