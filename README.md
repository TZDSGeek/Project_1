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
Across all categories, we found the top NBA performers are less consistent than the rest of the league when analyzing the data using a one sample T-test. However, when looking at the difference between the top performers and the rest of the league using a linear regression model, the top performers are consistently below the expected standard deviation in each category: points, assists, rebounds, blocks, and steals. The plus/minus score was the only category where this did not hold true. So, if we were to extrapolate the lower performance level of the NBA league to the higher performance of the top players in each category, we would expect a higher level of inconsistency for the rest of the league. 
Another key take away is that depending on the statistical analysis used, bias can sway the results of a research question. Depending on which aspect of the data we looked at, we could argue that the top 50 performers are both more consistent and less consistent than the rest of the NBA league. 

# Points 

Top performers have a very different level of consistency game-to-game than the typical player – p-value of 3.21e-28 Top performers are far less consistent with their scoring game-to-game than players across the league Typical top performer std for points / game = 9.0 vs. 5.5 for the league as a whole However, the linear regression shows that the majority of top performers are more consistent than expected based on the league-wide performance (The r-value is: 0.81) Notable top performers include KD & LeBron, while TMac & James Harden are among the least consistent

# Rebounds

The top 5 most consistent top performers: Evan Mobley, Luka Doncic, Wendell Carter Jr., Al Horford, and Julius Randle. Is there a statistical significance between high performance and consistency. The Ttest Results were (statistic=23.16368326535982, pvalue=4.755563100474603e-28, df=49)
The pvalue suggests strong evidence against the null hypothesis.
r-value: 0.7906679736573208, indicates there is a very strong correlation between the two variables. The top performers tend to be more consistent when compared to the rest of the league.

# Analysis: +/-
The top 50 NBA players in +/- value per game have a higher standard deviation for +/- per game compared to the rest of the league. The average +/- standard deviation for the top 50 is 12.2, compared to 9.4 for the rest of the league. Additionally, when looking at a linear regression of the league as a whole, the top 50 NBA players are mostly above the line, indicating that they would still have a higher standard deviation if the rest of the league were performing at their level.
This means that the top 50 players have higher variability from game to game, despite overall performing much better than the rest of the league. The rest of the league is more consistently bad than the best are consistently good.
![alt text](https://github.com/TZDSGeek/Project_1/blob/main/Output/PlusMinus_Scatter_LinRegress.png?raw=true)

# Analysis: Assists
Compared to the rest of the league, the top 50 NBA players in the category of assists have a higher overall average assists per game. Likewise, they also have a larger average standard deviation compared to the rest of the league, with an average standard deviation of 3.2 assists compared to 1.5 assists for the rest of the league.
However, when looking at a linear regression for the league as a whole, the top 50 NBA players for assists actually fall below the line, indicating that if the rest of the league were putting up the strong numbers that the top 50 performer were, their spread (standard deviation) would be even higher.
Therefore, it appears that the top 50 NBA players are actually more consistent than the rest of the league in terms of assists per game
![alt text](https://github.com/TZDSGeek/Project_1/blob/main/Output/Assists_Scatter_LinRegress.png?raw=true)
# Blocks 
- The top 5 most consistent top performers were: Myles Turner, Marcus Camby, Anthony Davis, Rudy Gobert, and Alonzo Mourning
Significance between high performance and consistency?
T-statistic: 32.34117091161321
P-value: 2.650445452097839e-37
Reject the null hypothesis: There is a significant difference in standard deviation.
r-value: 0.8623664653984808, indicates a strong correlation with both variables.

# Steals 
Top 5 most consistent top performers were: Chris Paul, Jason Kidd, Ricky Rubio, Allen Iverson, and Baron Davis
Significance between high performance and consistency?
T-statistic: 42.973780114954124
P-value: 5.479311290129507e-51
Reject the null hypothesis: There is a significant difference in standard deviation.
r-value:  0.8594005618731932, does indeed indicate a strong correlation between both variables



