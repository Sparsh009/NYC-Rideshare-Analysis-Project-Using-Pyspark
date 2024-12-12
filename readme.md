
# NYC Rideshare Analysis Project

## Overview
This project involves analyzing a dataset from the New York 'Uber/Lyft' service, covering rides from January 1, 2023, to May 31, 2023. The data, pre-processed by the NYC Taxi and Limousine Commission (TLC), is used to perform various big data tasks using Apache Spark, showcasing data manipulation, aggregation, and analysis techniques.

## Dataset Description
The dataset consists of rideshare data with details about each trip including the business (Uber or Lyft), pickup and dropoff locations, trip length, times, fares, and payments. Two main CSV files are used:
- **rideshare_data.csv**: Contains detailed records of rideshare trips.
- **taxi_zone_lookup.csv**: Provides mapping for location IDs to boroughs and zones.

## Prerequisites
- Apache Spark 3.x
- Python 3.x
- Access to a Spark cluster for large-scale data processing

## Tasks and Questions

### Task 1: Merging Datasets
#### Question:
Merge `rideshare_data.csv` with `taxi_zone_lookup.csv` to enhance location data readability and convert date formats for better analysis.
#### APIs Used:
- `spark.read.format`, `withColumnRenamed`, `join`, `broadcast`, `withColumn`, `from_unixtime`
#### Challenges:
- Join conditions complexity and optimization issues addressed by using broadcast join.
#### Insights Gained:
- Mastered data merging techniques and performance optimization in Spark through broadcast joins.
<img width="333" alt="image" src="https://github.com/user-attachments/assets/e776087f-eaed-421e-8dcd-f92d73a8c8b1" />



### Task 2: Aggregation of Data
#### Question:
Aggregate data to compute the number of trips per business per month, calculate profits, and analyze drivers' earnings.
#### APIs Used:
- `withColumn`, `concat_ws`, `groupBy`, `count`, `agg`, `sum`, `orderBy`
#### Challenges:
- Date formatting issues resolved by casting the date column to the correct type.
#### Insights Gained:
- Deepened understanding of Spark's aggregation capabilities to draw business insights.
<img width="452" alt="image" src="https://github.com/user-attachments/assets/20e47973-5b49-4d97-adb4-0e1c023bd1f0" />
<img width="393" alt="image" src="https://github.com/user-attachments/assets/258be418-9a2e-4943-83c6-9c9056cc35dc" />





### Task 3: Top-K Processing
#### Question:
Identify the top 5 popular pickup and dropoff boroughs each month and analyze the top 30 most profitable routes.
#### APIs Used:
- `row_number`, `over`, `show`, `concat`
#### Challenges:
- Developing the logic for calculating routes; resolved through column concatenation.
#### Insights Gained:
- Enhanced skills in using SQL queries within Spark for complex data ranking and aggregation.
  <img width="342" alt="image" src="https://github.com/user-attachments/assets/cae2e0d4-785e-407c-b36d-e0e864135865" />


### Task 4: Average of Data
#### Question:
Calculate average driver pay and trip lengths during different times of the day to determine the most profitable periods.
#### APIs Used:
- `groupBy`, `agg`, `avg`, `orderBy`
#### Insights Gained:
- Analyzed time-based variations in pay and trip length to suggest optimal operating times for drivers.
  <img width="452" alt="image" src="https://github.com/user-attachments/assets/daba32e4-db18-4ee5-b682-a2bc218f7928" />


### Task 5: Finding Anomalies
#### Question:
Analyze and identify anomalies in average waiting times during January.
#### APIs Used:
- `filter`, `groupby`, `avg`, `orderby`
#### Challenges:
- Configuration issues with S3 buckets, resolved through careful documentation review.
#### Insights Gained:
- Gained proficiency in anomaly detection and understanding the impact of external events on service metrics.
    
       

### Task 6: Filtering Data
#### Question:
Explore trip data by filtering counts that fall within specific ranges for different boroughs and times of the day.
#### APIs Used:
- `filter`, `groupby`, `count`, `show`, `withColumn` with `lit`
#### Challenges:
- Mastering the `filter` function to effectively specify data subsets.
#### Insights Gained:
- Improved data filtering techniques to focus on specific aspects of the data.

## Running the Analysis
To execute the Spark jobs, use the command:
```bash
spark-submit --master <master-url> src/<spark-script>.py
```

## Contributing
Contributions to this project are welcome. Please fork the repository, make your changes, and submit a pull request.

## License
This project is licensed under the MIT License. See the LICENSE file for more details.
```
