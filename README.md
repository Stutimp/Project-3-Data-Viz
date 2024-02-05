# Project-3 (Data Visualization Track)

## Project Overview

### Regarding Dataset

For the project - 3, I picked the data visualization track. Here, as per the project requirements, I have picked a dataset from kaggle, the link for my dataset is as following:
https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset

This dataset is which is in csv form is a scrapped data collection from the amazon websites consisting different electronic goods. For my project, I have  picked two different kinds of categories. One consists of our everyday electronic items, such as Cables. I have explored different kinds of Cables from the dataset and did some exploratory data analysis on them.

## Data cleaning and exploration 
- Note: I have done my initial data exploration inside the jupyter notebook called as, 'Initial Data Analysis of Amazon data through python.ipynb' (inside Code_Amazon folder).
My original dataset contained 1465 rows and 16 columns. I did some preliminary data exploration in the jupyter notebook named as, 'Initial Data Analysis of Amazon data through python' (inside the Amazon_code folder), using .nunique(), .dtypes(), .info() functions.  For the successful query functions, I need my columns to be readable by the codes I will create.However, initially my data columns were all at string formats, hence for the sake of data cleaning and further data exploration, I did some required data type formatting. I changed the data types of the columns [discounted_price, actual_price, discount_percentage, rating and rating_count] from string format to numerical format. For this, first I removed the rupee symbol (Indian currency sign ,'₹') and any other non-numeric characters such as, (% ) except the decimal point, converting the columns to numeric, coercing errors to NaN (in case there are any non-numeric values left). After dropping all columns with missing values /Nan values, also deleting the duplicated rows on "product_id" column for the proper data analysis process, some data type conversions, and also dropping the duplicated data points, we are now left with 16 columns and 1348 data points with 2 floats, 3 integers and rest of all are in string formats.

- Finally the clean dataset is saved externally inside the Clean_Data_Resources folder as 'amazon_cleanData.csv'.
- Note: - Because of the size, the 'Resources' folder containing the original Amazon dataset and the 'Clean_Data_Resources' folder containing the cleaned dataset both are uploaded into google drive and the link is provided as following:***************


## Data analysis with interactive Visualizations using Plotly

- Note : The database that I have decided to use to house my cleaned dataset is, MongoDB,  where I will make some indepth queries and try to extract some relevant results from the dataset for the data analysis purpose. 

I have used following command to import my cleaned dataset into MongoDB database for the data analysis and visualizations:
 mongoimport --type csv -d Clean_Data_Resources -c amazon_cleanData --headerline --drop amazon_cleanData.csv

- First I imported all required dependencies.
- I created an instance of Mongoclient, and confirmed having my amazon new database using, print(mongo.list_database_names()) function.
- I assigned the Clean_Data_Resources database to a variable name 'db' and reviewed my collection. - After that I assigned the collection, 'amazon_cleanData' to a variable name 'amazon' and reviewed documents inside my collection.
- The made some interesting queries and tried to get some indepth insights of my dataset.
- I created some dataframes, and made some interesting interactive visualizations using Plotly and saved externally inside the 'output_Viz' folder.
- In the project, in order to process the text based information, inside the column "review_content" , I have used 'TextBlob'  as a new python library. 

- References for this new library are following: https://buildmedia.readthedocs.org/media/pdf/textblob/latest/textblob.pdf and https://textblob.readthedocs.io/en/dev/quickstart.html#create-a-textblob

## Some of most Important findings of the project
After making some queries, following are the findings I found from my dataset:
- My amazon dataset has total 159 computer USB cables. 
- {"Product_id": B07DC4RZPY, "Product_name": Amazon Basics USB A to Lightning MFi Certified...} is the most popular computer USB cable with 1,78,817 rating counts, with rating score >= 4, in our amazon dataset.
- 
- 
- 

