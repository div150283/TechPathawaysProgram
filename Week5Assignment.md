1. Use a public dataset from GCP (https://console.cloud.google.com/marketplace/browse?filter=solution-type:dataset&pli=1). Try using Newyork City Taxi data set.

The python script to create a datastore from green taxi dataset csv file taken from the above link is as follows:
First I have read the csv file from google cloud shell line by line and then uploaded the csv data into the datastore through Kinds and Entities.
![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week%205%20Assignment/Images/csvdatastore.png)

![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week%205%20Assignment/Images/loadingdataindatastore.png)

Data Fetched from datastore using python script is as follows:
![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week%205%20Assignment/Images/fetchingdata.png)

2. Create a python script which will run as a job in the data pipeline. The python script will read data from the nosql db and clean the data - remove null values from all columns, remove duplicate entries. The cleaned data is then written into parquet or orc file (alternatively can write to a json file).

![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week%205%20Assignment/Images/removingNullandDuplicates_createParquet.png)

3. Write another python script to read from the parquet or orc file and create a descriptive summary. Compute sum of a numeric column (for instance salary). You can take it a step further by grouping it on a specific column (eg: Title) and find the highest salaried Title.

First I created a dataproc cluster with below configuration :
CLUSTER_NAME="clusterspark" 
gcloud beta dataproc clusters create ${CLUSTER_NAME} \
--region us-central1 \
--zone us-central1-a  \
--master-machine-type n1-standard-1 \
--master-boot-disk-size 500 \
--num-workers 2  \
--worker-machine-type n1-standard-1  \
--worker-boot-disk-size 500  \
--image-version 1.3-debian10  \
--project the-webbing-300813 \
--optional-components=ANACONDA,JUPYTER  \
--enable-component-gateway \
--metadata 'PIP_PACKAGES=google-cloud-bigquery google-cloud-storage'  \
--metadata gcs-connector-url=gs://path/to/custom/gcs/connector.jar  \
--metadata bigquery-connector-url=gs://path/to/custom/hadoop/bigquery/connector.jar  \
--metadata spark-bigquery-connector-url=gs://path/to/custom/spark/bigquery/connector.jar  \
--initialization-actions gs://goog-dataproc-initialization-actions-us-central1/python/pip-install.sh \
--properties "spark:spark.jars=gs://spark-lib/bigquery/spark-bigquery-latest.jar"

![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week%205%20Assignment/Images/creatingdataproccluster.png)
The parquet file is copied from google cloud shell to google cloud storage bucket as mentioned in the screenshot:

![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week%205%20Assignment/Images/greentaxiparquet.png)

The python code for reading a parquet file and then generating the descriptive summary of the dataframe:

import pyspark
import sys
from pyspark.sql import SparkSession
spark = SparkSession.builder \
.appName("Green Taxi Data") \
.getOrCreate()
greentaxi_df = spark.read.parquet("gs://nycgreentaxibucket/greentaxi.parquet")
#Descriptive summary
greentaxi_df.describe().show()

Output is as mentioned:
![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week%205%20Assignment/Images/outputDescriptiveSummary.png)

The code for descriptive summary and tranformations on a spark dataframe
import pyspark
import sys

from pyspark.sql import SparkSession
spark = SparkSession.builder \
.appName("Green Taxi Data") \
.getOrCreate()
greentaxi_df = spark.read.parquet("gs://nycgreentaxibucket/greentaxi.parquet")
#Descriptive summary
#greentaxi_df.describe().show()
#greentaxi_df.agg({'Passenger_count': 'sum'}).show()
print(greentaxi_df.count())

#Number of trips grouped by vendor id and passenger count
greentaxi_df.groupBy('VendorID','Passenger_count').count().orderBy(greentaxi_df.VendorID.asc()).show()

4. Integrate the above jobs into a data pipeline, the job flow is important so step 2 should precede step 3 in the data pipeline https://cloud.google.com/solutions/building-production-ready-data-pipelines-using-dataflow-overview
