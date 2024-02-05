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
- Note: - Because of the huge sizes, the 'Resources' folder containing the original Amazon dataset and the 'Clean_Data_Resources' folder containing the cleaned dataset both are uploaded into a google drive and the link is provided as following: https://drive.google.com/drive/folders/10IlokEqsQ7Xx6Y9571HVIxnSrrij2VWW?usp=sharing (Kindly find both folders for the original and cleaned dataset for this project)


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
#### Cables:
- My amazon dataset has total 159 computer USB cables. 
- {"Product_id": B07DC4RZPY, "Product_name": Amazon Basics USB A to Lightning MFi Certified...} is the most popular computer USB cable with 1,78,817 rating counts, with rating score >= 4, in our amazon dataset.
- I used sentiment analysis on the "review"_content" column of top 5 computer USB products' and found the overall positive reviews, as indicated by the positive polarity scores. Likewise, the reviews appear to contain a mix of subjective opinions and objective statements, with subjectivity scores in the moderate range.
- Total Number of items which are TV HDMI cables in result are: 21.
- **{"product_id" : B014I8SX4Y, "product_name": Amazon Basics High-Speed HDMI Cable, 6 Feet. }** is the most popular TV HDMI in the dataset with rating counts of 4,26,973. Likewise, overall, the sentiment analysis of most popular TV HDMI cables suggests that the reviews given by its customers are generally positive about the HDMI cables, with varying degrees of positivity and subjectivity.
- Altogether, there are eight kinds of Cables in this dataset, they are:
1. Computer USB Cables are: 159
2. TV HDMI Cables are: 21
3. RCA Cables are: 2
4. Optical Cables are: 3
5. DVI Cables are: 1
6. Speaker Cables are: 1
7. ethernet Cables are: 2
8. SATA Cables are: 1
- Therefore, Total Cables = Computer_USBs + TV_HDMI_cables + RCA_cables + optical cables + DVI cables + speaker cables + ethernet cables + SATA cables = 190.
#### Smart Tvs:
- Total Number of items which are all Smart Televisions in our dataset are: 18.
-  **"Product_id": B08Y55LPBF, product_name : Redmi 126 cm (50 inches) 4K Ultra HD Android S...** is the most popular Smart Tv in the dataset with the rating counts equal to 45238.0. 
- Likewise, all the sentiment polarity scores are positive, which indicates that the reviews have a generally positive tone.Also, the subjectivity scores are also moderate, which implies that the reviews contain a mix of objective facts and subjective opinions.
- Within the dataframe made out of five Most Popular Smart Tvs, we found the correlation coefficient between 'rating_count' and 'discounted_price' is approximately 0.054 which indicates a very weak positive linear relationship between the number of ratings a product has received and its discounted price within the dataset. This suggests that there is barely any linear correlation between how many times a product has been rated and its discounted price and vice versa.
- Also the stacked bar graph showing a comparison between the actual prices and discounted prices of smart TVs with a rating score of 4, where one bar showing actual price of each product and another bar showing discounted price for each product suggests that the actual prices reach up to 150k INR while the discounted prices are consistently lower among the SmarT TVs int he dataset.

###  Data Visualizations




## Ethical Considerations made in the project:
The ethical considerations for collecting and analyzing datasets are very critical to ensure respect for privacy, consent, fairness, and transparency.The purpose for which data is collected and analyzed should be ethical and not harm individuals or communities.Stakeholders, including the public and data subjects, should have the ability to understand and question how their data is being used and the decisions being made based on the data analysis. 
For this project, I have used the kaggle website to collect my dataset. This dataset is a scrapped data from amazon website, where the main author has correctly provided a reference to the Amazon website, as a source of dataset where he has collected data from . This dataset contains information regarding different categories of electronic goods, from USB chargers to Smart Televisions. This dataset doesnot provide personal information about any users beside their provided full name and user id. Also I found on this Amazon official website: https://www.aboutamazon.com/news/how-amazon-works/amazon-is-earning-and-maintaining-customer-trust-through-privacy ,where Amazon is claiming how they are very much aware of their ethical obligations towards their users and following every rules and regulations to ensure the customers privacy and data security. The Amazon website has claimed that through their internal security processes and procedures they are trying their best to maintain the trust of customers around the world.

Thanks to my awesome teaching assistants and tutors who have helped me throughout this project. 

Some references I have used while working in this project:
- https://plotly.com/python/
- https://buildmedia.readthedocs.org/media/pdf/textblob/latest/textblob.pdf
- https://textblob.readthedocs.io/en/dev/quickstart.html#create-a-textblob
- https://www.mongodb.com/docs/atlas/getting-started/
- https://pandas.pydata.org/docs/reference/api/pandas.json_normalize.html
- https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style



