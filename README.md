# code
Data analytics using SQL
Is a portfolio project that i did so i can keep track of my progress.
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


Then, lets find out the total death in each country and their population.

SELECT 
	location,
    population,
    SUM(new_deaths) AS total_deaths
FROM
    `covid-death`
group by(location)
order by total_deaths DESC;

the results must be like:

# location, population, total_deaths
'Europe', '748680069', '1079651'
'South America', '430759772', '910865'
'North America', '592072204', '886143'
'European Union', '444919060', '728493'
'United States', '331002647', '597001'
'Brazil', '212559409', '470842'
'India', '1380004385', '344082'
'Mexico', '128932753', '228568'
'Peru', '32971846', '185813'
'Africa', '1340598113', '131794'
'United Kingdom', '67886004', '128086'
'Italy', '60461828', '126415'
'Russia', '145934460', '120974'
'France', '67564251', '110078'
'Colombia', '50882884', '90890'
'Germany', '83783945', '89152'
'Iran', '83992953', '80813'
'Argentina', '45195777', '80411'
'Spain', '46754783', '80195'
'Poland', '37846605', '74101'
'South Africa', '59308690', '56832'
'Ukraine', '43733759', '53117'




