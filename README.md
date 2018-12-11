# Independent Gaming Company Data Analysis
---

Analyzing the data for the fantasy game Heroes of Pymoli.

## Heroes of Pymoli

Congratulations! After a lot of hard work in the data munging mines, you've landed a job as Lead Analyst for an independent gaming company. You've been assigned the task of analyzing the data for their most recent fantasy game Heroes of Pymoli.

Like many others in its genre, the game is free-to-play, but players are encouraged to purchase optional items that enhance their playing experience. As a first task, the company would like you to generate a report that breaks down the game's purchasing data into meaningful insights.

Your final report should include each of the following:

### Player Count

* Total Number of Players

<div>
<table border="1" class="dataframe">  <thead>    <tr style="text-align: right;">      <th></th>      <th>Total Players</th>   </tr>  </thead>  <tbody>    <tr>      <th>0</th>     <td>576</td>   </tr>  </tbody></table>
</div>

|    |   Total Players |
|---:|----------------:|
|  0 |             576 |


### Purchasing Analysis (Total)

* Number of Unique Items
* Average Purchase Price
* Total Number of Purchases
* Total Revenue

<div>
<table border="1" class="dataframe">  <thead>    <tr style="text-align: right;">      <th></th>      <th>Number of Unique Items</th>      <th>Average Price</th>      <th>Number of Purchases</th>      <th>Total Revenue</th>    </tr>  </thead>  <tbody>    <tr>      <th>0</th>      <td>183</td>      <td>$3.05</td>      <td>780</td>      <td>$2,379.77</td>    </tr>  </tbody></table>
</div>

|    |   Number of Unique Items | Average Price   |   Number of Purchases | Total Revenue   |
|---:|-------------------------:|:----------------|----------------------:|:----------------|
|  0 |                      183 | $3.05           |                   780 | $2,379.77       |


### Gender Demographics

* Percentage and Count of Male Players
* Percentage and Count of Female Players
* Percentage and Count of Other / Non-Disclosed

<div>
<table border="1" class="dataframe">  <thead>    <tr style="text-align: right;">      <th></th>      <th>Total Count</th>      <th>Percentage of Players</th>    </tr>  </thead>  <tbody>    <tr>      <th>Male</th>      <td>484</td>      <td>84.03</td>    </tr>    <tr>      <th>Female</th>      <td>81</td>      <td>14.06</td>    </tr>    <tr>      <th>Other / Non-Disclosed</th>      <td>11</td>      <td>1.91</td>    </tr>  </tbody></table>
</div>

|                       |   Total Count |   Percentage of Players |
|:----------------------|--------------:|------------------------:|
| Male                  |           484 |                   84.03 |
| Female                |            81 |                   14.06 |
| Other / Non-Disclosed |            11 |                    1.91 |


### Purchasing Analysis (Gender)

* The below each broken by gender
  * Purchase Count
  * Average Purchase Price
  * Total Purchase Value
  * Average Purchase Total per Person by Gender

<div>
<table border="1" class="dataframe">  <thead>    <tr style="text-align: right;">      <th></th>      <th>Purchase Count</th>      <th>Average Purchase Price</th>      <th>Total Purchase Value</th>      <th>Avg Total Purchase per Person</th>    </tr>  </thead>  <tbody>    <tr>      <th>Female</th>      <td>113</td>      <td>$3.20</td>      <td>$361.94</td>      <td>$4.47</td>    </tr>    <tr>      <th>Male</th>      <td>652</td>      <td>$3.02</td>      <td>$1,967.64</td>      <td>$4.07</td>    </tr>    <tr>      <th>Other / Non-Disclosed</th>      <td>15</td>      <td>$3.35</td>      <td>$50.19</td>      <td>$4.56</td>    </tr>  </tbody></table>
</div>

|                       |   Purchase Count | Average Purchase Price   | Total Purchase Value   | Avg Total Purchase per Person   |
|:----------------------|-----------------:|:-------------------------|:-----------------------|:--------------------------------|
| Female                |              113 | $3.20                    | $361.94                | $4.47                           |
| Male                  |              652 | $3.02                    | $1,967.64              | $4.07                           |
| Other / Non-Disclosed |               15 | $3.35                    | $50.19                 | $4.56                           |

