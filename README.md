# Movies-ETL


## RegEx, ETL pipe-line, PGAdmin, PostgresSQL, Python, Pandas

1) Downloaded Wiki Json files of movies
2) Downloaded Kaggle metadata movie files
3) MovieLens Ratings files
4) cleaned enormous data files using RegEx sql and Python

filter out TV shows, change and clean all data files so that they
concur, analyse data sets to discover the most thorough and combine 
that set with data from the other sources
merge data sets and create data frames. 

The complete files are: 
### Module 8: 
<ul>
<li> part 1: ETL_function_test.ipynb </li>
<li> part 2: ETL_clean_wiki_movies.ipynb </li>
<li> part 3: ETL_clean_kaggle_data.ipynb </li>
<li> part 4: ETL_create_database.ipynb </li>


Final count of two data sets in Postgres: 

<img width="379" alt="movie_query" src="https://user-images.githubusercontent.com/14239715/121823678-d662bd80-cc74-11eb-8099-c473f194ffd7.png">


and 

<img width="346" alt="ratings_query" src="https://user-images.githubusercontent.com/14239715/121823848-cb5c5d00-cc75-11eb-8868-e06bca7cd7a7.png">


  
  
## The journey was tough. 
on part 2: The wiki_movie_df kept printing out as a list, not a df. I worked with many sources for hours after trying to troubleshoot for hours. Including with two amazing askBCS humans who ultimattely threw up thier hands after being super kind and thorough. I had already pulled apart each code block to test it but I learned a lot more about code dissection. After three hours, I was sent this message: 
  
  <img width="465" alt="Screen Shot 2021-06-13 at 6 05 28 PM" src="https://user-images.githubusercontent.com/14239715/121823242-065c9180-cc72-11eb-9941-af2f8e9daa7e.png">

BUT I kept going and got to the bottom of the problem**** Hurray, seriously was a 15 hour problem. This line of code was the issue. It was embedded deep in a large function: 

I had an extra line of partial code:release_date.str.extract(f'({date_form_one}|{date_form_two}|{date_form_three}|{date_form_four})')[0]

instead of:  

wiki_movies_df['release_date'] = pd.to_datetime(release_date.str.extract(f'({date_form_one}|{date_form_two}|{date_form_three}|{date_form_four})')[0], infer_datetime_format=True)

it was not re-parsing from the str.extract into a df.

on part 3 and 4 I stumbled a few times but made it through. 

I am deeply proud to finish this work. 
