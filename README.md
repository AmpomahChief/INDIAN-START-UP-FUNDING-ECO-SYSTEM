# INDIAN-START-UP-FUNDING-ECO-SYSTEM
THE ECO SYSTEM OF INDIAN START-UP FUNDING (2018 -2022) - A DATA SCIENCE PROJECT.


PROJECT OBJECTIVE
The objective of the project is to Investigate the start-up funding eco-system in India from 2018 to 2021 and propose the best course of action forward for new start-ups.

Technologies Used: Python
Project Status: Completed 

DATA STRUCTURE.
The years under review are from 2018 to 2021. The data set is in four different csv files, each file corresponding to a year under review. Below are column names and descriptions. 
Column names and description:
•	Company/Brand: Name of the company/start-up
•	Founded: Year start-up was founded
•	Sector: Sector of service
•	What it does: Description about Company
•	Founders: Founders of the Company
•	Investor: Investors
•	Amount: Raised fund
•	Stage: Round of funding reached

QUESTIONS ASKED
These are questions that I seek to answer after processing and analyzing the data set
1.	Which sector has the most number of start-ups 
2.	What Sector had the most funding?
3.	What is the yearly average of funding received by Indian start-ups?
4.	What is the number of start-ups in each year?
5.	Which year of Start-Ups receive the most funding?
6.	Does the Location of a Start-Up influence investor decision?
7.	Which Investors made the most investment in Indian Start-Ups?


HYPOTHESIS 
•	Businesses in the tech sector are more likely to receive funding from investors than other sectors.

DATA PROCESSING AND ANALYSIS
The data used in this project are real data from 2018 to 2021 containing list of start-ups in India and funding received over the years under review.
The data processing was done using python Jupyter Notebook. Details of the entire process and analysis are explained infra.
NB: For better understanding of the data set I decided to explore and clean the years data of start-up funding separately, after which all will be merged for analysis.  
The cleaning done column by column to aid a systematic process.
Before I began processing and cleaning the data, I imported the necessary python libraries that I would need for my work. The libraries are listed below
	Numpy as np
	Pandas as pd
	Matplotlib.pyplot as plt
	Seaborn as sns
	Math
	waterfall_chart


1.	PROCESSING DATA SET FOR 2018 START-UP FUNDING

Column Names for 2018 data
Company Name  
Industry  
Round/Series  
Amount      
Location     
About Company

1.1.	Data EXPLORING 
1.1.1.	I began by exploring the data to get basic information about the data set such, number of rows and columns, names of columns, number of null values in each column and data types of each column. 
1.1.2.	A new column named ‘Year of funding was created to indicate the year the funding was received. (This was done for all other years.)  
1.2.	Cleaning the ‘INDUSTRY’ column: 
1.2.1.	Most cells in the industry column had more than one industry name so I decided to only the first industry name stated and discard the rest.
1.3.	Cleaning the ‘LOCATION’ column:
1.3.1.	The location record included the city, town and country. The town and city were stripped off and only the city remained. 
1.4.	Cleaning the AMOUNT column: The Amount column had figures in both Rupees and USD. It also contained. 
1.4.1.	I began cleaning the amount column by removing all commas ( , ) , hyphens( - ) and the dollars currency signs.
1.4.2.	A new column was created called ‘Amount RP’ to represent all figures recorded in rupees and data type was set to float. This was necessary to help convert them to USD.
1.4.3.	The amounts in the ‘Amount RP’ were converted into dollars by multiplying them with dollar rate as at December 2018.
1.4.4.	After converting them they added to the amounts in USD. The ‘Amount RP’ was dropped in other to have only one Amount column.
1.4.5.	All zero values in the amount column were replaced by null values.
1.4.6.	The null values (132 total) in the Amount column were filled with the median.
1.4.7.	The data type of the Amount column was changed to integer.
1.5.	Dropping and Renaming columns.
1.5.1.	The column names were changed from; "Company Name" to "Company/Brand", "Industry" to "Sector", "Location" to "HeadQuarter". This was necessary in other to make the column names consistent with the column names of the other years, since they will be merged after cleaning.
1.5.2.	The 'Round/Series' and ‘About Company' columns were dropped since it will not be needed for my analysis.



2.	PROCESSING DATA SET FOR 2019 START-UP FUNDING
Column Names for 2019 data
         Company/Brand
         Founded        
         HeadQuarter
         Sector            
         What it does    
         Founders   
         Investor     
         Amount($)
         Stage

