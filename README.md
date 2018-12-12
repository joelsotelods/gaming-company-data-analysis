# Independent Gaming Company Data Analysis
---

Analyzing the data for the fantasy game Heroes of Pymoli.

## Heroes of Pymoli

Congratulations! After a lot of hard work in the data munging mines, you've landed a job as Lead Analyst for an independent gaming company. You've been assigned the task of analyzing the data for their most recent fantasy game Heroes of Pymoli.

Like many others in its genre, the game is free-to-play, but players are encouraged to purchase optional items that enhance their playing experience. As a first task, the company would like you to generate a report that breaks down the game's purchasing data into meaningful insights.

---
## Report

The below script provides an analytic approach for the information of sales of optional items on the Heroes of Pymoli video game. The data was loaded from a csv, then parsed and analyzed using Python Pandas.

Click here to see the [Solution code](HeroesOfPymoli.ipynb).

##### Initial Code:

```python
# Dependencies and Setup
import pandas as pd
import numpy as np
from tabulate import tabulate

# File to Load (Remember to Change These)
file_to_load = "Resources/purchase_data.csv"

# Read Purchasing File and store into Pandas data frame
purchase_data = pd.read_csv(file_to_load)

purchase_data.head()

# Tabulate code to export any data frame to MarkDown table
#print(tabulate(df, tablefmt="pipe", headers="keys").replace('---:','----').replace(':---','----'))

# Code to export DataFrame to html
#df.to_html().replace("\n", "")
```



### Player Count

* Total Number of Players

##### Code:

```python
#Get number of players by groupyin by User Name and then getting the unique and counting them.
num_players = purchase_data.groupby('SN')['SN'].nunique().count()

#adding the total players count as a data frame to show it
df = pd.DataFrame([[num_players]], columns=['Total Players'])

df.head()
```
##### DataFrame Output:
|   Total Players |
|-----------------|
|             576 |


### Purchasing Analysis (Total)

* Number of Unique Items
* Average Purchase Price
* Total Number of Purchases
* Total Revenue 

##### Code:
```python
num_unique_items = purchase_data.groupby('Item ID')['Item ID'].nunique().count()
average_price = purchase_data['Price'].mean()
number_of_purchases = purchase_data.groupby('Purchase ID')['Purchase ID'].nunique().count()
total_revenue = purchase_data['Price'].sum()

data = [num_unique_items, f'${average_price:,.2f}',number_of_purchases,f'${total_revenue:,.2f}']

#adding as a data frame to show it
df = pd.DataFrame([data], columns=['Number of Unique Items','Average Price', 'Number of Purchases', 'Total Revenue'])

df
```
##### DataFrame Output:
|   Number of Unique Items | Average Price   |   Number of Purchases | Total Revenue   |
|--------------------------|-----------------|-----------------------|-----------------|
|                      183 | $3.05           |                   780 | $2,379.77       |


### Gender Demographics

* Percentage and Count of Male Players
* Percentage and Count of Female Players
* Percentage and Count of Other / Non-Disclosed

##### Code:
```python
genders = purchase_data.groupby(['Gender','SN'])['Gender','SN'].count()

genders.columns = ['sa','sd']

genders= genders.reset_index()

genders = genders.drop(columns=['sa','sd'])

genders = genders.groupby(['Gender']).count()

del genders.index.name

genders.columns = ['Total Count']

genders['Percentage of Players'] =  np.around( (genders['Total Count']/num_players)*100 , decimals=2)

genders = genders.sort_values(by=['Total Count'] , ascending=False).head()

genders
```

##### DataFrame Output:
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

##### Code:
```python
gender_analysys = purchase_data.groupby('Gender').agg({'Purchase ID': 'count', 'Price': ['mean','sum'], 'Gender': 'count'})

gender_analysys.columns = gender_analysys.columns.droplevel()

gender_analysys.columns = ['Purchase Count', 'Average Purchase Price', 'Total Purchase Value', 'Persons by Purchase']

gender_analysys = pd.merge(gender_analysys, genders, left_index=True, right_index=True)

gender_analysys['Avg Total Purchase per Person'] = gender_analysys['Total Purchase Value']/gender_analysys['Total Count']

gender_analysys['Average Purchase Price'] = gender_analysys.apply(lambda x: "${:,.2f}".format(x['Average Purchase Price']), axis=1)
gender_analysys['Total Purchase Value'] = gender_analysys.apply(lambda x: "${:,.2f}".format(x['Total Purchase Value']), axis=1)
gender_analysys['Avg Total Purchase per Person'] = gender_analysys.apply(lambda x: "${:,.2f}".format(x['Avg Total Purchase per Person']), axis=1)

gender_report = gender_analysys[['Purchase Count','Average Purchase Price','Total Purchase Value','Avg Total Purchase per Person']]

gender_report
```

##### DataFrame Output:
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

##### Code:
```python
bins = [0, 9, 14, 19, 24, 29, 34, 39, 1000]

groups_xxx = purchase_data.groupby(['Age','SN'])['Age','SN'].count()

groups_xxx.columns = ['sa','sd']

groups_xxx= groups_xxx.reset_index()

groups_xxx = groups_xxx.drop(columns=['sa','sd'])

groups_xxx = groups_xxx.groupby(['Age']).count()

groups_xxx= groups_xxx.reset_index()

groups_xxx.columns = ['Age','Total Count']

bins = pd.cut(groups_xxx['Age'], bins, labels=['<10', '10-14', '15-19', '20-24', '25-29', '30-34','35-39','40+'])

groups_xxx = groups_xxx.groupby(bins).agg(['sum'])

groups_xxx.columns = groups_xxx.columns.droplevel(1)

del groups_xxx.index.name

groups_xxx['Percentage of Players'] =  np.around( (groups_xxx['Total Count']/num_players)*100 , decimals=2)

groups_xxx[['Total Count','Percentage of Players']]
```
##### DataFrame Output:
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