|                       |   Purchase Count | Average Purchase Price   | Total Purchase Value   | Avg Total Purchase per Person   |
|-----------------------|------------------|--------------------------|------------------------|---------------------------------|
| Female                |              113 | $3.20                    | $361.94                | $4.47                           |
| Male                  |              652 | $3.02                    | $1,967.64              | $4.07                           |
| Other / Non-Disclosed |               15 | $3.35                    | $50.19                 | $4.56                           |


### Age Demographics

* The below each broken into bins of 4 years (i.e. &lt;10, 10-14, 15-19, etc.)
  * Purchase Count
  * Average Purchase Price
  * Total Purchase Value
  * Average Purchase Total per Person by Age Group

<div>
<table border="1" class="dataframe">  <thead>    <tr style="text-align: right;">      <th></th>      <th>Total Count</th>      <th>Percentage of Players</th>    </tr>  </thead>  <tbody>    <tr>      <th>&lt;10</th>      <td>17</td>      <td>2.95</td>    </tr>    <tr>      <th>10-14</th>      <td>22</td>      <td>3.82</td>    </tr>    <tr>      <th>15-19</th>      <td>107</td>      <td>18.58</td>    </tr>    <tr>      <th>20-24</th>      <td>258</td>      <td>44.79</td>    </tr>    <tr>      <th>25-29</th>      <td>77</td>      <td>13.37</td>    </tr>    <tr>      <th>30-34</th>      <td>52</td>      <td>9.03</td>    </tr>    <tr>      <th>35-39</th>      <td>31</td>      <td>5.38</td>    </tr>    <tr>      <th>40+</th>      <td>12</td>      <td>2.08</td>    </tr>  </tbody></table>
</div>

|       |   Total Count |   Percentage of Players |
|-------|---------------|-------------------------|
| <10   |            17 |                    2.95 |
| 10-14 |            22 |                    3.82 |
| 15-19 |           107 |                   18.58 |
| 20-24 |           258 |                   44.79 |
| 25-29 |            77 |                   13.37 |
| 30-34 |            52 |                    9.03 |
| 35-39 |            31 |                    5.38 |
| 40+   |            12 |                    2.08 |

## Purchasing Analysis (Age)

* Bin the purchase_data data frame by age
* Run basic calculations to obtain purchase count, avg. purchase price, avg. purchase total per person etc. in the table below
* Create a summary data frame to hold the results
* Optional: give the displayed data cleaner formatting
* Display the summary data frame

<div>
<table border="1" class="dataframe">  <thead>    <tr style="text-align: right;">      <th></th>      <th>Purchase Count</th>      <th>Average Purchase Price</th>      <th>Total Purchase Value</th>      <th>Avg Total Purchase per Person</th>    </tr>    <tr>      <th>Age</th>      <th></th>      <th></th>      <th></th>      <th></th>    </tr>  </thead>  <tbody>    <tr>      <th>&lt;10</th>      <td>23</td>      <td>$3.35</td>      <td>$77.13</td>      <td>$4.54</td>    </tr>    <tr>      <th>10-14</th>      <td>28</td>      <td>$2.96</td>      <td>$82.78</td>      <td>$3.76</td>    </tr>    <tr>      <th>15-19</th>      <td>136</td>      <td>$3.04</td>      <td>$412.89</td>      <td>$3.86</td>    </tr>    <tr>      <th>20-24</th>      <td>365</td>      <td>$3.05</td>      <td>$1,114.06</td>      <td>$4.32</td>    </tr>    <tr>      <th>25-29</th>      <td>101</td>      <td>$2.90</td>      <td>$293.00</td>      <td>$3.81</td>    </tr>    <tr>      <th>30-34</th>      <td>73</td>      <td>$2.93</td>      <td>$214.00</td>      <td>$4.12</td>    </tr>    <tr>      <th>35-39</th>      <td>41</td>      <td>$3.60</td>      <td>$147.67</td>      <td>$4.76</td>    </tr>    <tr>      <th>40+</th>      <td>13</td>      <td>$2.94</td>      <td>$38.24</td>      <td>$3.19</td>    </tr>  </tbody></table>
</div>

