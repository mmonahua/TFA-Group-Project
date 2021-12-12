# TFA-Group-Project
Group name: Project Group 37

Group Members and UNI: Yimeng Hua(yh3434), Xinqiao Qin(xq2218) 

Section: 001

## Data Cleaning
The New York City ZIP code we chose for our project is 10019 where both of us reside. Therefore, we first got the subset of data such that the Zip Code is 10019.
```
df = df.loc[df['Incident Zip'] == 10019.0]
```

## Top 10 Analysis
To get the top 10 types of calls to 311 and total incidents of each of these 10 types, we used the groupby function. In the groupby function, we also sorted the values in descending order and get the first 10 values. 
```
top10 = df.groupby(df['Complaint Type']).size().sort_values(ascending=False).iloc[:10]
```

## Parking Analysis
To get whether illegal parking incidents are a larger fraction of total 311 incidents in my ZIP code 10019 than they are in general, we first seperately calculated the proportions and then applied np.where to create the single bool.
```
higher_parking_proportion = np.where(new_proportion>global_proportion, True, False)
```
