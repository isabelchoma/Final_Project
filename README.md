README
================

## Introduction

As college students, we are constantly busy with classes, homeworks, and
exams. We are all very involved in extracurricular activities outside of
classes, which takes up a lot of time. However, in the free time that we
do have, we love to get together with our friends and watch sports
games. Whether it is the fall semester or the spring semester, there is
always a sport being played (football in the fall, basketball in the
winter, baseball in the spring). Since this project is being completed
in the spring season, we decided to focus our attention on baseball.

Specifically, we are interested in learning more about what influences a
baseball player’s salary. Is it their batting average? Their experience?
Their age? The team they play for? We will analyze these variables, plus
many others, and how they influence a player’s salary. In this case, we
are interested in assessing the following question: What best influences
a hitters’ baseball player’s salary?

To start, we will understand the data by reading literature about
impacts on a baseball player’s salary. This will allow us to absorb the
material we are trying to learn more about before actually starting to
import and analyze the data into an open source data software. Then, we
will provide some descriptive and numeric statistics of the dataset we
collected. This will help provide an overview of the important features
of the variables. Next, we will do some exploratory data analysis,
analyzing any correlations between the independent variables of interest
and the dependent variable. We will utilize plots and graphs to help us
visualize the data. Finally, we will use machine learning models to see
what the best way to identify patterns, make predictions, and improve
its performance over time.

We will calculate the batting average by dividing each player’s total
hits per season by their total at-bat. This batting average is different
because a hit is a batter reaching first base. It is a good starting
point for evaluating a player’s offensive skills. A higher batting
average suggests a batter is more consistent in making solid contact
with the ball and getting on base via hits.

## Data Organization

Data was collected using a website called Baseball Reference, which has
baseball history and statistics for Major League Baseball. It is the
complete source for current and historical baseball players, teams,
scores, and leaders. Specifically, our dataset focuses on statistics
from 1985, showing individuals’ performance, age, and other relevant
information for a singular season.

According to the Bureau Labor of Statistics, salary trends change over
time. With free agencies and salary arbitration, salaries escalate. In
addition, TV revenues fuel salary expansion, as the League has more
money to work with. In order to understand how much a team can spend on
its players, it is important to understand the distribution of their
money. For the owners, player compensation looks like this: Major League
Player Compensation + Benefit Plan Costs + Postseason Share Payments +
Minor League Signing Bonuses (not including associated tax) + Minor
League Salaries And Benefits.

So, in order to comprehend the salary of an individual player, we must
take this distribution into account. Salaries to the players themselves
are comparable to salaries in the entertainment industry: star
performers disproportionately earn higher amounts. These higher amounts
are influenced by performance, seniority, and market size, with
performance being the dominant factor.

After filtering the data by removing the irrelevant attributes to our
analysis, these are the attributes included in our data, as well as
their data type:

### Feature Descriptions for Baseball Data

| Feature       | Description                            | Scale_Type |
|:--------------|:---------------------------------------|:-----------|
| Player_ID     | Player ID                              | Character  |
| Year_ID       | Year ID                                | Ordinal    |
| Hits          | Number of hits per season              | Interval   |
| Games Played  | Games played per season                | Interval   |
| Stint         | How many years player has been on team | Interval   |
| At Bat        | Number of times at bat per season      | Interval   |
| Homeruns      | Home runs per season                   | Interval   |
| RBI           | Runs Batted In per season              | Interval   |
| Birth Year    | Birth Year                             | Interval   |
| Logged_Salary | Yearly salary in dollars, logged       | Ratio      |

Some of the players in the dataset were pitchers and not hitters, so we
had to remove rows with NA values for hits in order to only look at the
hitters.