* The below each broken by age
  * Purchase Count
  * Average Purchase Price
  * Total Purchase Value
  * Average Purchase Total per Person by Age

##### Code:
```python
bins = [0, 9, 14, 19, 24, 29, 34, 39, 1000]

groups_xxx_ps = purchase_data[['Age', 'Purchase ID','Price']]

bins = pd.cut(groups_xxx_ps['Age'], bins, labels=['<10', '10-14', '15-19', '20-24', '25-29', '30-34','35-39','40+'])

groups_xxx_ps = groups_xxx_ps.groupby(bins).agg({'Purchase ID': 'count', 'Price':['sum','mean']})

groups_xxx_ps.columns = groups_xxx_ps.columns.droplevel(1)

groups_xxx_ps.columns = ['Purchase Count','Total Purchase Value', 'Average Purchase Price']

groups_xxx_ps = pd.merge(groups_xxx_ps, groups_xxx[['Total Count','Percentage of Players']], left_index=True, right_index=True)


groups_xxx_ps['Avg Total Purchase per Person'] = groups_xxx_ps['Total Purchase Value']/groups_xxx_ps['Total Count']

groups_xxx_ps['Average Purchase Price'] = groups_xxx_ps.apply(lambda x: "${:,.2f}".format(x['Average Purchase Price']), axis=1)
groups_xxx_ps['Total Purchase Value'] = groups_xxx_ps.apply(lambda x: "${:,.2f}".format(x['Total Purchase Value']), axis=1)
groups_xxx_ps['Avg Total Purchase per Person'] = groups_xxx_ps.apply(lambda x: "${:,.2f}".format(x['Avg Total Purchase per Person']), axis=1)


groups_xxx_ps_report = groups_xxx_ps[['Purchase Count','Average Purchase Price','Total Purchase Value','Avg Total Purchase per Person']]


groups_xxx_ps_report
```

##### DataFrame Output:
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

##### Code:
```python
top_spenders = purchase_data.groupby(['SN']).agg({'Purchase ID': 'count', 'Price': ['mean','sum']})

top_spenders.columns = top_spenders.columns.droplevel(1)

top_spenders.columns = ['Purchase Count','Average Purchase Price', 'Total Purchase Value']

top_spenders = top_spenders.sort_values('Total Purchase Value', ascending=False)

top_spenders['Average Purchase Price'] = top_spenders.apply(lambda x: "${:,.2f}".format(x['Average Purchase Price']), axis=1)
top_spenders['Total Purchase Value'] = top_spenders.apply(lambda x: "${:,.2f}".format(x['Total Purchase Value']), axis=1)


top_spenders.head(6)
```

##### DataFrame Output:
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

##### Code:
```python
sales_by_item = purchase_data.groupby(['Item ID','Item Name']).agg({'Purchase ID': 'count', 'Price': ['max','sum']})

sales_by_item.columns = sales_by_item.columns.droplevel(1)

sales_by_item.columns = ['Purchase Count','Item Price', 'Total Purchase Value']

popular_items = sales_by_item.sort_values('Purchase Count', ascending=False)

popular_items['Item Price'] = popular_items.apply(lambda x: "${:,.2f}".format(x['Item Price']), axis=1)
popular_items['Total Purchase Value'] = popular_items.apply(lambda x: "${:,.2f}".format(x['Total Purchase Value']), axis=1)

popular_items.head(6)
```

##### DataFrame Output:
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


##### Code:
```python
profitable_items = sales_by_item.sort_values('Total Purchase Value', ascending=False)

profitable_items['Item Price'] = profitable_items.apply(lambda x: "${:,.2f}".format(x['Item Price']), axis=1)
profitable_items['Total Purchase Value'] = profitable_items.apply(lambda x: "${:,.2f}".format(x['Total Purchase Value']), axis=1)

profitable_items.head(6)
```

##### DataFrame Output:
|   Item ID | Item Name                                    |   Purchase Count | Item Price   | Total Purchase Value   |
|-----------|----------------------------------------------|------------------|--------------|------------------------|
|       **178** | **Oathbreaker, Last Hope of the Breaking Storm** |               12 | $4.23        | $50.76                 |
|        **82** | **Nirvana**                                      |                9 | $4.90        | $44.10                 |
|       **145** | **Fiery Glass Crusader**                         |                9 | $4.58        | $41.22                 |
|        **92** | **Final Critic**                                 |                8 | $4.88        | $39.04                 |
|       **103** | **Singed Scalpel**                               |                8 | $4.35        | $34.80                 |
|        **59** | **Lightning, Etcher of the King**                |                8 | $4.23        | $33.84                 |



## Conclusions

Based on our analysis, the following conclusions can be stated:

* From the 576 unique users that Purchase something, the majority of them are from 20 to 24 years old (%44.79), however, 	The most profitable users are the ones between 35 to 39 years old, spending $4.76 aproximately by user, compaired to $4.32 spend by user on the range 20-24.

* *Nirvana* not only is among the most popular items, it is also one of the most profitables, beign $4.90.

* *Extraction, Quickblade Of Trembling Hands*, is the third most popular item on the store's game, and even though is not the most profitable, 9 purchases has made Heroes of Pymoli $31.77 bucks.
