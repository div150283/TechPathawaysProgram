A short write-up on  data quality issues that you have encountered in real world data and how they fit onto the data quality dimensions.
  
  In real world wherever we collect the data manually we get data issues. It could be anything like duplicate data, missing data, spelling mistakes, wrong format data, late recording of data, calculation errors etc.
  This type of issues of data quantity or quality can happen anywhere like shops, offices, banks etc.
  From quality perspective we may have multiple dimensions of data and automation helps us with dealing with those issues in real world.
  Let's see multiple dimensions of data with and without automation in bus reservation system: 
  
  1.Accuracy: How well does a piece of information reflect reality?   
   This dimension means data is accurate and not misleading. If we produce the ticket manually we may wrongly type Travel date info/name of person(s) traveling/start station or end station in real world which may be inaccurate. But if we book this ticket through computerized system  like RedBus we dont have these accuracy problems as they will always produce the ticket with accurate details for each passenger.
  
  2.Timeliness : Is your information available when you need it?  
  This dimension means the data is up to date or recent. Manual ticket generation process will need booking of tickets in person or  over phone and if tickets are generated over multiple centres it takes time to produce a report how many seats booked in same bus.But with booking software we can see which seats are booked/vacant live while booking.Ticket generation and report generation is very fast.
  
  3.Uniqueness :Is this the only instance in which this information appears in the database?  
   Multiple shops/booking centers may book same seat while booking manually leading to duplicate records.Same seat may be allocated to multiple people/booked multiple times. This is avoided into the booking software like RedBus.
  
  4.Validity : Is information in a specific format, does it follow business rules, or is it in an unusable format?  
   Manual booking may have different ways of recording like data of birth, travel date may be entered in multiple formats by people making it hard to process whereas a software will ensure we have same format of data for each booking.
  
  5.Consistency : Does information stored in one place match relevant data stored elsewhere?  
   After booking completes, everyone get to see the same number of available seats/waiting list across the RedBus system whereas if it's booked manually without software person may be wrongly calculating the available seats.
  
  6.Completeness : Does it fulfill your expectations of what’s comprehensive?  
   Data should be complete for every booking and all mandatory fields should be captured in the data.While issuing manual ticket, we may forgot to mention destination/date of travel or some other mandatory fields.Whereas in software these fields can be made mandatory so that all required information is captured.

Dataprep is very good tool for data cleaning and tranformations. I used my movielens dataset and then imported my dataset from google cloud storage in the dataprep flow and then created recipe on the data.The recipe logic is as follows:
Created a recipe for movie duration greater than 60 minutes and then ordered the results by country and then removed duplicate values from the data and also removed missing values and null values from two columns usa_gross_income and worldwide_gross_income.The screenhsots are attached as follows:

1.Created a new bucket in cloud storage bucket and uploaded movie_lens csv file in the bucket:
![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week6Assignment/Images/dataprep_moviebucket.png)
2.Imported the data from bucket into google cloud dataprep by import button
![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week6Assignment/Images/importeddataset.png)
3.Created a flow in dataprep and then applied recipe on it with transformations.The screenshots are as follows:
![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week6Assignment/Images/Movie_flow.png)

![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week6Assignment/Images/runjobondataprep.png)

![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week6Assignment/Images/job_transformation.png)
![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week6Assignment/Images/job_transformation.png)
![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week6Assignment/Images/transformeddatamovie.png)
![](https://github.com/div150283/TechPathawaysProgramModule1/blob/main/Week6Assignment/Images/transformeddatamovie.png)
