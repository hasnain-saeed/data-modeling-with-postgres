# Data Modeling with Postgres

## Summary
This project deals with data modeling with postgres for a music streaming app by 'Sparkify'. Sparkify has collected data of songs and user activity from their app in the form of JSON files and wants to analyze what songs users are listening to.

This project creates an ETL pipeline for this purpose and stores data in the postgres database using a star schema. In this schema we create fact and dimension tables; fact table having our quantitative business information (songs users are listening to) and dimension tables having descriptive attributes (song and user details etc.) related to fact table.

## Usage
```etl.py``` is the main python file for this project which creates ETL pipeline. Before running this file make sure to run ```create_tables.py``` in your current workspace.
```
/home/workspace# python3 create_tables.py
/home/workspace# python3 etl.py
```

Each time you run the cells in the ```test.ipynb```, you need to restart this notebook to close the connection to your database. Otherwise, you won't be able to run your code in ```create_tables.py```, ```etl.py```, or ```etl.ipynb``` files since you can't make multiple connections to the same database (in this case, sparkifydb).
## Project Structure
This repository includes a data folder which contains song_data and log_data. In addition to data folder project contains 5 files:

1. ```test.ipynb```: This file displays the first few rows of each table in order to test your database
2. ```create_tables.py```: This file drops and creates your tables and you need to reset your tables before each time you run your ETL scripts.
3. ```etl.ipynb```: This file contains detailed instructions on the ETL process for each of the tables.
4. ```etl.py``` This file creates the ETL pipeline, reads and processes files from song_data and log_data and loads them into your tables.
5. ```sql_queries.py``` This file contains all sql queries used in above three files.

## Database Design and ETL Pipeline

This project defines fact and dimension tables for a star schema for user-songplay analytic focus, and writes an ETL pipeline that transfers data from files in two local directories into these tables in Postgres using Python and SQL.

### Schema
<img src="schema/sparkify" alt="Logo" width="80" height="80">
