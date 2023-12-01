# Crowdfunding_ETL
Module13

In the first part of the challenge, we were asked to create a repo called Crowdfunding_ETL and using the provided starter code we created the category and subcategory, campaign, and contact data frames. First, we split the category and subcategory column from the crowdfunding.xlsx into a separate category column and a subcategory column, then used a for loop to create category_id and subcategory_id columns. For the campaigns data frame, we cleaned the crowdfunding.xlsx to contain only the desired columns: cf_id, contact_id, company_name, description, goal. pledged, outcome, backers_count, country, currency, launched_date, end_date, category_id, and subcategory_id. For the contacts data frame, we extracted values from the rows of data from the dictionary and created individual columns for the desired variables: contact_id, name, and email. 


In the second part of this challenge we were tasked to create a crowdfunding database. To begin we sketched an ERD of the crowdfunding tables using cf_id as the primary key for the campaigns data frame, contact_id as the foreign key for the contacts data frame, category_id for the foreign key for the category data frame, and subcategory_id for the subcategory data frame. Next, we imported the schema into Postgres to create the crowdfunding_db. To get the data into the appropriate tables we had to create the tables and import the CSV files in a specific order: contacts, category, subcategory, and campaigns. Finally, we loaded in the data with the “select * from” statement. 


Through the use of Stack Overflow, Github, Rexegg, the help of TAs we were able to find the code for:
- pd.to_datetime(dataframe["column"], unit='s', utc=True).dt.strftime('%Y-%m-%d') which formatted the integer values for the launched_date and end_date columns to date time variables.
- converted_data = json.loads(row[0]) which stored the data from the first column in the contacts data frame into a jason-formatted string.
- https://rexegg.com/regex-quickstart.html for extracting values from the contact dictionary to add to new columns for the regex option. 
