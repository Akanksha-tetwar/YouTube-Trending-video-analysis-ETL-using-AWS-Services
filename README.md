# YouTube-Trending-video-analysis-ETL-using-AWS-Services-

In this project I have used the Trending YouTube Video Statistics  data from Kaggle to analyze and prepare it for usage.
This dataset has two kinds of files: JSON and CSV files. The process goes as follows:
1.	Uploaded the data from my local machine into the S3 bucket using AWS CLI commands while trying to maintain a proper file organization. Stored the JSON and CSV files in separate folders.
2.	Used AWS Glue Catalog to crawl the data from JSON and CSV files from the raw bucket which would be stored in a separate database.
3.	On facing issues raised due to the data in the JSON format, create a Python function using AWS Lambda to clean them and convert them into parquet format. 
4.	Created a trigger on this Lambda function so as to run every time new data is being added to S3 bucket and the output was stored in a new database in Athena.
5.	Converted the CSV files into parquet format as well using AWS Glue ETL.
6.	Created a new Glue Crawler to crawl the clean data into the database.
7.	Now when all the clean data from the parquet files (converted from CSV and JSON files) is present in the same database, developed an ETL job using AWS Glue Studio to join both the tables and store it in a separate S3 bucket intended to use for BI purposes.
8.	The data is now ready to be used for building dashboards out of it. 
I decided to analyze this data for finding out the popularity, most liked video categories, video reach, engagement and likes to views comparison of channels in UK and Canada.

Dataset used from : https://www.kaggle.com/datasets/datasnaek/youtube-new

