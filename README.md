# Baby-Names-ETL

## Extract: Finding Data

**This project was completed using two different datasets from Data World.**

The first dataset is a csv file containing the most popular male and female baby names in the US from 1880-2018.

- *[Most Popular National Baby Names](https://data.world/nkrishnaswami/us-ssa-baby-names-national)*

The second dataset is a csv file containing the top 25 most popular male and female baby names in CA from 2005-2020.

- *[Most Popular Baby Names in California](https://data.world/chhs/4a8cb74f-c4fa-458a-8ab1-5f2c0b2e22e3)*

## Transform: Data Cleanup & Analysis

**Once I had identified my datasets, I performed ETL on the data.**

*Steps:*

1. Reviewed the two datasets and thought about how I wanted to transform them. I needed them to display the same type of information because I wanted to combine the two dataframes into one for my database. I determined that I wanted to display only data for the year 2018 as it was the most current year for the National dataset.

2. Starting with the National dataset, I changed the "rank" column from float to an integer as the decimal place was unnecessary. Then, I used conditionals to filter out only the top 25 male and female baby names from the year 2018. I renamed columns and then sorted the values by rank and gender so that the number one female name and number one male name were displayed next to each other and so there was a consistent "Female, Male, Female, Male" pattern to the dataframe. Finally, I reorganized the columns in a way that read more logically to me.

3. Moving onto the California dataset, I followed most of the same process trying to make the two datasets look similar and consistent. I filtered out only data from the year 2018 and made sure the names were capitalized correctly. I renamed the columns, sorted by rank and gender, converted the gender values to "F" and "M" to match the National Dataset, and reorganized the columns.

4. Finally, I joined the two tables on rank, gender, and year and reorganized the columns to display a clean dataframe called "clean_top_baby_names" that had all the information I wanted shown in a consistent manner.

## Load: SQL Database

*Steps:*

1. For the loading process, I created a relational database in pgAdmin called babynames_db that I would save my final table into.

2. Next, I connected my Jupyter Notebook to SQL using my connection string and creating an engine.

3. Finally, I loaded my cleaned final table into SQL using .to_sql() and named the SQL database "top_25_baby_names".

4. I confirmed the data had been added by querying the table in my Jupyter Notebook and by double checking in pgAdmin.

5. I chose to load the final cleaned table into a PostgreSQL relational database because it was the management system that I was most comfortable with and I was able to work with it efficiently.
