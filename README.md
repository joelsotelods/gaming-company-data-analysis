# Independent Gaming Company Data Analysis
---

Analyzing the data for the fantasy game Heroes of Pymoli.

## Heroes of Pymoli

Congratulations! After a lot of hard work in the data munging mines, you've landed a job as Lead Analyst for an independent gaming company. You've been assigned the task of analyzing the data for their most recent fantasy game Heroes of Pymoli.

Like many others in its genre, the game is free-to-play, but players are encouraged to purchase optional items that enhance their playing experience. As a first task, the company would like you to generate a report that breaks down the game's purchasing data into meaningful insights.

Your final report should include each of the following:

### Player Count

* Total Number of Players


|   Total Players |
|-----------------|
|             576 |


### Purchasing Analysis (Total)

* Number of Unique Items
* Average Purchase Price
* Total Number of Purchases
* Total Revenue


|   Number of Unique Items | Average Price   |   Number of Purchases | Total Revenue   |
|--------------------------|-----------------|-----------------------|-----------------|
|                      183 | $3.05           |                   780 | $2,379.77       |


### Gender Demographics

* Percentage and Count of Male Players
* Percentage and Count of Female Players
* Percentage and Count of Other / Non-Disclosed


|                       |   Total Count |   Percentage of Players |
|-----------------------|---------------|-------------------------|
| **Male**                  |           484 |                   84.03 |
| **Female**                |            81 |                   14.06 |
| **Other / Non-Disclosed** |            11 |                    1.91 |


### Purchasing Analysis (Gender)

* The below each broken by gender
  * Purchase Count
  * Average Purchase Price
  * Total Purchase Value
  * Average Purchase Total per Person by Gender


|                       |   Purchase Count | Average Purchase Price   | Total Purchase Value   | Avg Total Purchase per Person   |
|-----------------------|------------------|--------------------------|------------------------|---------------------------------|
| **Female**                |              113 | $3.20                    | $361.94                | $4.47                           |
| **Male**                  |              652 | $3.02                    | $1,967.64              | $4.07                           |
| **Other / Non-Disclosed** |               15 | $3.35                    | $50.19                 | $4.56                           |


### Age Demographics

* The below each broken into bins of 4 years (i.e. &lt;10, 10-14, 15-19, etc.)
  * Purchase Count
  * Average Purchase Price
  * Total Purchase Value
  * Average Purchase Total per Person by Age Group


|       |   Total Count |   Percentage of Players |
|-------|---------------|-------------------------|
| **<10**   |            17 |                    2.95 |
| **10-14** |            22 |                    3.82 |
| **15-19** |           107 |                   18.58 |
| **20-24** |           258 |                   44.79 |
| **25-29** |            77 |                   13.37 |
| **30-34** |            52 |                    9.03 |
| **35-39** |            31 |                    5.38 |
| **40+**   |            12 |                    2.08 |

## Purchasing Analysis (Age)

* Bin the purchase_data data frame by age
* Run basic calculations to obtain purchase count, avg. purchase price, avg. purchase total per person etc. in the table below
* Create a summary data frame to hold the results
* Optional: give the displayed data cleaner formatting
* Display the summary data frame


| Age   |   Purchase Count | Average Purchase Price   | Total Purchase Value   | Avg Total Purchase per Person   |
|-------|------------------|--------------------------|------------------------|---------------------------------|
| **<10**   |               23 | $3.35                    | $77.13                 | $4.54                           |
| **10-14** |               28 | $2.96                    | $82.78                 | $3.76                           |
| **15-19** |              136 | $3.04                    | $412.89                | $3.86                           |
| **20-24** |              365 | $3.05                    | $1,114.06              | $4.32                           |
| **25-29** |              101 | $2.90                    | $293.00                | $3.81                           |
| **30-34** |               73 | $2.93                    | $214.00                | $4.12                           |
| **35-39** |               41 | $3.60                    | $147.67                | $4.76                           |
| **40+**   |               13 | $2.94                    | $38.24                 | $3.19                           |

### Top Spenders

* Identify the the top 5 spenders in the game by total purchase value, then list (in a table):
  * SN
  * Purchase Count
  * Average Purchase Price
  * Total Purchase Value

| SN          |   Purchase Count | Average Purchase Price   | Total Purchase Value   |
|-------------|------------------|--------------------------|------------------------|
| **Lisosia93**   |                5 | $3.79                    | $18.96                 |
| **Idastidru52** |                4 | $3.86                    | $15.45                 |
| **Chamjask73**  |                3 | $4.61                    | $13.83                 |
| **Iral74**      |                4 | $3.40                    | $13.62                 |
| **Iskadarya95** |                3 | $4.37                    | $13.10                 |
| **Ilarin91**    |                3 | $4.23                    | $12.70                 |

### Most Popular Items

* Identify the 5 most popular items by purchase count, then list (in a table):
  * Item ID
  * Item Name
  * Purchase Count
  * Item Price
  * Total Purchase Value

|   Item ID | Item Name                                    |   Purchase Count | Item Price   | Total Purchase Value   |
|-----------|----------------------------------------------|------------------|--------------|------------------------|
|       **178** | **Oathbreaker, Last Hope of the Breaking Storm** |               12 | $4.23        | $50.76                 |
|       **145** | **Fiery Glass Crusader**                         |                9 | $4.58        | $41.22                 |
|       **108** | **Extraction, Quickblade Of Trembling Hands**    |                9 | $3.53        | $31.77                 |
|        **82** | **Nirvana**                                      |                9 | $4.90        | $44.10                 |
|        **19** | **Pursuit, Cudgel of Necromancy**                |                8 | $1.02        | $8.16                  |
|       **103** | **Singed Scalpel**                              |                8 | $4.35        | $34.80                 |

### Most Profitable Items

* Identify the 5 most profitable items by total purchase value, then list (in a table):
  * Item ID
  * Item Name
  * Purchase Count
  * Item Price
  * Total Purchase Value


<

|   Item ID | Item Name                                    |   Purchase Count | Item Price   | Total Purchase Value   |
|-----------|----------------------------------------------|------------------|--------------|------------------------|
|       **178** | **Oathbreaker, Last Hope of the Breaking Storm** |               12 | $4.23        | $50.76                 |
|        **82** | **Nirvana**                                      |                9 | $4.90        | $44.10                 |
|       **145** | **Fiery Glass Crusader**                         |                9 | $4.58        | $41.22                 |
|        **92** | **Final Critic**                                 |                8 | $4.88        | $39.04                 |
|       **103** | **Singed Scalpel**                               |                8 | $4.35        | $34.80                 |
|        **59** | **Lightning, Etcher of the King**                |                8 | $4.23        | $33.84                 |

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
