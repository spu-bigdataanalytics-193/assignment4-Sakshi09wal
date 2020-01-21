# :penguin: Assignment 3 - Spark :penguin::trophy:


## About Dataset

The data consists of flight arrival and departure details for all commercial flights within the USA, from October 1987 to April 2008. 
We have a dataset of size 1.6 GB (compressed, and 12 GB when uncompressed), with the records of nearly 120 million records. Our goal is to use map-reduce algorithm to get the **count** of **number of flights** for each carrier.
Each row represents an individual flight record with details of that flight in the row. The information are:

- Time and date of arrival
- Originating and destination of airports
- Amount of time for a plane from taxi to takeoff

You can find more information about this dataset in the website of [Statistical Computing](http://stat-computing.org/dataexpo/2009/).



## Assignment Instructions

For calculating the number of flights for each carrier using Spark and pyspark library. Following is the set of things i have to complete for this:

1. Prepare Spark Tools
2. Complete carrier count example

### 1. Spark Tools

There are few ways of using spark. 

- Using [Databricks](https://community.cloud.databricks.com/)
- Using [Google Colab](https://colab.research.google.com/)


``` py
# install java libs and spark.
! apt-get install openjdk-8-jdk-headless -qq > /dev/null
! wget -q https://www-us.apache.org/dist/spark/spark-2.4.4/spark-2.4.4-bin-hadoop2.7.tgz
! tar xf spark-2.4.4-bin-hadoop2.7.tgz
! pip install -q findspark
import os
os.environ["JAVA_HOME"] = "/usr/lib/jvm/java-8-openjdk-amd64"
os.environ["SPARK_HOME"] = "/content/spark-2.4.4-bin-hadoop2.7"
```


### 2. Carrier Counts

In this part I will **create a notebook** and implement map reduce algorithm and find the carrier counts. 

Following is a sample initation code for `SparkSession`. I will use similar code to count number of carriers.

``` py
from pyspark.sql import SparkSession

spark = SparkSession.builder \
    .master("local[*]") \
    .appName("Counting_Carriers") \
    .getOrCreate()
```

