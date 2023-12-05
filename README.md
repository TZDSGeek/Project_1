# Project_1

Our group chose to analyze 20 seasons of NBA games data to determine the relationship between performance (as measured by per game averages) and consistency (as measured by standard deviations of game-level stats).

Our original research question was "Who is the most consistent top performer in the NBA from 2003 to 2022?". As we dug into the available data and better understood our chosen measures of "performance" and "consistency" we modified our research focus to narrow in on individual statistical categories where we found some differences in the relationship between consistency and performance across categories.

# High-level approach:

# Description of the datasets:
We started with datasets covering the 2003 to 2022 seasons, including the following:
games = "Resources/games.csv" --> Date, teams playing, and team-level statistics for games played.
games_details = "Resources/games_details.csv" --> Player level statical data for all games played.
players = "Resources/players.csv" --> Player ID, name, team, and season metadata
ranking = "Resources/ranking.csv" --> The ranking of each team within each conference based on win-loss record at multiple dates over the course of the season.
teams = "Resources/teams.csv" --> Metadata information about each team, including ownership, home city, etc.

# Cleaning and analysis
After understanding the datasets, experimenting with some merges and cleaning, we focused on creating a dataframe from the games_details dataset to use for our analysis. We determined that, in order to exclude players not participating in a number of games large enough from which to calculate a meaningful standard deviation, we would limit our analysis to players participating in at least 82 games (the equivalent of a full NBA season) over the full dataset. 

This filtering exercise likely excludes many players whose careers were winding down or just starting in 2004 or 2022, respectively. For example, this examindation of top performers excludes Hall of Famer Reggie Miller who played in only 66 games during the 2004-2005 season before retiring.

# Analysis
Each member of the team focused on a different set of statistical categories as follows: 
* Points -- James
* Assists -- Daniel
* Rebounds -- Tyson
* Blocks -- Jesse
* Steals -- Jesse
* Plus / Minus -- Daniel

For each of the six statistical categories, we did the following: 
- 
1. Calculated the per game average of each player using 'groupby' on the Player_Id column
2. Sorted the dataset from best to worst per game average for the given statistic
3. Identified the Top 50 performers based on per game average and designated them our "Top Performer" dataset
4. Compared the standard deviation of the Top Performer dataset to the standard deviation of the league as a whole for the given statistical category, using t-tests, data visualizations, and linear regression.
5. Drew conclusions about the relationship between performance and consistency based on the results

# Analysis
Across all categories, we found...
