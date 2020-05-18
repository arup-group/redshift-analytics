# Data warehouse with AWS S3 and Redshift for analytics

In this project, AWS S3 and Redshift are used to build an ETL pipeline for storing song and user data in a Data Warehouse that is
optimized for analytics, thus enabling the platform owner to continue finding insights in what songs their users are listening to.

The pipeline extracts information about songs, artists and events that are stored as JSON files in two S3 buckets. It then stages the
data in Redshift and transforms it into a star schema'ed Data Warehouse.

### Schema definition

The data is transformed into a star schema, with the aim of minimizing JOIN operations and enabling fast read queries for analytics.

The following tables are included in the schema:

Fact Table

    songplays - records in event data associated with song plays
    
Dimension Tables

    users - users in the app
    songs - songs in music database
    artists - artists in music database
    time - timestamps of records in songplays broken down into specific units

The Data Warehouse also includes two staging table for the song dataset and events dataset, respectively.


### ETL pipeline
Python 3 is used in the project to connect to the redshift cluster and execute the ETL steps. SQL queries are defined in sql_queries.py that contain
all operations for the ETL process.

### Running the pipeline
1. Create the tables by running create_tables.py
2. Execute the ETL process by running etl.py