| Age   |   Purchase Count | Average Purchase Price   | Total Purchase Value   | Avg Total Purchase per Person   |
|-------|------------------|--------------------------|------------------------|---------------------------------|
| <10   |               23 | $3.35                    | $77.13                 | $4.54                           |
| 10-14 |               28 | $2.96                    | $82.78                 | $3.76                           |
| 15-19 |              136 | $3.04                    | $412.89                | $3.86                           |
| 20-24 |              365 | $3.05                    | $1,114.06              | $4.32                           |
| 25-29 |              101 | $2.90                    | $293.00                | $3.81                           |
| 30-34 |               73 | $2.93                    | $214.00                | $4.12                           |
| 35-39 |               41 | $3.60                    | $147.67                | $4.76                           |
| 40+   |               13 | $2.94                    | $38.24                 | $3.19                           |

### Top Spenders

* Identify the the top 5 spenders in the game by total purchase value, then list (in a table):
  * SN
  * Purchase Count
  * Average Purchase Price
  * Total Purchase Value

<table border="1" class="dataframe">  <thead>    <tr style="text-align: right;">      <th></th>      <th>Purchase Count</th>      <th>Average Purchase Price</th>      <th>Total Purchase Value</th>    </tr>    <tr>      <th>SN</th>      <th></th>      <th></th>      <th></th>    </tr>  </thead>  <tbody>    <tr>      <th>Lisosia93</th>      <td>5</td>      <td>$3.79</td>      <td>$18.96</td>    </tr>    <tr>      <th>Idastidru52</th>      <td>4</td>      <td>$3.86</td>      <td>$15.45</td>    </tr>    <tr>      <th>Chamjask73</th>      <td>3</td>      <td>$4.61</td>      <td>$13.83</td>    </tr>    <tr>      <th>Iral74</th>      <td>4</td>      <td>$3.40</td>      <td>$13.62</td>    </tr>    <tr>      <th>Iskadarya95</th>      <td>3</td>      <td>$4.37</td>      <td>$13.10</td>    </tr>    <tr>      <th>Ilarin91</th>      <td>3</td>      <td>$4.23</td>      <td>$12.70</td>    </tr>  </tbody></table>

| SN          |   Purchase Count | Average Purchase Price   | Total Purchase Value   |
|-------------|------------------|--------------------------|------------------------|
| Lisosia93   |                5 | $3.79                    | $18.96                 |
| Idastidru52 |                4 | $3.86                    | $15.45                 |
| Chamjask73  |                3 | $4.61                    | $13.83                 |
| Iral74      |                4 | $3.40                    | $13.62                 |
| Iskadarya95 |                3 | $4.37                    | $13.10                 |
| Ilarin91    |                3 | $4.23                    | $12.70                 |

### Most Popular Items

* Identify the 5 most popular items by purchase count, then list (in a table):
  * Item ID
  * Item Name
  * Purchase Count
  * Item Price
  * Total Purchase Value

<div>
<table border="1" class="dataframe">  <thead>    <tr style="text-align: right;">      <th></th>      <th></th>      <th>Purchase Count</th>      <th>Item Price</th>      <th>Total Purchase Value</th>    </tr>    <tr>      <th>Item ID</th>      <th>Item Name</th>      <th></th>      <th></th>      <th></th>    </tr>  </thead>  <tbody>    <tr>      <th>178</th>      <th>Oathbreaker, Last Hope of the Breaking Storm</th>      <td>12</td>      <td>$4.23</td>      <td>$50.76</td>    </tr>    <tr>      <th>145</th>      <th>Fiery Glass Crusader</th>      <td>9</td>      <td>$4.58</td>      <td>$41.22</td>    </tr>    <tr>      <th>108</th>      <th>Extraction, Quickblade Of Trembling Hands</th>      <td>9</td>      <td>$3.53</td>      <td>$31.77</td>    </tr>    <tr>      <th>82</th>      <th>Nirvana</th>      <td>9</td>      <td>$4.90</td>      <td>$44.10</td>    </tr>    <tr>      <th>19</th>      <th>Pursuit, Cudgel of Necromancy</th>      <td>8</td>      <td>$1.02</td>      <td>$8.16</td>    </tr>    <tr>      <th>103</th>      <th>Singed Scalpel</th>      <td>8</td>      <td>$4.35</td>      <td>$34.80</td>    </tr>  </tbody></table>
</div>

