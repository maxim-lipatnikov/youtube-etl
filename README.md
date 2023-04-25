# YouTube Trending Videos ETL Project
This is a team project done on the second year of my university.

## The Idea of the Project
1. Finding a dataset on Kaggle and defining the purpose of analysis,
2. Cleaning and preprocessing the data to make it usable in the ETL pipeline,
3. Splitting the dataset into two data sources with different formats (e.g. CSV and JSON),
4. Designing and developing a data warehouse and a data mart based on the structure of the downloaded dataset and the purpose of analysis,
5. Creating an ETL pipeline to integrate the data step-by-step from the sources into the data mart, including setting a mechanism of exporting corrupt data into separate CSV file,
6. Building an OLAP cube based on the Facts table.

## Tech Stack
1. Microsoft Excel - Data Preprocessing
2. Microsoft SQL Server & Microsoft SQL Server Management Studio - DWH
3. Microsoft SSIS - ETL
4. Microsoft SSAS - OLAP

## Results
1. The [dataset](https://www.kaggle.com/datasets/datasnaek/youtube-new) was selected among others and downloaded from Kaggle, and the purpose of the data integration was defined - **to have an ability to analyze trending videos based on the number of likes/dislikes, views, category, and other features**
2. The data was cleaned from mistakes and null values, then the dataset was splitted into two different files - CSV and JSON
3. The initial dataset did not contain enough columns to design a full DWH and separate data marts - in this project the DWH is basically the data mart itself (which was designed as a "snowflake")

This is a diagram of a data mart:
![](https://github.com/maxim-lipatnikov/youtube-etl/blob/main/snowflake.png)

4. The autoincrement keys and all relations between the tables were set
5. The connection to the DWH from the Microsoft SSIS was set, and the ETL pipeline was developed, consisting of these steps:
- Clearing the Staging Area,
- Clearing the Dimensions and Facts tables,
- Importing the data to Staging Area,
- Importing the data from Staging Area to one of the Dimensions,
- Updating the Dimension's foreign key in Staging Area,
- Repeating this for every Dimension of the data mart,
- Importing the data to Facts table.

This is a diagram of the whole data flow:

![Whole data flow](https://github.com/maxim-lipatnikov/youtube-etl/blob/main/pipeline.png)

And this is what ETL pipeline in Microsoft SSIS looks like:

![ETL in SSIS](https://github.com/maxim-lipatnikov/youtube-etl/blob/main/ETL%20control%20flow.png)

6. The data mart then was used for building an OLAP cube in Microsoft SSAS, which was used for basic Excel visualizations.
