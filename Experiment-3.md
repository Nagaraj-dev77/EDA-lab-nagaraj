program 1:load the datset

import pandas as pd
df = pd.read_csv("student_dataset.csv")
print(df)

output:<img width="413" height="186" alt="Screenshot 2026-09-04 210005" src="https://github.com/user-attachments/assets/5b642b22-8995-4be1-aca7-681639bd8f87" />

program 2:identify missing value

import pandas as pd
df = pd.read_csv("student_dataset.csv")
print(df.isnull().sum())

output:<img width="145" height="125" alt="Screenshot 2026-09-04 210255" src="https://github.com/user-attachments/assets/ee154c1d-e04e-4e91-9a17-822580405acc" />

program 3:replace missing numerical values using mean

import pandas as pd
df = pd.read_csv("student_dataset.csv")
df["Age"] = df["Age"].fillna(df["Age"].mean())
df["Marks"] = df["Marks"].fillna(df["Marks"].mean())
df["Attendance"] = df["Attendance"].fillna(df["Attendance"].mean())
print(df)

output:<img width="391" height="96" alt="Screenshot 2026-09-04 210841" src="https://github.com/user-attachments/assets/5129f074-f1ea-4f3d-9dd3-980f81bdf153" />

program 4:replace missing categorical value using mode

import pandas as pd
df = pd.read_csv("student_dataset.csv")
df["Department"] = df["Department"].fillna(df["Department"].mode()[0])
print(df)

output:<img width="314" height="102" alt="Screenshot 2026-09-04 211502" src="https://github.com/user-attachments/assets/111caa05-088c-470c-ab2a-2b99ccf822d8" />

program 5:identify duplicate records

import pandas as pd
df = pd.read_csv("student_dataset.csv")
print(df[df.duplicated()])

output:<img width="292" height="49" alt="Screenshot 2026-09-04 212122" src="https://github.com/user-attachments/assets/4e3b326c-ec7e-4bac-a6a3-52f9a1298139" />

program 6:remove duplicate records

import pandas as pd
df = pd.read_csv("student_dataset.csv")
df = df.drop_duplicates()
print(df)

output:<img width="299" height="91" alt="Screenshot 2026-09-04 212813" src="https://github.com/user-attachments/assets/0b903482-011e-4da1-8567-91009892979d" />

program 7:correct inconsistent department values

import pandas as pd
df = pd.read_csv("student_dataset.csv")
df["Department"] = df["Department"].replace("AI&DS", "AIDS")
print(df)

output:<img width="308" height="104" alt="Screenshot 2026-09-04 213241" src="https://github.com/user-attachments/assets/9636f1c6-4785-4b55-b852-8607b2e23c07" />

program 8:verify data consistency

Program 8: Verify Data Consistency
import pandas as pd
df = pd.read_csv("Messy_FoodSales.csv")
df["Age"] = df["Age"].fillna(df["Age"].mean())
df["Marks"] = df["Marks"].fillna(df["Marks"].mean())
df["Attendance"] = df["Attendance"].fillna(df["Attendance"].mean())
df["Department"] = df["Department"].fillna(df["Department"].mode()[0])
df["Department"] = df["Department"].replace("AIDS", "AI&DS")
df = df.drop_duplicates()
print("Missing Values:")
print(df.isnull().sum())
print("\nDuplicate Records:")
print(df.duplicated().sum())
print("\nCleaned Dataset:")
print(df)

output:<img width="395" height="250" alt="Screenshot 2026-09-04 213653" src="https://github.com/user-attachments/assets/cde39a76-dbe4-42f6-b8fc-1ba67573be1b" />