<table class="table table-striped table-hover" style="width: auto !important; margin-left: auto; margin-right: auto;">
<caption>
Detailed Summary Statistics
</caption>
<thead>
<tr>
<th style="text-align:left;">
Variable
</th>
<th style="text-align:right;">
Count
</th>
<th style="text-align:right;">
Mean
</th>
<th style="text-align:right;">
Median
</th>
<th style="text-align:right;">
SD
</th>
<th style="text-align:right;">
Min
</th>
<th style="text-align:right;">
Max
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
Hits
</td>
<td style="text-align:right;">
11953
</td>
<td style="text-align:right;">
88.6848490
</td>
<td style="text-align:right;">
65.0000
</td>
<td style="text-align:right;">
67.1299314
</td>
<td style="text-align:right;">
0.0000
</td>
<td style="text-align:right;">
284.00000
</td>
</tr>
<tr>
<td style="text-align:left;">
Games Played
</td>
<td style="text-align:right;">
11953
</td>
<td style="text-align:right;">
33.9375889
</td>
<td style="text-align:right;">
32.0000
</td>
<td style="text-align:right;">
20.4525020
</td>
<td style="text-align:right;">
1.0000
</td>
<td style="text-align:right;">
94.00000
</td>
</tr>
<tr>
<td style="text-align:left;">
Stint
</td>
<td style="text-align:right;">
11953
</td>
<td style="text-align:right;">
1.0087007
</td>
<td style="text-align:right;">
1.0000
</td>
<td style="text-align:right;">
0.1014846
</td>
<td style="text-align:right;">
1.0000
</td>
<td style="text-align:right;">
4.00000
</td>
</tr>
<tr>
<td style="text-align:left;">
At Bat
</td>
<td style="text-align:right;">
11953
</td>
<td style="text-align:right;">
14.4105246
</td>
<td style="text-align:right;">
1.0000
</td>
<td style="text-align:right;">
38.0810457
</td>
<td style="text-align:right;">
0.0000
</td>
<td style="text-align:right;">
593.00000
</td>
</tr>
<tr>
<td style="text-align:left;">
Homeruns
</td>
<td style="text-align:right;">
11953
</td>
<td style="text-align:right;">
0.1258262
</td>
<td style="text-align:right;">
0.0000
</td>
<td style="text-align:right;">
0.9721162
</td>
<td style="text-align:right;">
0.0000
</td>
<td style="text-align:right;">
33.00000
</td>
</tr>
<tr>
<td style="text-align:left;">
RBI
</td>
<td style="text-align:right;">
11953
</td>
<td style="text-align:right;">
1.0046014
</td>
<td style="text-align:right;">
0.0000
</td>
<td style="text-align:right;">
4.3189322
</td>
<td style="text-align:right;">
0.0000
</td>
<td style="text-align:right;">
123.00000
</td>
</tr>
<tr>
<td style="text-align:left;">
Birth Year
</td>
<td style="text-align:right;">
11953
</td>
<td style="text-align:right;">
1971.9335732
</td>
<td style="text-align:right;">
1972.0000
</td>
<td style="text-align:right;">
9.6556476
</td>
<td style="text-align:right;">
1939.0000
</td>
<td style="text-align:right;">
1995.00000
</td>
</tr>
<tr>
<td style="text-align:left;">
Logged_Salary
</td>
<td style="text-align:right;">
11953
</td>
<td style="text-align:right;">
13.5320265
</td>
<td style="text-align:right;">
13.1869
</td>
<td style="text-align:right;">
1.3606015
</td>
<td style="text-align:right;">
11.0021
</td>
<td style="text-align:right;">
17.31202
</td>
</tr>
</tbody>
</table>

## Exploratory Data Analysis

### Distribution of Variables

![](README_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->![](README_files/figure-gfm/unnamed-chunk-6-2.png)<!-- -->![](README_files/figure-gfm/unnamed-chunk-6-3.png)<!-- -->![](README_files/figure-gfm/unnamed-chunk-6-4.png)<!-- -->![](README_files/figure-gfm/unnamed-chunk-6-5.png)<!-- -->![](README_files/figure-gfm/unnamed-chunk-6-6.png)<!-- -->![](README_files/figure-gfm/unnamed-chunk-6-7.png)<!-- -->![](README_files/figure-gfm/unnamed-chunk-6-8.png)<!-- -->

Both variables are not normally distributed, so we cannot run tests that
assume normality, such as the Shapiro-Wilk test or Q-Q plots. Instead,
we would use the Pearson Correlation test.

### Pearson Correlation heatmap

![](README_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->

### Scatterplots

### Assumption tests

## Conclusions

## Main Observations

## Future Directions
