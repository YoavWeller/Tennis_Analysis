# Serving Success: An EDA of First Serve Impact on Tennis Match Outcomes
## Authors
* [Yoav Weller](https://github.com/YoavWeller)
## Table of Contents
* [Introduction](https://github.com/YoavWeller/Tennis_Analysis#introduction)
* [Business Problem](https://github.com/YoavWeller/Tennis_Analysis#business-problem)
* [Data Source](https://github.com/YoavWeller/Tennis_Analysis#data-source)
* [Methodology](https://github.com/YoavWeller/Tennis_Analysis#methodology)
* [Requirements/Installation](https://github.com/YoavWeller/Tennis_Analysis#requirementsinstallation)
* [Results and Recommendation](https://github.com/YoavWeller/Tennis_Analysis#results-and-recommendation)
* [Limitations and What Could Be Improved](https://github.com/YoavWeller/Tennis_Analysis#limitations-and-what-could-be-improved)
* [Repository Structure](https://github.com/YoavWeller/Tennis_Analysis#repository-structure)

## Introduction
Tennis, a globally renowned sport, is a perfect blend of athleticism, strategy, and skill. Spanning from community courts to grand slam arenas, the game attracts millions of enthusiasts worldwide, both as participants and spectators. While the sport's beauty lies in its intricacies, one element stands out as a critical determinant of a player's success: the serve.

Serving in tennis is equivalent to a pitcher's throw in baseball or a quarterback's pass in football. It sets the tone for the entire point, giving the server an initial advantage. Within this domain, the first serve is particularly crucial. A powerful and accurate first serve can drastically diminish the opponent's chances of returning the ball effectively, thereby providing the server with a strategic upper hand.

However, it's not just about getting the ball into play. The quality of the first serve, measured by both its accuracy (percentage of successful first serves) and its effectiveness (percentage of points won on a successful first serve), can be game-changing. A higher first-serve percentage indicates consistent performance, while a higher winning percentage on the first-serve points reflects the serve's potency.

## Business Problem
This study seeks to delve deeper into these metrics to uncover patterns and insights. Specifically, I aim to answer:

1. Is there a difference between winners' and losers' first-serve percentages?
2. Does a difference exist between winners' and losers' percentages of winning first-serve points?

By analyzing these questions, I hope to shed light on the pivotal role the first serve plays in a tennis match's outcome and potentially provide players and coaches with valuable insights to refine their strategies.

## Data Source
The data is taken from Kaggle and is called ['Huge Tennis Database'](https://www.kaggle.com/datasets/guillemservera/tennis). This dataset is a comprehensive collection of ATP tennis rankings, match results, and player statistics. It is derived from the original database created and maintained by Jeff Sackmann, which can be found in the [following GitHub repository](https://github.com/JeffSackmann/tennis_atp).

There were two methods for importing this data - by using SQLite or by using CSV files. I chose to download the CSV files regarding all the ATP matches conducted between 1968 and 2023. Because the data of each year's matches is stored in a separate CSV file, I had to concatenate them into a variable called `combined_df`.

## Methodology
1. Data Cleaning & Preprocessing:
   * Removed all matches that didn't have data about the match stats.
   * Removed unnecessary columns.
   * Created derived variables, such as 'Winning Percentage on First Serve', by combining relevant data columns.
   * Converted the data type of certain columns from float64 to int8/int16 in order to reduce memory usage.
   * Created several subsets of the original dataset in order to make the visual analysis easier to execute.
2. Univariate Analysis (provided a preliminary understanding of the general trends within the data):
   * Calculated the frequencies for key categorical variables like the surface type or the number of matches played in each tournament type.
   * Calculated mean, median, and standard deviation for key numerical variables like 'First Serve Percentage' and 'Winning First Serve Points Percentage'.
   * Plotted the frequencies of the categorical variables using bar plots and the distributions of numerical variables using histograms.
3. Bivariate Analysis:
   * Used visual methods such as scatter plots and statistical methods such as correlations to identify potential correlations between various variables.

## Requirements/Installation
1. Tools:
   * Anaconda/Google Colab - I wrote the analysis code using Jupyter Notebook. In order to open it, you should use Anaconda/Google Colab (or any other tool that can open Jupyter Notebook).
   * Microsoft PowerPoint - If you desire to open my report in PowerPoint format.
   * PDF reader - If you desire to open my report in PDF format.
2. Python Libraries:
   * General Purpose: `os`
   * Data Manipulation: `numpy`, `pandas`
   * Data Visualization: `matplotlib`, `seaborn`
   * scientific computing: `scipy`

## Results and Recommendation
### Results

Besides the textual explanation of the results and the corresponding plot for each result, I made an [interactive dashboard](https://public.tableau.com/views/TennisDashboard_16979727707560/not_segregated_dashboard?:language=en-GB&:display_count=n&:origin=viz_share_link) using Tableau Public. In my opinion, it's easier to understand the plots and results in the dashboard.

1. **First-Serve Accuracy (Percentage Of Successful First Serves) - Difference Between Winners' And Losers'**: 
Winners exhibit a slightly higher median percentage of successful first serves (60.98%) compared to losers (59.13%). While this difference may or may not be statistically significant [^1], it appears to be relatively small. This suggests that a minor advantage in accuracy on the first serve may not be the sole determinant of match outcomes.

![First-Serve Accuracy Plot](https://github.com/YoavWeller/Tennis_Analysis/blob/main/Plots%20Images/first_serve_accuracy.png)

* **First-Serve Accuracy By Surface Type - Difference Between Winners' And Losers'**:
  * On carpet and grass surfaces, winners demonstrate notably higher first-serve accuracy compared to losers, indicating their ability to consistently place their serves within the desired areas. 
  * For clay and hard surfaces, while there is still a difference in accuracy between winners and losers, it is less pronounced, suggesting that other factors may come into play on these surfaces.
<div align="center">

| Surface Type | Winners' Median Accuracy | Losers' Median Accuracy |
| ------------ | --------------- | -------------- |
| Carpet | 58.97% | 57.29% |
| Clay | 61.74% | 60.00% |
| Grass | 62.14% | 60.32% |
| Hard | 60.46% | 58.65% |

</div>

![First-Serve Accuracy By Surface Type Plot](https://github.com/YoavWeller/Tennis_Analysis/blob/main/Plots%20Images/First%20Serve%20In%20Percentage%20By%20Surface.png)

* **First-Serve Accuracy By Tourney Type - Difference Between Winners' And Losers'**:
  * Across all tournament levels, winners generally maintain higher first-serve accuracy than losers, with the Grand Slam tournaments showing the most significant difference.

<div align="center">

| Tourney Type | Winners' Median Accuracy | Losers' Median Accuracy |
| ------------ | --------------- | -------------- |
| Another | 60.74% | 59.04% |
| Grand Slam | 61.98% | 60.00% |
| Masters 1000 | 60.66% | 58.46% |

</div>

![First-Serve Accuracy By Tourney Type Plot](https://github.com/YoavWeller/Tennis_Analysis/blob/main/Plots%20Images/First%20Serve%20In%20Percentage%20By%20Tourney%20Level.png)

2. **First-Serve Effectiveness (Percentage Of Points Won On A Successful First Serve) - Difference Between Winners' And Losers'**:
A more significant disparity emerges when we examine the percentage of points won on a successful first serve. Winners have a median of 76.47%, whereas losers have a median of 66.00%. This substantial difference implies that winners are more adept at leveraging their first serves to secure points [^1]. It suggests that the effectiveness of the first serve plays a crucial role in determining match results.

![First-Serve Effectiveness Plot](https://github.com/YoavWeller/Tennis_Analysis/blob/main/Plots%20Images/first_serve_effectiveness.png)

* **First-Serve Effectiveness By Surface Type - Difference Between Winners' And Losers'**:
  * When it comes to first-serve effectiveness, the differences are generally smaller across all surface types, indicating that the ability to win points on successful first serves is influenced by multiple factors, including opponent skill and court conditions.
<div align="center">

| Surface Type | Winners' Median Accuracy | Losers' Median Accuracy |
| ------------ | --------------- | -------------- |
| Carpet | 79.17% | 69.23% |
| Clay | 73.33% | 62.86% |
| Grass | 79.31% | 69.44% |
| Hard | 77.42% | 67.06% |

</div>

![First-Serve Effectiveness By Surface Type Plot](https://github.com/YoavWeller/Tennis_Analysis/blob/main/Plots%20Images/First%20Serve%20Winning%20Percentage%20By%20Surface.png)

* **First-Serve Effectiveness By Tourney Type - Difference Between Winners' And Losers'**:
  * First-serve effectiveness, however, exhibits a more substantial gap between winners and losers, emphasizing the critical role of effectively winning points on successful first serves.

<div align="center">

| Tourney Type | Winners' Median Accuracy | Losers' Median Accuracy |
| ------------ | --------------- | -------------- |
| Another | 76.32% | 65.85% |
| Grand Slam | 77.00% | 66.67% |
| Masters 1000 | 76.19% | 65.96% |

</div>

![First-Serve Effectiveness By Surface Type Plot](https://github.com/YoavWeller/Tennis_Analysis/blob/main/Plots%20Images/First%20Serve%20Winning%20Percentage%20By%20Tourney%20Level.png)

### Recommendation
These findings emphasize that while accuracy on the first serve is important, it is the ability to capitalize on it that sets winners apart from losers. Effectiveness in winning points on the first serve appears to be a more influential factor in achieving victory in tennis matches. Therefore, I believe several useful insights could be implied while training:
1. Focus on First Serve Effectiveness: Emphasize the importance of not just hitting successful first serves but also winning points when they are in play. Players and coaches should work on strategies and techniques to ensure that their first serves are not just accurate but also challenging for opponents to return.
2. Training for Point-Winning on First Serve: Training programs should incorporate specific drills and exercises that aim to improve the ability to win points on successful first serves. This may include working on placement, speed, spin, and placement to make the first serve more potent.
3. Balancing Accuracy and Effectiveness: While the ability to capitalize on the first serve is crucial, it's essential not to overlook the importance of first serve accuracy. Players should strike a balance between precision and power in their serves. A highly accurate first serve can set the stage for effective point-winning. Therefore, strive for both accuracy and effectiveness to create a well-rounded first-serve strategy.

[^1]: I haven't performed significance tests or calculated effect size on either of the results yet. See the [Limitations and What Could Be Improved](https://github.com/YoavWeller/Tennis_Analysis#limitations-and-what-could-be-improved) section for further explanation.

## Limitations and What Could Be Improved
1. Missing Data - while examining the missing data in my dataset, I noticed that most of the matches that didn't have stats were played in a Davis Cup event. Besides removing all the rows with the missing data, I decided to remove all the matches played in a Davis Cup event. I'm not sure this was the right thing to do, and in the future, I'm planning to make a thorough investigation in order to understand why so many matches without stats were played in the Davis Cup.
2. Not conducting statistical significance tests - as mentioned in the results section, I didn't do statistical significance tests - because of my insufficient knowledge. I'm currently retaking a statistical inference course, and after finishing it I will add the statistical significance tests.

## Repository Structure
```console
|   README.md
|   tennis_analysis.ipynb
|   matches_data_dictionary.txt
|   combined_and_cleaned_df.csv
|   wins_on_first_serve_melted_df.csv
|   first_serve_in_melted_df.csv
|   Tennis Dashboard.twbx
|   directory_tree.txt
|   
---full_matches_data
|       atp_matches_1997.csv
|       atp_matches_1998.csv
|       atp_matches_1999.csv
|       atp_matches_2000.csv
|       atp_matches_2001.csv
|       atp_matches_2002.csv
|       atp_matches_2003.csv
|       atp_matches_2004.csv
|       atp_matches_2005.csv
|       atp_matches_2006.csv
|       atp_matches_2007.csv
|       atp_matches_2008.csv
|       atp_matches_2009.csv
|       atp_matches_2010.csv
|       atp_matches_2011.csv
|       atp_matches_2012.csv
|       atp_matches_2013.csv
|       atp_matches_2014.csv
|       atp_matches_2015.csv
|       atp_matches_2016.csv
|       atp_matches_2017.csv
|       atp_matches_2018.csv
|       atp_matches_2019.csv
|       atp_matches_2020.csv
|       atp_matches_2021.csv
|       atp_matches_2022.csv
|       atp_matches_2023.csv
|       atp_matches_1991.csv
|       atp_matches_1992.csv
|       atp_matches_1993.csv
|       atp_matches_1994.csv
|       atp_matches_1995.csv
|       atp_matches_1996.csv
|       
---Archive (unused files)
|       atp_tennis.csv
|       tennis_players_data_scarping.ipynb
|       atp_players.csv
|       
---Plots Images
|       First Serve In Percentage By Surface.png
|       First Serve Winning Percentage By Surface.png
|       First Serve In Percentage By Tourney Level.png
|       First Serve Winning Percentage By Tourney Level.png
|       first_serve_accuracy.png
|       first_serve_effectiveness.png   
```
