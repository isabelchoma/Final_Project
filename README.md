README
================

## Data Organization

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

![](README_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->![](README_files/figure-gfm/unnamed-chunk-6-2.png)<!-- -->![](README_files/figure-gfm/unnamed-chunk-6-3.png)<!-- -->![](README_files/figure-gfm/unnamed-chunk-6-4.png)<!-- -->

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
