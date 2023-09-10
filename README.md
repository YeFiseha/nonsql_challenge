# nonsql_challenge

UK Food Standards Agency evaluates various establishments across the United Kingdom and gives them a food hygiene rating. We are contracted by a food magazine, Eat Safe, Love, to evaluate some of these ratings data to help their journalists and food critics decide where to focus future articles.

# Findings

Part 1: Database and Jupyter Notebook Set Up

•	The data provided in the - establishments.json- file is imported
•	The database is Named uk_food
•	The collection is named - establishments
•	One document is found and displayed in the establishments collection 
•	The establishments collection is assigned to a variable

Part 2: Update the Database

•	A new halal restaurant “Penang Flavours" that just opened in Greenwich, has been added to the database
•	A query is performed to find the BusinessTypeID for "Restaurant/Cafe/Canteen" and the BusinessTypeID and BusinessType for "Restaurant/Cafe/Canteen" are listed
•	The "Penang Flavours" document is updated with the correct BusinessType and BusinessTypeID
•	A query is performed to delete all the documents in the collection where LocalAuthorityName is "Dover" 
•	A count documents check is performed before and after the removal of the Dover documents to ensure the documents were removed
•	A query is performed to convert the latitude and longitude fields from strings to decimal numbers and convert RatingValue to integers 

Part 3: Exploratory Analysis

1.	Establishments with a hygiene score of 20   
•	Number of establishments with hygiene score of 20 are identified
•	The results are converted to a Pandas DataFrame, number of rows in the DataFrame are identified, and the first 10 rows are displayed

2.	Establishments in London with a RatingValue greater than or equal to 4
   
•	The London establishments with a RatingValue greater than or equal to 4 are located
•	The correct number of establishments with a RatingValue greater than or equal to 4 are determined
•	The first result is printed 
•	The results are converted to a Pandas DataFrame, the number of rows in the DataFrame are identified and the first 10 rows are displayed

3.	The top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score (in ascending order), and nearest to the newly restaurant "Penang Flavours"
   
•	The search is done for establishments within 0.01 degree on either side of the latitude and longitude from the location of "Penang Flavours"
•	The search is limited to establishments with a RatingValue of 5
•	The establishments are sorted in ascending order based on their respective hygiene scores
•	The limit to the search results is 5 
•	The results are printed 
•	The results are converted to a Pandas DataFrame and displayed

4.	Establishments in each Local Authority area with a hygiene score of 0. The results are sorted from highest to lowest (descending order), and the top ten local authority areas are printed.
   
•	The aggregation pipeline is built including a match query, group, and sort 
•	The match query matches documents with a hygiene score of 0
•	The group query groups documents based on LocalAuthorityName and counts the documents 
•	The sort query sorts the count of the documents in descending order 
•	Thee aggregation pipeline integrates the match, group and sort query values
•	The results from the aggregation pipeline are cast as a list and then saved to a variable
•	The first ten results are printed 
•	The results are converted into a Pandas DataFrame, number of rows are determined, and the first 10 rows are displayed

# References

NoSQL_setup_starter.ipynb contains the data analysis for parts 1 (Database and Jupyter Notebook Set Up) and 2 (Update the Database) of the assignment

NoSQL_analysis_starter.ipynb contains the data analysis for Part 3 'Exploratory Analysis' of the assignment

Resources folder contains the dataset