2.1.	Data EXPLORING 
2.1.1.	Refer to 1.1.1
2.2.	Cleaning the AMOUNT column
2.2.1.	First, the Amount column was renamed from "Amount($)" to "Amount".
2.2.2.	Dollar signs and commas were removed .
2.2.3.	Cells in the Amount column were labeled with ‘Undisclosed’ was replaced with zero (0) value.
2.2.4.	The data type of the Amount column was changed from object to integer.
2.2.5.	Null values (12 in total) were filled with median of the Amount column. 
2.3.	Cleaning the FOUNDED column
2.3.1.	I checked for the null values in the founded column which totaled 25.
2.3.2.	The null values were filled with the actual year those start-ups were founded. The actual years were obtained from google.
2.3.3.	The data type was then changed from object/string to integer 
2.4.	Cleaning the HEADQUARTER column
2.4.1.	I checked for total number of null values. This totaled 19 null values.
2.4.2.	The null values were filled with the actual HeadQuarters of  those start-ups . The actual HeadQuarters were obtained from google.
2.5.	Cleaning the SECTOR column
2.5.1.	The sector column had 5 total null values 
2.5.2.	The null values were filled with the actual sector of  those start-ups . The actual sectors were obtained from google.
2.5.3.	The cells in the sector column had multiple issues such as spelling mistakes and mixed cases. I did some formatting in the column to capitalize all the entries in the column to fix some of those issues.
2.5.4.	I then passed in a function to efficiently group the sectors. Example sectors such as ‘food’, ‘food and beverages’, and ‘beverages’ will all be grouped under one sector ‘Food and Beverages.
2.6.	Dropping columns
2.6.1.	The 'What it does', 'Stage', and  'Founders' were dropped because they will not be needed in my analysis.




3.	PROCESSING DATA SET FOR 2020 START-UP FUNDING
Column Names for 2020 data
Company/Brand 
 Founded        
 HeadQuarter
 Sector         
 What it does
 Founders   
 Investor     
 Amount($)
 Stage          
 Unnamed: 9 

3.1.	Data EXPLORING 
3.1.1.	Refer to 1.1.1
3.2.	Dropping columns that are not needed.
3.2.1.	The 'What it does', 'Stage',  'Founders', and 'Unnamed: 9' were dropped because they are not needed in my analysis.
3.3.	Cleaning the ‘AMOUNT’ column
3.3.1.	The Amount column was renamed from ‘Amount($)’ to ‘Amount’
3.3.2.	The dollar sign, commas and other characters that are not needed were removed from the Amount column.
3.3.3.	The data type of the Amount column was changed from ‘object’ to ‘float’.
3.3.4.	I then checked for the null values which totaled 248.
3.3.5.	The null values were filled with the median
3.4.	Cleaning the ‘SECTOR’ column
3.4.1.	Refer to 2.5.2, 2.5.3, and 2.5.4
3.5.	Cleaning the ‘FOUNDED’ column
3.5.1.	I replaced Hyphens (-) as null values
3.5.2.	I checked for the null values in the founded column which totaled 25.
3.5.3.	I checked for the null values and it totaled 213.
3.5.4.	Refer to 2.3.1,  2.3.2,and 2.3.3. 
3.5.5.	The data type of he Founded column was changed from ‘float’ to ‘integer’
3.6.	Cleaning the ‘FOUNDED’ column
3.6.1.	The null values in the HeadQuarter column totaled 94
3.6.2.	Refer to 2.4.2
3.7.	Cleaning the ‘INVESTER’ column
3.7.1.	I checked for the null values in the  investor column which totaled 38.
3.7.2.	The null  values were replaced as ‘Unspecified’.

4.	PROCESSING DATA SET FOR 2021 START-UP FUNDING
Column Names for 2021 data
           Company/Brand 
           Founded        
           HeadQuarter 
           Sector          
           What it does 
           Founders      
           Investor        
           Amount($)    
           Stage .

