program 1-dispay the dataset

import pandas as pd
df=pd.read_csv("student_dataset.csv")
print(df.head())
print("\n dataset information")
print(df.info())

output:<img width="260" height="289" alt="Screenshot 2026-09-04 193621" src="https://github.com/user-attachments/assets/e50463c5-676a-40b9-bb6b-3f030b4cd88f" />

program 2:construct a pair plot with categorial hue

import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("student_dataset.csv")
sns.pairplot(df.vars=["age","math","science","english","attendance"],hue="department",diag_kind="hist")
plt.show()

output:<img width="1569" height="1003" alt="ChatGPT Image Sep 4, 2026, 07_49_24 PM" src="https://github.com/user-attachments/assets/6d5357dd-5a72-4f75-b92f-b3f8eb849bdd" />
