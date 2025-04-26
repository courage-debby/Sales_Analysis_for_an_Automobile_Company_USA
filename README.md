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
