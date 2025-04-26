# Sales_Analysis_for_an_Automobile_Company_USA
A Data Science Project that Analysed  the sales performance of an Automobile company Based in the United States. The company’s sales transaction data generated over the past years was used for this  analysis.

## PROBLEM STATEMENT: 
What are the Top Most-Profitable 5 States for a Bike Product Category in the United States ?

## DATA PRE-PROCESSING
#  importing all the necessary python packages 
#### DATA LOADING
```Python
#solution
import numpy as np 
import pandas as pd 
import matplotlib.pyplot as plt

print ("The packages have been successfully imported")
```
# reading the sales Data into a pandas dataframe
```Python
bikes_df=pd.read_csv("D:/DATA SCIENCE CLASS/_EXCLUSIVE DATA SCIENCE BOOT CAMP_STUDENT FOLDER/_DATASET/bikes.csv")
bikes_df.head()
```
## DATA MODIFICATION
```Python

# (1). Adding the following 3 columns to your pandas Dataframe:  bikes_df


# TotalCostPrice : To be obtained by (OrderQuantity x CostPrice_usd)


bikes_df["TotalCostPrice"] = bikes_df["OrderQuantity"] * bikes_df["CostPrice_usd"] 


# SalesRevenue : To be obtained by (OrderQuantity x SellingPrice_usd)


bikes_df["SalesRevenue"] = bikes_df["OrderQuantity"] * bikes_df["SellingPrice_usd"] 


# Profit : To be obtained by (SalesRevenue - TotalCostPrice)


bikes_df["Profit"] = bikes_df["SalesRevenue"] - bikes_df["TotalCostPrice"]

bikes_df.head()
```
## DATA ANALYSIS

### DATA FILTERING
# Filtering out only the data relevant to solving the problem statement  
```Python
is_usa = bikes_df["CustomerCountry"]== "United States"
is_bike= bikes_df["ProductCategory"]== "Bikes"

bike_in_the_US =bikes_df[(is_usa) & (is_bike)]
bike_in_the_US.head()
```
#### DATA AGGREGATION
# aggreegating the total profit by states in the United States for bike Sales.
```Python
total_profit_by_state = bike_in_the_US.pivot_table(values="Profit",index="CustomerState",aggfunc=np.sum)
total_profit_by_state
```
#### DATA SORTING
# Sorting the Aggregated Data in order to Rank the state according to the top most profitable state
```Python
total_profit_by_state.sort_values("Profit",ascending=False)
```
## RESULTS
#Top Most-Profitable 5 States for a Bike Product Category in the United States
```Python
Top_5_most_profitable_state_USA = total_profit_by_state.sort_values("Profit",ascending=False).head()
Top_5_most_profitable_state_USA
```
## DATA VISUALIZATION
# Visualizing the Result
```Python

Top_5_most_profitable_state_USA.plot(kind="bar")

#add a title and label to the plot
plt.title("The Top 5 Most Profitable for Bike Product in the USA")

plt.ylabel("Total profit in Million Dollars")
plt.xlabel("States")

#showing the plot
plt.show()
```

<img width="451" alt="PROJECT 1 screenshot" src="https://github.com/user-attachments/assets/97051134-2fee-413f-980d-a1525672e41d" />