|   Item ID | Item Name                                    |   Purchase Count | Item Price   | Total Purchase Value   |
|-----------|----------------------------------------------|------------------|--------------|------------------------|
|       178 | Oathbreaker, Last Hope of the Breaking Storm |               12 | $4.23        | $50.76                 |
|       145 | Fiery Glass Crusader                         |                9 | $4.58        | $41.22                 |
|       108 | Extraction, Quickblade Of Trembling Hands    |                9 | $3.53        | $31.77                 |
|        82 | Nirvana                                      |                9 | $4.90        | $44.10                 |
|        19 | Pursuit, Cudgel of Necromancy                |                8 | $1.02        | $8.16                  |
|       103 | Singed Scalpel                               |                8 | $4.35        | $34.80                 |

### Most Profitable Items

* Identify the 5 most profitable items by total purchase value, then list (in a table):
  * Item ID
  * Item Name
  * Purchase Count
  * Item Price
  * Total Purchase Value


<div>
<table border="1" class="dataframe">  <thead>    <tr style="text-align: right;">      <th></th>      <th></th>      <th>Purchase Count</th>      <th>Item Price</th>      <th>Total Purchase Value</th>    </tr>    <tr>      <th>Item ID</th>      <th>Item Name</th>      <th></th>      <th></th>      <th></th>    </tr>  </thead>  <tbody>    <tr>      <th>178</th>      <th>Oathbreaker, Last Hope of the Breaking Storm</th>      <td>12</td>      <td>$4.23</td>      <td>$50.76</td>    </tr>    <tr>      <th>82</th>      <th>Nirvana</th>      <td>9</td>      <td>$4.90</td>      <td>$44.10</td>    </tr>    <tr>      <th>145</th>      <th>Fiery Glass Crusader</th>      <td>9</td>      <td>$4.58</td>      <td>$41.22</td>    </tr>    <tr>      <th>92</th>      <th>Final Critic</th>      <td>8</td>      <td>$4.88</td>      <td>$39.04</td>    </tr>    <tr>      <th>103</th>      <th>Singed Scalpel</th>      <td>8</td>      <td>$4.35</td>      <td>$34.80</td>    </tr>    <tr>      <th>59</th>      <th>Lightning, Etcher of the King</th>      <td>8</td>      <td>$4.23</td>      <td>$33.84</td>    </tr>  </tbody></table>
</div>

|   Item ID | Item Name                                    |   Purchase Count | Item Price   | Total Purchase Value   |
|-----------|----------------------------------------------|------------------|--------------|------------------------|
|       178 | Oathbreaker, Last Hope of the Breaking Storm |               12 | $4.23        | $50.76                 |
|        82 | Nirvana                                      |                9 | $4.90        | $44.10                 |
|       145 | Fiery Glass Crusader                         |                9 | $4.58        | $41.22                 |
|        92 | Final Critic                                 |                8 | $4.88        | $39.04                 |
|       103 | Singed Scalpel                               |                8 | $4.35        | $34.80                 |
|        59 | Lightning, Etcher of the King                |                8 | $4.23        | $33.84                 |

## As final considerations:

* You must use the Pandas Library and the Jupyter Notebook.
* You must submit a link to your Jupyter Notebook with the viewable Data Frames.
* You must include a written description of three observable trends based on the data.
* See [Example Solution](HeroesOfPymoli/HeroesOfPymoli_starter.ipynb) for a reference on expected format.





# Example report
---

The below script provides an analytic approach for assessing American preferences of Italian vs. Mexican food. Using data from the US Census and the Yelp API, the script randomly selects over 500 zip codes and aggregates Yelp reviews from the 20 most popular Italian and Mexican restaurants in each area. The data is then parsed and analyzed using Python Pandas and Matplotlib.


```python
# Dependencies
import numpy as np
i
```

## Zip Code Sampling

## Yelp Data Retrieval

## Calculate Summaries

## Display Summary of Results






## Conclusions
---
Based on our analysis, it is clear that the American preference for Italian and Mexican food are similar in nature. As a whole, Americans rate Mexican and Italian restaurants at statistically similar scores (Avg score: 3.8, p-value: 0.285). However, there  exists statistically significant evidence that Americans write more reviews of Italian restaurants than Mexican. This may indicate that there is an increased interest in visiting Italian restaurants at an experiential level. However, it may also merely suggest that Yelp users enjoy writing reviews on Italian restaurants more than Mexican restaurants.
