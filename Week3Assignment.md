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
   
    
