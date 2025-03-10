# PySpark ETL Pipeline

## Overview
This project demonstrates how to set up a PySpark environment in Google Colab, initialize a PySpark session, and load a dataset for further processing. The dataset contains temperature data for various countries spanning multiple years.

## Prerequisites
Before running the project, ensure you have the following:
- Google Colab or a local environment with Python installed
- PySpark installed (`pip install pyspark`)
- A CSV dataset (temperature.csv) stored in your working directory

## Installation
If you're using Google Colab, install PySpark using the following command:
```python
!pip install pyspark
```

## Initializing a PySpark Session
To interact with Spark, initialize a Spark session as shown below:
```python
from pyspark.sql import SparkSession

spark = SparkSession.builder \
    .appName("ETL Pipeline") \
    .getOrCreate()
```

## Extract: Loading the Dataset
Load the CSV file into a PySpark DataFrame:
```python
file_path = "/content/temperature.csv"
df = spark.read.csv(file_path, header=True, inferSchema=True)
```

### Display Schema & Preview Data
```python
df.printSchema()
df.show(5)
```
This command will display the structure of the dataset, including column names, data types, and sample records.

## Dataset Structure
The dataset contains the following columns:
- `ObjectId`: Unique identifier
- `Country`: Country name
- `ISO2`: ISO 2-letter country code
- `ISO3`: ISO 3-letter country code
- `F1961` to `F2022`: Temperature values for each year from 1961 to 2022

## Next Steps
- Perform data cleaning and transformation
- Conduct exploratory data analysis (EDA)
- Implement data aggregation and processing using Spark SQL
- Save processed data for further analysis

## License
This project is open-source and available for modification and use under the MIT License.

