1. Use a public dataset from GCP (https://console.cloud.google.com/marketplace/browse?filter=solution-type:dataset&pli=1). Try using Newyork City Taxi data set.

The python script to create a datastore from green taxi dataset csv file taken from the above link is as follows:
First I have read the csv file from google cloud shell line by line and then uploaded the csv data into the datastore through Kinds and Entities.
![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week%205%20Assignment/Images/csvdatastore.png)

![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week%205%20Assignment/Images/loadingdataindatastore.png)

Data Fetched from datastore using python script is as follows:
![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week%205%20Assignment/Images/loadingdataindatastore.png)



2. Create a python script which will run as a job in the data pipeline. The python script will read data from the nosql db and clean the data - remove null values from all columns, remove duplicate entries. The cleaned data is then written into parquet or orc file (alternatively can write to a json file).
3. Write another python script to read from the parquet or orc file and create a descriptive summary. Compute sum of a numeric column (for instance salary). You can take it a step further by grouping it on a specific column (eg: Title) and find the highest salaried Title.
4. Integrate the above jobs into a data pipeline, the job flow is important so step 2 should precede step 3 in the data pipeline https://cloud.google.com/solutions/building-production-ready-data-pipelines-using-dataflow-overview
