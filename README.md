# ml-fifa
This project was started in January 2018. Our goal is to create a "football oracle" which can predict game outcomes of the FIFA World Cup 2018.

## Collecting data
We collected various tournament data from transfermarkt using python frameworks such as scrapy. The scraper source code can be found [here](https://github.com/ViviLearns2Code/ml-fifa). 
During the data collecting phase, we encountered challenges such as
* Data inconsistencies on the transfermarkt website: match lineups list wrong player data from time to time so that we cannot be certain of the quality of our collected data. Since transfermarkt was the most detailed website we have found for our purpose, we could not switch our data source and could only correct the inconsistencies manually to the best of our knowledge.
* Missing data: players from less known teams often do not have a publicly available market value estimate. We solved this by imputing these missing values with the minimum value within the player's team.

## Data exploration
The raw data which we collected for a single match is distributed over two files, one file contains the match result, the other contains the team's lineup statistics. We merge both files to one in which each row contains the following columns:
* sample_id (can be matchid + team name)
* avg. market value (MV) of defence teamA minus teamB 
* avg. market value (MV) of offence teamA minus teamB
* number of different clubs teamA minus teamB 
* avg. age teamA minus teamB
* additional game information, such as results, round etc.

The target variable for our regression is the number of goals scored by one team. Depending on whether we decide to use multiple output regression, the number of goals conceded can be included as an additional target variable. For single output regression, we can use every match twice, once from the perspective of each team.

After this preprocessing step, we can start with data visualization to get a feel for our data.

In progress

## Modeling
To be done

## Evaluation
To be done