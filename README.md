# nosqlFoodAnalysis

The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. You've been contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

Part 1: Database and Jupyter Notebook Set Up

1. Use NoSQL_setup_starter.ipynb for this section.Import the data provided in the establishments.json file from your Terminal. Name the database uk_food and the collection establishments. Copy the text you used to import your data from your Terminal to a markdown cell in your notebook.

2. Within your notebook, import the libraries you need: PyMongo and Pretty Print (pprint).

3. Create an instance of the Mongo Client.

4. Confirm that you created the database and loaded the data properly:
-List the databases you have in MongoDB. Confirm that uk_food is listed.
-List the collection(s) in the database to ensure that establishments is there.
-Find and display one document in the establishments collection using find_one and display with pprint.

5. Assign the establishments collection to a variable to prepare the collection for use.

Part 2: Update the Database

Use NoSQL_setup_starter.ipynb for this section.

The magazine editors have some requested modifications for the database before you can perform any queries or analysis for them. Make the following changes to the establishments collection:

1. An exciting new halal restaurant just opened in Greenwich, but hasn't been rated yet. The magazine has asked you to include it in your analysis. Add the following information to the database:

![Screen Shot 2023-07-19 at 10 12 22 PM](https://github.com/kshirazi5/nosql-challenge/assets/116853144/2d3d9f85-d628-4054-b2f7-2eac02715eec)


2. Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the BusinessTypeID and BusinessType fields.

3. Update the new restaurant with the BusinessTypeID you found.

4. The magazine is not interested in any establishments in Dover, so check how many documents contain the Dover Local Authority. Then, remove any establishments within the Dover Local Authority from the database, and check the number of documents to ensure they were deleted.

5. Some of the number values are stored as strings, when they should be stored as numbers.
 1. Use update_many to convert latitude and longitude to decimal numbers.
 2. Use update_many to convert RatingValue to integer numbers.

Part 3: Exploratory Analysis

Eat Safe, Love has specific questions they want you to answer, which will help them find the locations they wish to visit and avoid.

Use NoSQL_analysis_starter.ipynb for this section of the challenge.

Some notes to be aware of while you are exploring the dataset:
RatingValue refers to the overall rating decided by the Food Authority and ranges from 1-5. The higher the value, the better the rating.

Note: This field also includes non-numeric values such as 'Pass', where 'Pass' means that the establishment passed their inspection but isn't given a number rating. We will coerce non-numeric values to nulls during the database setup before converting ratings to integers.

The scores for Hygiene, Structural, and ConfidenceInManagement work in reverse. This means, the higher the value, the worse the establishment is in these areas.

Questions:

1. Which establishments have a hygiene score equal to 20?
![Screen Shot 2023-07-19 at 10 20 54 PM](https://github.com/kshirazi5/nosql-challenge/assets/116853144/a3c7f43c-a0c5-4e79-9106-a601556aec82)

2. Which establishments in London have a RatingValue greater than or equal to 4?
![Screen Shot 2023-07-19 at 10 23 05 PM](https://github.com/kshirazi5/nosql-challenge/assets/116853144/5f0d664d-4db3-4230-b5e4-30321dab0575)

3. What are the top 5 establishments with a RatingValue rating value of '5', sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?
![Screen Shot 2023-07-19 at 10 24 10 PM](https://github.com/kshirazi5/nosql-challenge/assets/116853144/d4cc26b5-0022-4252-bce9-d0c2194addd9)

4. How many establishments in each Local Authority area have a hygiene score of 0?

![Screen Shot 2023-07-19 at 10 24 46 PM](https://github.com/kshirazi5/nosql-challenge/assets/116853144/4280fdad-7dd0-4d91-aa54-ca8c522e3f95)




