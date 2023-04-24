# YouTube ETL Project
This is a team project done on the second year of my university.

## The Idea of the Project
1. Find a dataset on Kaggle,
2. Clean and preprocess the data to make it usable for ETL processes,
3. Split the dataset into two data sources with different formats (i.e. CSV and JSON)
4. Design and develop a data warehouse and a data mart based on the downloaded dataset,
5. Create an ETL pipeline consisting of these steps:
- Clear the Staging Area,
- Clear the Dimemsions and Facts tables,
- Import the data to Staging Area,
- Import the data from Staging Area to one of the Dimensions,
- Update the Dimension's foreign key in Staging Area,
- Repeat this for every Dimension of the data mart,
- Import the data to Facts table.
6. Build an OLAP cube based on the Facts table.

## Tech Stack
1. Microsoft Excel,
2. Microsoft SQL Server & Microsoft SQL Server Management Studio,
3. Microsoft SSIS
4. Microsoft SSRS

## Results
1. The [dataset](https://www.kaggle.com/datasets/datasnaek/youtube-new) was downloaded from Kaggle,
2. 
