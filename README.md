# Data Modeling with Postgres

## Data Created
This project is created at 24-04-2020

## Description 
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

We will apply what we have learned on data modeling with Postgres and build an ETL pipeline using Python. To complete the project,, and write an ETL pipeline that transfers data from files in two local directories into these tables in Postgres using Python and SQL.

## Database schema design and ETL process
 we will need to define fact and dimension tables for a star schema for a particular analytic focus.Moreover the schema is defines as following:
 - **Fact Table** 
    - songplays - records in log data associated with song plays i.e. records with page NextSong:
         - songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent
 - **Dimension Tables**
    - users - users in the app
        - user_id, first_name, last_name, gender, level
    - songs - songs in music database :
        - song_id, title, artist_id, year, duration
    - artists - artists in music database
        - artist_id, name, location, latitude, longitude
    - time - timestamps of records in songplays broken down into specific units
        - start_time, hour, day, week, month, year, weekday
        
![song_ERD](Song_ERD.png)

## Files used

### 1. sql_queries.py
In this file is used to write down ad-hoc queries of creating, inserting, dropping tables

### 2. create_tables.py
Once we have the queries, this file we will:
    a. create the connection
    b. drop the tables if exist
    c. create all necesary the tables if not exist
    
### 3. etl.py
Once creating the tables, we performance an ETL pipeline from log_data, song_data insert into 5 tables created in database sparkify.

## How to run the python scripts
Open a terminal and introduce the following code to file the files:
```
python filename.py
```