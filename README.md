# code
Data analytics using SQL
This a portfolio project that i did so i can keep track of my progress.
In this project i will do some basic analysis using mySQL and a dataset related to covid deatha and vaccination.

After uploading the datasets, lets start with:
  Discovering our datasets
  
  USE portfolio; #this is the name of the created folder in mySQL
SELECT 
    *
FROM
    `covid-death`;
    
    
now we get a clear idea about how our dataset lookslike



After investigating our dataset, lets find out which country had the most new cases in one day.

USE portfolio;
SELECT 
	location,population,new_cases
FROM
    `covid-death`
WHERE new_cases=(SELECT max(new_cases) FROM `covid-death`);

the result was like: 
# location, population, date, new_cases
'Turkey', '84339067', '10/12/2020', '823225'

