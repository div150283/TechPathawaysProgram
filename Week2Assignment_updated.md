1. Setup Cloud BigQuery: Bigquery setup done from this link

[](https://cloud.google.com/bigquery/docs/quickstarts/quickstart-web-ui)

2. Imported data from movie.csv, occupation.csv,users.csv,ratings.csv,movie_genere.csv stored in storage bucket and then queried the data.

https://github.com/div150283/TechPathawaysProgramModule1/blob/main/2_1.png

https://github.com/div150283/TechPathawaysProgramModule1/blob/main/2_2.png

3. New denormalized table created for Bigquery so that we don't need to query data other table and just one table is sufficient  

   **create table movielens.denormalised_movielens_table**
   **as**
   **(select** 
   **movie.movie_id,movie.movie_title,movie.movie_year,**
   **movie_genere.movie_genere,**
   **users.user_id,users.gender,users.age,users.zipcode,**
   **ratings.rating, TIMESTAMP_SECONDS(ratings.time_stamp) time_stamp,**
   **occupation.occupation_name**
   **from movielens.movie,movielens.movie_genere,movielens.users,movielens.ratings,movielens.occupation**
   **where** 
   **movie.movie_id=movie_genere.movie_id and**
   **ratings.movie_id=movie.movie_id and** 
   **users.user_id=ratings.user_id and**
   **occupation.occupation_id=users.occupation)**
   
   https://github.com/div150283/TechPathawaysProgramModule1/blob/main/3_1.png

   Link Referrred:  https://cloud.google.com/solutions/performing-etl-from-relational-database-into-bigquery#create_a_bigquery_dataset

4. Public dataset in Bigquery-Imported data from public dataset new_york_taxi_trips  and ran following query:

**How many trips did Yellow taxis take each month in 2015?**
This query returns monthly trip totals for all Yellow taxis in 2015[]()
https://github.com/div150283/TechPathawaysProgramModule1/blob/main/4_1.png
