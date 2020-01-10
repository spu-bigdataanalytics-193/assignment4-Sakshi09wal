# :hatched_chick: Introduction to Spark :penguin::pager:

Spark is the computing engine of big data. It's fast, fault tolerant, and resourceful with many libraries including machine learning, graphing, etc.

In this assignment, your mission, should you choose to accept it, is to rewrite your code for your previous assignment, using pyspark in the Spark environment. 

The dataset is the same, the flights information of each different airline carriers between 1987 to 2008. The goal is to count the `number of flights` that each carrier made, for all the flights in the dataset.

## Assignment Instructions

Calculate the number of flights for each carrier using Spark and pyspark library. Following is the set of things you will have to complete for this assignment.

1. Prepare Spark Tools
2. Complete carrier count example

### 1. Spark Tools

There are four ways of using spark. 

- Install it on your own system, either using [dockers](http://docker.com/) or on your host system directly.
- Using [Databricks](https://community.cloud.databricks.com/)
- Using [Google Colab](https://colab.research.google.com/)
- Using Saint Peter's University Data Science Lab Notebooks (Link will be provided later)

To make this part easy, you don't have to install it on your own computer. However, you will have to use all the other tools. 

Databricks will work on the fly, you just need to create and account. SPU data science lab is similar to Databricks, after you log in, you will be able to create notebooks. For Google Colab, you have to run the following script first, in order to be able to use spark.

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

Finally, in order to complete this part of assignment, you will have to share a screenshot of your running Carrier Counts code into **`spark-tool-screenshots`** folder. For each tool, share a single screenshot of your script in the folder. Thats it!

### 2. Carrier Counts

In this part of the assignment, you will **create a notebook** and implement map reduce algorithm and find the carrier counts, same as before. This time, you will use Spark. 

Following is a sample initation code for `SparkSession`. You will use similar code to count number of carriers.

``` py
from pyspark.sql import SparkSession

spark = SparkSession.builder \
    .master("local[*]") \
    .appName("Counting_Carriers") \
    .getOrCreate()
```

Your notebook should be committed to the github along with cell results. Not doing so will make you lose points.

## What are all these other files?

Following table is will give it a meaning for each file.

File                | Description 
-------             | ----------- 
README.md **        | A descriptive file to give an introduction of current project/ assignment. 
Instructions.md **  | A copy of current README.md file. 
LICENCE **          | The licence of the file that every project should have.
.gitignore          | The file to control which files should be ignored by Git.
.gitkeep            | An empty file to keep folders under git.
spark-tool-screenshots | Screenshots of tools you ran your notebook.
*.ipynb   | Assignment notebook with your Spark code for counting carriers. 