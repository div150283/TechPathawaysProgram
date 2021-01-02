<b>Part 1.</b> Implement data lake on GCP Cloud Datastore, Cloud Dataproc and BigQuery. 
 
 Created cluster using the below command to connect dataproc with Spark and BigQuery:
 
CLUSTER_NAME="clusterspark" 
gcloud beta dataproc clusters create ${CLUSTER_NAME} \
  --region us-central1 \
  --zone us-central1-a \
  --master-machine-type n1-standard-1 \
  --master-boot-disk-size 500 \
  --num-workers 2 \
  --worker-machine-type n1-standard-1 \
  --worker-boot-disk-size 500 \
  --image-version 1.3-debian10 \
  --project warm-skill-297413 \
  --optional-components=ANACONDA,JUPYTER \
  --enable-component-gateway \
  --metadata 'PIP_PACKAGES=google-cloud-bigquery google-cloud-storage' \
  --metadata gcs-connector-url=gs://path/to/custom/gcs/connector.jar \
  --metadata bigquery-connector-url=gs://path/to/custom/hadoop/bigquery/connector.jar \
  --metadata spark-bigquery-connector-url=gs://path/to/custom/spark/bigquery/connector.jar \
  --initialization-actions gs://goog-dataproc-initialization-actions-${REGION}/python/pip-install.sh \
  --properties "spark:spark.jars=gs://spark-lib/bigquery/spark-bigquery-latest.jar" 

![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week4Assignment/Images/CreatingClusterSparkBigquery.png)


<b>Part 2.</b> Try ELT processes (created python scripts and submit them as jobs in dataproc) with all three types of storage learned in week 

<b>Part 3.<b> Try with structured data (csv, parquet,orc), unstructured data (text excerpts from article, images), semi-structured data (json, xml). Use pyspark for loading and querying. 
  
Part 4. Write a python script to read a csv file and write it back to cloud storage in parquet format using pyspark

<b>Part 4: </b>
Read the CSV file from Google Cloud and converted to Parquet file
![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week4Assignment/Images/ConvertCsv2Parque.png)
![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week4Assignment/Images/buckcetFolderCreated.png)
![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week4Assignment/Images/bucketParquetFileCreated.png)
