# ny_weather_historical_data_pipeline

An automated serverless data engineering pipeline that handles New York historical weather data data through a serverless data pipeline using AWS cloud services to extract and transform the data and Grfana to load it (visualisations).

## Data Source
This project has been made based on the weather data availale within [Open meteo API](https://open-meteo.com/), API calls have been made to retrieve the project data.


## Project Architecture
![Project Pipeline](https://github.com/BillelBenoudjit/ny_weather_historical_data_pipeline/blob/main/project_pipe.png)


## Used Tools
- **AWS S3**
    - Save API data and AWS Athena queries results.
- **AWS Lambda**
    - Ingest data from the API to AWS S3 using Kinesis data firehose.
- **AWS Kinesis Data Firehose**
    -  Handle API data ingestion from Lambda to S3.
- **AWS Athena**
    -  Analyze API data directly saved in S3 using standard SQL.  
- **AWS Glue**
    - Transform Data through Python script.
    - Perform data quality checks.
    - Save the output data to a table stored as Parquet files.
    - Build a workflow based on the jobs above to get a final table with the transformed and checked API data.
- **Grafana**
    - Build a dashboard with visualizations based on the final obtained data from AWS. 


## Final output
The final output is a snapshat from Grafana available [here](https://billelbenoudjit.grafana.net/dashboard/snapshot/xBJ402a5JCZHNojSAPb56Zv1HU8MYjkV).
