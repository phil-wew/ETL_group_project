# ETL_group_project

Extract: Our team chose to look data that included populations and median home prices from 2010 through 2019. The datasets were extracted from CSV files downloaded from Kaggle. 

Transform: We used both Jupyter Notebook and SQL pgAdmin4 to input and transform the data into actionable data for results. 
Utilizing Jupyter Notebook, we split the home pricing data into average years from the monthly averages that were included in the raw CSV file. We also utilized the raw CSV population data to combine with the average yearly prices to create a single dataset with the available data. We did run into issues with the merging of monthly to yearly averages but were able to break each year out into its own dataframe to work around the issue. Once we brought all of the data into on dataframe, we ran into an issue where we didn’t have data due to a space in-front of the name ‘State’. We were able to utilize the scrape function to remove the extra space and return clean data. Our final step was to remove columns that did not include final data we were seeking. From this we were able to export two clean CSV files, one with population data and one with median home price data from Jupyter Notebook

Utilizing the SQL pgAdmin4 tool, we were able to upload and merge both raw CSV files (population and median prices) and removed any additional cities that did not contain data in both CSV files and any additional data that was not relevant to our final table output. We also utilized the SQL pgAdmin4 tool to upload both raw CSV files to combine the data into one merged CSV/Table that showed the relation of city population and average home prices from 2010 to 2019. 

Some of the issues we worked around within SQL pgAdmin4 analysis included:
1) It didn’t like comma in the long numbers, even though they weren’t really there 
2) There were some fields labeled as (X) instead of blank 
3) We had some fields typed as int when they should have been float 
4) Added underscores to beginning of column names that were just numbers 
5) Took away the “not null” that QDB auto-generated 
6) When splitting the state from the city, the state ended up with a space at the beginning (which I couldn’t see), which caused the joins based on state to not work.

Load: We executed a SQLite export from Jupyter Notebook via SQLAlchemy engine.excute to export the data out as SQLite dataset. We also utilized SQL pgAdmin4 to export a CSV file with the combined data providing two datasets for other users

