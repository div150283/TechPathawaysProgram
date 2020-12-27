<b>Assignment 1:</b>

Read a csv file from gcp cloud storage and view the contents using python

Here I have read the csv file using 2 methods:

1. Using For loop- I had read the file and printed the output using the For Loop 

![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week3Assignment/Images/readingcsv_forloop.png)

2.Using Pandas-This library is having read_csv function which reads all the data from csv into a dataframe.

![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week3Assignment/Images/readingcsv_panda.png)

Output Using Pandas

![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week3Assignment/Images/readingcsv_panda_output.png)

<b>References used for Assignment1:</b>

https://www.youtube.com/watch?v=ED5vHa3fE1Q&t=71s
https://cloud.google.com/appengine/docs/standard/python/googlecloudstorageclient/read-write-to-cloud-storage#specifying_the_cloud_storage_bucket

<b>Assignment 2:</b>
 
Uploaded the parquet file to cloud storage using upload files option in google cloud storage browser and read the file using the python code.
Parquet file output displayed in 3 different ways
    
<b>(a)</b> Output by printing the dataframe directly
  
![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week3Assignment/Images/parque_dataframePrint.png)
    
<b>(b)</b> Output by printing the dataframe using to_string() function 
![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week3Assignment/Images/parque_dataframePrint_ToString.png)
    
<b>(c)</b> Output by printing the dataframe using Location function in which I had specified labels: lineNoFrom and lineNoTo and just printed few lines I want to see.
![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week3Assignment/Images/parque_dataframe_byLineNumber.png)
   
<b>References used for Assignment2:</b>
 
 https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.read_parquet.html
 https://www.w3schools.com/python/pandas_dataframes.asp
 
<b>Assignment 3:</b>
 
Run ELT processes to load data from source into data lake. And run some queries on the data on databricks using spark.

The first part in this assignment is setting up a databricks cluster.The cluster type is Single Node as shown below
![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week3Assignment/Images/dataproc_setup.png)
![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week3Assignment/Images/dataproc_vminstances.png)
 
<b>1)</b> Get the data of Movies from Google Cloud storage. Loaded data into datalake and showing the data. As the file was not having the headers so added the header names dynamically.

![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week3Assignment/Images/dataproc_addHeaderToCsv.png)
<b>2)</b> Written a spark sql query to retrieve the count of total rows(total movies) in a dataframe.

![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week3Assignment/Images/dataproc_dataframe_countQuery.png)
<b>3)</b> Written a spark sql query to select moviename and movieyear from a dataframe(All records cannot come into image there are so many records)

![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week3Assignment/Images/dataproc_dataframe_selectQuery.png)
<b>4)</b> Written a spark sql query to get count of movies per year from the dataframe sorted by movie year

![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week3Assignment/Images/dataproc_dataframe_moviesPerYear.png)
<b>5)</b> Created a view from dataframe and then queried on the movielens view to show movies which were released in 1995

![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week3Assignment/Images/dataproc_dataframe_queryMovieLensView.png)

<b>Assignment 4:</b>

4) Bonus: Do some visualizations to show a simple analysis on the data.
I have created a dataframe and then created bar graph,line graph,pie chart from the selected data(Number of movies per year)
![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week3Assignment/Images/dataproc_dataframe_barGraph.png)

![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week3Assignment/Images/dataproc_dataframe_lineGraph.png)

![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week3Assignment/Images/dataproc_dataframe_PieChart.png)

References used for Assignment 3 and 4:
https://datascience-school.com/blog/practical-apache-spark-in-10-minutes-part-3-dataframes-and-sql/
https://www.datasciencemadesimple.com/get-number-of-rows-and-number-of-columns-of-dataframe-in-pyspark/
https://problemsolvingwithpython.com/06-Plotting-with-Matplotlib/06.06-Bar-Charts-and-Pie-Charts/
https://stackoverflow.com/questions/34091877/how-to-add-header-row-to-a-pandas-dataframe
https://sparkbyexamples.com/pyspark/convert-pyspark-dataframe-to-pandas/

