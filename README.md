# nosql-challenge Eat Safe, Love: UK Food Establishments Database Analysis

## Instructions

The UK Food Standards Agency evaluates various establishments across the United Kingdom and gives them a food hygiene rating. You've been contracted by the editors of a food magazine, *Eat Safe, Love*, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

## Part 1: Database and Jupyter Notebook Set Up

First, import the data provided in the `establishments.json` file from your Terminal. Name the database `uk_food` and the collection `establishments` using the following command:


```bash 
mongoimport --db uk_food --collection establishments --file /path/to/establishments.json --jsonArray
```


Within your Jupyter notebook, import the necessary libraries (`PyMongo` and `pprint`), create an instance of the Mongo Client, and confirm that the database and collection were created and loaded properly. List all databases to ensure `uk_food` is listed, list collections in the `uk_food` database to ensure `establishments` is there, and display one document from the `establishments` collection. Assign the `establishments` collection to a variable for use.

## Part 2: Update the Database

Insert a new halal restaurant "Penang Flavours" in Greenwich. Then, find the `BusinessTypeID` for "Restaurant/Cafe/Canteen" and update the new restaurant with the found `BusinessTypeID`.

Next, check how many documents contain the Dover Local Authority, remove any establishments within the Dover Local Authority, and confirm deletion by checking the number of documents again.

Use `update_many` to convert latitude and longitude to decimal numbers, and to convert `RatingValue` to integer numbers. Coerce non-numeric `RatingValue` entries to nulls before converting ratings to integers.

## Part 3: Exploratory Analysis

### Establishments with Hygiene Score Equal to 20
Find establishments with a hygiene score of 20. Use `count_documents` to display the number of documents in the result, display the first document in the results using `pprint`, and convert the result to a Pandas DataFrame. Print the number of rows and display the first 10 rows of the DataFrame.

### Establishments in London with RatingValue >= 4
Find establishments in London with a `RatingValue` greater than or equal to 4. Use `count_documents` to display the number of documents in the result, display the first document in the results using `pprint`, and convert the result to a Pandas DataFrame. Print the number of rows and display the first 10 rows of the DataFrame.

### Top 5 Establishments with RatingValue 5, Sorted by Lowest Hygiene Score, Nearest to "Penang Flavours"
Search within 0.01 degree on either side of the latitude and longitude for establishments with a `RatingValue` of 5, sort by hygiene score, and limit results to the top 5 establishments. Print the number of establishments found, display the first document, and convert the result to a Pandas DataFrame. Print the number of rows and display the first 10 rows of the DataFrame.

### Number of Establishments in Each Local Authority with a Hygiene Score of 0
Create a pipeline to match establishments with a hygiene score of 0, group matches by Local Authority, and sort matches from highest to lowest. Print the number of documents in the result, display the first 10 results using `pprint`, and convert the result to a Pandas DataFrame. Print the number of rows and display the first 10 rows of the DataFrame.





