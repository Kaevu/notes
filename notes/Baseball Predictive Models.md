Notes from the research paper "Assessing win strength in MLB win prediction models"
	- "relationship between predicted win probability and strength of win"
		- is paper asking if a 7-1 win more impactful than a blowout in predicting future wins

Problem is too small amounts of data or use only most common models or mess up entirely in methodology

Win probability percentage does determine strength of win

### Analysis of other papers

Jia et al (2013) using SVM and gradient boosting found the more recent statistics more impactful than lifetime stats

Soto Valero -> 58.92% using ANN, SVM, decision trees and KNN
	- Temporal dependence problem?
	- testing data overlaps with training data
Elfrink(2018) -> many models -> achieved 55.2%
	- maybe different models help predict in different distinct ways
Huang and Li (2021) -> SVM and neural nets -> achieved >= 90% accuracy with each model
	 - used only 2019 for training and testing using cross validation
		 - very likely overfit to the max

All the other models predicted outcomes of games
	- other predict via runs

### This Papers Methodology

Used 2001 to 2019 w/o playoffs -> 46,159 games in dataset
Used lots (84) of variables

The Good
	- Team OPS and OBP
	- AVG
	- SLG
	- ISO
	- WHIP
	- ELO + log5
The Meh
	- Pythagorean Expected Wins
	- Team Rank
The Awful
	- Avg Attendance (WHAT?)
	- Fielding PCT%
	- Starting Pitcher WPA

Six Models (wrote 6 but have 7)
	- Always Home Team Win
		- Home team does have an inherent advantage
	- Logistic Regression
		- predicts home team win
		- very restrictive but good baseline
	- SVM
	- KNN
	- Gradient Boosting
		- cites good results in other sports
	- ANN
		- says tabular data works well with feed forward networks
	- 538 ELO system
		- this should work the best imo

Measure win strength based off of score differential
	- improves performance vs using just W/L data

Tested on 2016-2019, player team movement does not affcet the models
Home win model achieves an accuracy of 53.1%
	- maybe an inherent ~3% edge to home team?

3 metrics to look at -> Area under the receiver operating characteristic curve
Log-Loss
brier Score