# Microsoft Movie Maximisation

**Author**: Shane Dowling

## Overview

Microsoft sees all the big companies creating original video content and they want to get in on the fun. They have decided to create a new movie studio, but they don’t know anything about creating movies. This project will explore what types of films are currently doing the best at the box office. This project will then translate those findings into actionable insights that the head of Microsoft's new movie studio can use to help decide what type of films to create.

## Business Problem

This project will explore the movie market and offer recommendations for next steps in the expansion of Microsoft operations into the creation of new and exciting video content.

The problem being, that Microsoft admittedly do not know anything about creating movies.

Given that Microsoft is currently the most valuable public traded company in the world.  
The main goal in this exercise is to make movies that are profitable.

So, the main aim of this project will be to determine factors that affect profitability.

Once we have a measure for success,  
I will continue my analysis to examine three main categories that may affect profit.

* Genre
* Principal Contributors
* Release timing


***

## Data

This project draws on multiple datasets from a variety of sources.

### Box Office Mojo
* ### bom.movie_gross.csv.gz 
includes data for both Domestic and Foreign Gross profits.

### The Numbers
* ### tn.movie_budgets.csv.gz
includes data for Domestic and "Worldwide" profits.

The above two datasets is where i will extract profit data from.

### IMDB
I have also used numerous datasets from the IMDB database.  
These provide additional information which can then be compared as factors affecting profitability.

* ### imdb.title.basics.csv.gz
* ### imdb.title.principals.csv.gz

I have given a complete breakdown of the raw data   
including some of the methods i had to employ to access this data  
in the following Jupyter notebook:  
* Complete Dataset summary.ipynb

### Other useful data
In addition to the above datasets,  
I also needed to draw on additional data,   
in order to solve problems that arose,
I realised early on that i would need to calculate and adjust profit figures for inflation.
the additional data required to make these calculations was sourced from the following website:  
https://www.in2013dollars.com/  
***

## Methods

The process of analysing data for this project began with Merging the two datasets that contained information about profits.
I decided to focus on worldwide gross profits.
#### Merging data
Once data from the BOM and The Numbers datasets was cleaned. i needed to create a worldwide column in the BOM data.  this was calculated by adding the domestic + foreign gross figures.
This gave me a dataset with 6179 records all with Worldwide gross figures.
#### Adjusting for inflation
I then realised that the data spanned over 100 years, so to be able to meaningfully compare the figures across the years it was necessary to create an inflation modifier.
by the end of this process my data was all comparable to 2024 real US$ terms.
#### importing IMDB data
the IMDB data included a title reference, which made it easy to merge and compare various factors included in the data.  
by merging this data, i was able to compare genre and principal contributor roles, by merging this data in to my larger dataset.
the release date timing data was all included in the original merged dataset.
by the end of this process i had three main datasets that were useful.
#### id_wwgross_infl_genre
which included Movie tiltles, the gross profit adjusted for inflation, and genre information
#### id_wwgross_infl_principals  
which included titles of movies, the gross profit adjusted for inflation, and the roles of principal members of the production team.
#### r_date_wwgross_infl
which included the title of the movie, the gross profit adjusted for inflation, and the month of release.


## Results

Once cleaned and prepared, the modelling process for the data was then relatively simple.
I created graphs for each of the datasets, based on groupby functions on the relevant categories.
theses graphs made the recommendations fairly clear.
i learned how to customise bars on bar plots to highlight the results further.



## Conclusions

In conclusion,  As Microsoft prepares to branch out into Movie Production, I can offer the following recommendations.

1. To begin with focus on the Musical Genre.  
Traditionally, Musicals have been the highest grossing movies.  

2. Secondly, start with a great script.  
Writers have the highest influence overall on movie profitability. Good directors and Actors are also important, but start with a good writer.

3. Finally, aim for a release date in May.  
Movies released in May tend to have greater success than movies released in other months.    
June, December, November or July are also good,  
but avoid January or September.





## Repository Structure

Describe the structure of your repository and its contents, for example:

```
├── README.md                           <- The top-level README for reviewers of this project
├── dsc-phase1-project-template.ipynb   <- Narrative documentation of analysis in Jupyter notebook
├── DS_Project_Presentation.pdf         <- PDF version of project presentation
├── data                                <- Both sourced externally and generated from code
└── images                              <- Both sourced externally and generated from code
```
