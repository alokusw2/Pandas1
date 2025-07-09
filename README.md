# Pandas1

1 Problem 1 : Make a Pandas DataFrame with two-dimensional list	(	https://www.geeksforgeeks.org/make-a-pandas-dataframe-with-two-dimensional-list-python/)

Create Pandas Dataframe from 2D List using pd.DataFrame()
In this example below code creates a Pandas DataFrame ('df') from a two-dimensional list ('lst') with specified column names ('Tag' and 'number') and prints the resulting DataFrame.
------------------------------------------------------
import pandas as pd
lst = [['geek', 25], ['is', 30],
      ['for', 26], ['Geeksforgeeks', 22]]
# creating df object with columns specified
df = pd.Dataframe(lst, columns=['Tag', 'number])
print(df)
------------------------------------------------------
#Create Pandas Dataframe from 2D List using pd.DataFrame.from_records()

import pandas as pd

# Two-dimensional list
data = [['Geek1', 28, 'Analyst'],
        ['Geek2', 35, 'Manager'],
        ['Geek3', 29, 'Developer']]

# Column names
columns = ['Name', 'Age', 'Occupation']

# Creating DataFrame using pd.DataFrame.from_records()
df = pd.DataFrame.from_records(data,columns=columns)

print(df)

------------------------------------------------------
#Create Pandas Dataframe from 2D List using pd.DataFrame.from_dict()

import pandas as pd

# Two-dimensional list
data = [['Geek1', 26, 'Scientist'],
        ['Geek2', 31, 'Researcher'],
        ['Geek3', 24, 'Engineer']]

# Column names
columns = ['Name', 'Age', 'Occupation']

# Creating DataFrame using pd.DataFrame.from_dict()
df = pd.DataFrame.from_dict(dict(zip(columns, zip(*data))))

# Displaying the DataFrame
print(df)
------------------------------------------------------------
#Create Pandas Dataframe from 2D List using Specifying Data Types

import pandas as pd

# Two-dimensional list
data = [['Geek1', 'Reacher', 25],
        ['Geek2', 'Pete', 30],
        ['Geek3', 'Wilson', 26],
        ['Geek4', 'Williams', 22]]

# Column names
columns = ['FName', 'LName', 'Age']

# Creating DataFrame with specified data types
df = pd.DataFrame(data, columns = columns)

# Displaying the DataFrame
print(df)


------------------------------------------------------------

------------------------------------------------------
2 Problem 2 :Big Countries	(	https://leetcode.com/problems/big-countries/ )
------------------------------------------------------------
import pandas as pd

def big_countries(world: pd.DataFrame) -> pd.DataFrame: 
    df = world[(world['area'] >= 3000000) | (world['population'] >= 25000000)]
    #always give condition within ()
    return df[['name', 'population', 'area']]
------------------------------------------------------------------------------

3 Problem 3 :Recyclable and Low Fat Products	(	https://leetcode.com/problems/recyclable-and-low-fat-products/ )

------------------------------------------------------------
import pandas as pd

def find_products(products: pd.DataFrame) -> pd.DataFrame:
    df = products[(products["low_fats"] == 'Y') & (products["recyclable"] == 'Y') ]
    return df[["product_id"]]


------------------------------------------------------------
------------------------------------------------------------
------------------------------------------------------------
------------------------------------------------------------------------------------------------------------------------

4 Problem 4 :Customer Who Never Order	(	https://leetcode.com/problems/customers-who-never-order/  )

import pandas as pd

def find_customers(customers: pd.DataFrame, orders: pd.DataFrame) -> pd.DataFrame:
    merged_df = customers.merge(orders, left_on='id', right_on='customerId', how='left')
    return merged_df[merged_df['customerId'].isna()][['name']]
