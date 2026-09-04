program 1:rename ambiguous column names

import pandas as pd
df = pd.read_csv("student_dataset.csv")
print("Original Column Names:")
print(df.columns)
df.rename(columns={
    'id': 'Student_ID',
    'name': 'Student_Name',
    'age': 'Age',
    'dept': 'Department',
    'math': 'Math_Marks',
    'science': 'Science_Marks',
    'english': 'English_Marks'
}, inplace=True)
print("\nRenamed Column Names:")
print(df.columns)

output:<img width="487" height="290" alt="Screenshot 2026-09-04 201657" src="https://github.com/user-attachments/assets/8e2afaef-adda-42b3-9d83-b44637db9b5c" />

program 2:convert data types

import pandas as pd 
df = pd.read_csv("fastfood_sales.csv") 
df.rename(columns={
    'id': 'Student_ID',
    'name': 'Student_Name',
    'age': 'Age',
    'dept': 'Department',
    'math': 'Math_Marks',
    'science': 'Science_Marks',
    'english': 'English_Marks'
}, inplace=True) 
print("Before Conversion:") 
print(df.dtypes) 
df["Price"] = df["Price"].astype(float)  
df["Quantity"] = df["Quantity"].astype(int) 
print("\nAfter Conversion:") 
print(df.dtypes)

output:<img width="171" height="257" alt="Screenshot 2026-09-04 204548" src="https://github.com/user-attachments/assets/3f8915a9-ea9a-41a4-b80c-94b007fc89c1" />

program 3:apply equal width and equal frequency binning

import pandas as pd
df = pd.read_csv("student_dataset.csv")
df["Age_EqualWidth"] = pd.cut(
    df["Age"],
    bins=4,
    labels=["Young", "Adult", "Middle Age", "Senior"]
)
df["Age_EqualFrequency"] = pd.qcut(
    df["Age"],
    q=4,
    labels=["Young", "Adult", "Middle Age", "Senior"]
)
print(df[["Age", "Age_EqualWidth", "Age_EqualFrequency"]])

output:<img width="251" height="131" alt="Screenshot 2026-09-04 205236" src="https://github.com/user-attachments/assets/e77091d5-1045-4af1-998c-648fbb6dc6f4" />
