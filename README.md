# Serving Success: An EDA of First Serve Impact on Tennis Match Outcomes
## Authors
* [Yoav Weller](https://github.com/YoavWeller)
## Table of Contents
* [Business Problem](https://github.com/YoavWeller/Tennis_Analysis#business-problem)
* [Data Source](https://github.com/YoavWeller/Tennis_Analysis#data-source)
* [Methods](https://github.com/YoavWeller/Tennis_Analysis#methods)
* [Tech Stack](https://github.com/YoavWeller/Tennis_Analysis#tech-stack)
* [Lessons Learned and Recommendation](https://github.com/YoavWeller/Tennis_Analysis#lessons-learned-and-recommendation)
* [Limitations and What Could Be Improved](https://github.com/YoavWeller/Tennis_Analysis#limitations-and-what-could-be-improved)
* [Repository Structure](https://github.com/YoavWeller/Tennis_Analysis#repository-structure)
* [Run Locally](https://github.com/YoavWeller/Tennis_Analysis#run-locally)

## Business Problem
Tennis, a globally renowned sport, is a perfect blend of athleticism, strategy, and skill. Spanning from community courts to grand slam arenas, the game attracts millions of enthusiasts worldwide, both as participants and spectators. While the sport's beauty lies in its intricacies, one element stands out as a critical determinant of a player's success: the serve.

Serving in tennis is equivalent to a pitcher's throw in baseball or a quarterback's pass in football. It sets the tone for the entire point, giving the server an initial advantage. Within this domain, the first serve is particularly crucial. A powerful and accurate first serve can drastically diminish the opponent's chances of returning the ball effectively, thereby providing the server with a strategic upper hand.

However, it's not just about getting the ball into play. The quality of the first serve, measured by both its accuracy (percentage of successful first serves) and its effectiveness (percentage of points won on a successful first serve), can be game-changing. A higher first-serve percentage indicates consistent performance, while a higher winning percentage on the first-serve points reflects the serve's potency.

This study seeks to delve deeper into these metrics to uncover patterns and insights. Specifically, I aim to answer:

1. Is there a difference between winners' and losers' first-serve percentages?
2. Does a difference exist between winners' and losers' percentages of winning first-serve points?

By analyzing these questions, I hope to shed light on the pivotal role the first serve plays in a tennis match's outcome and potentially provide players and coaches with valuable insights to refine their strategies.

## Data Source
The data is taken from Kaggle and is called ['Huge Tennis Database'](https://www.kaggle.com/datasets/guillemservera/tennis). This dataset is a comprehensive collection of ATP tennis rankings, match results, and player statistics. It is derived from the original database created and maintained by Jeff Sackmann, which can be found in the [following GitHub repository](https://github.com/JeffSackmann/tennis_atp).

There were two methods for importing this data - by using SQLite or by using CSV files. I chose to download the CSV files regarding all the ATP matches conducted between 1968 and 2023. Because the data of each year's matches is stored in a separate CSV file, I had to concatenate them into a variable called `combined_df`.

## Methods

## Tech Stack

## Lessons Learned and Recommendation

## Limitations and What Could Be Improved

## Repository Structure

## Run Locally