4.1.	Data EXPLORING 
4.1.1.	Refer to 1.1.1
4.1.2.	The 'What it does', 'Stage', and  'Founders' were removed because they will not be needed for the analysis.
4.2.	Cleaning the ‘INVESTOR’ column
4.2.1.	The investor column had multiple investors in the records. I reduced the number of investors in a record by selecting only the first investor. The assumption is the first investor is primary investor.
4.2.2.	 The Investor column had 591 null values. They replaced as ‘Undisclosed’.
4.3.	Cleaning the ‘AMOUNT’ column
4.3.1.	Refer to 3.3.1, 3.3.2 and 3.3.3 
4.3.2.	I then checked for the null values which totaled 153.
4.3.3.	Refer to 3.3.5
4.4.	Cleaning the ‘HEADQUARTER’ column
4.4.1.	The HeadQuarter column had 1 missing value and it was filled in with the headquarters of the start-up.
4.5.	Cleaning the ‘FOUNDED’ column
4.5.1.	The Founded column also had 1 missing value. The right value was obtained and filled in.
4.5.2.	The data type of the founded column was changed from ‘object’ to ‘float'

5.	MERGING ALL DATA
5.1.	All data sets were concatenated from 2018 to 2021.
5.2.	After merging them I did some additional cleaning. Some cities had two different names ( an old and new name. example ; ‘Gurugram’ is the new name for ‘Gurgaon’ , so I replace all Gurgaon with the new name.) 



6.	DATA ANALYSIS AND VISUALIZATION TO ANSWER QUESTIONS
6.1.	Q1. Which sector has the most number of start-ups
To get the sector with the most number of start-ups, the data set was grouped the start-up and the sector they represent and the top 10 was filtered out. With this Fintech (Tech in the finance sector) topped with 273 start-ups, followed by Tech with 269 start-ups and Edtech( Tech in the education sector). With 226. 

With this we can see that the Tech sector in general has the most number of start-ups compared to other sectors like Health and wellness, and Food and beverages.

The grouped data set was visualized using bar chart. 

6.2.	Q2. What Sector had the most funding?
To answer the question the data was grouped into sectors and the total amount that went to the sector. The top 10 was filtered out .

 Fintech, Tech and Edtech came up as top 3 sectors to receive the most funding. Other sectors included Automotive, Hospitality and E-Commerce

The results were plotted on a horizontal bar graph to visualize the results.


6.3.	Q3. What is the yearly average of funding received by Indian start-ups?
For every year the mean/average amount of funding received calculated. This gives a perspective on how much a start-up is likely to receive as funding. 

2021 came up first with the highest average of funding for a start-up, followed by 2020, 2019 and 2018.

The data was visualized using a vertical bar plot.

6.4.	Q4. What is the number of start-ups in each year?
To answer this question the number of start-ups in each year was summed up. 
This gives some perspective on why a particular year would receive more funding than other years. For example, if 2021 has the highest number of start-ups, then it will make since that 2021 also has the highest amount of funding received by start-ups.



6.5.	Q5. Which year of Start-Ups receive the most funding?
The purpose of this question is to find out if start-ups in a particular year has influences investor decision. To get the answer to the question start-ups were grouped according to the year started and the amount of funding that particular year received. 

After the grouping them this way, start-ups in 2018 came up with the most funding, followed by 2006, 2015,2011 and so on.

The out come was visualized using a line plot to indicate start-up year and Amount of funding received.

6.6.	Q6. Does the Location of a Start-Up influence investor decision?
The reason for this Question is to find out if investors favor start-ups in a particular done other locations. To get the answer to this question  the data was grouped according to the Location of the start-up and the Amount of funding that went to start-ups in that location.

Mumbai came up as the city to have received the most funding , Bangalore, Gurugram, and Delhi also followed up respectively. 

6.7.	Q7. Which Investors made the most investment in Indian Start-Ups?
The purpose of this Question was to find which inveators are the most active in funding start-ups. To get this the Investors were group according to how much investment they made in start-Ups.

Mubadala Investment company came up with the highest funding for start-ups , It was followed by Dragoneer Investment Group and Google respectively.

The results were visualized using a horizontal bar plot.



CONCLUSION
The Start-Up eco system in Indian is very diverse and has lots start-ups springing up in various sectors of the economy.  
The goal of this project was to find if Start-ups in the tech sector are more likely to receive funding than other sectors. From the findings it can be concluded that it is indeed true that the tech (Especially Fintech) sector received more funding than any other sector. 
Whereas this evidently true it could have also been influence by the COVID 19 pandemic which started in late 2019. This could have forced the tech sectors to flourish due to the fact that things were done remotely. 
In conclusion, the Tech sector receives more funding than any other sector, this implies the business start-ups should consider venturing into tech products or services. Start ups should also consider the location of their business. Cities such as Mumbai, Bangalore and Delhi also attract more funding from investors.


