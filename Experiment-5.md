program 1: create correlation matrix

import pandas as pd
df = pd.read_csv("student_dataset.csv")
num_data = df.select_dtypes(include=['number'])
corr_matrix = num_data.corr()
print("Correlation Matrix")
print(corr_matrix)

output:<img width="388" height="101" alt="Screenshot 2026-09-04 191338" src="https://github.com/user-attachments/assets/28e42643-5267-49b6-83f1-c72fdfb58c2e" />

program 2:display correlation matrix using heatmap

import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
df = pd.read_csv("student_dataset.csv")
num_data = df.select_dtypes(include=['number'])
corr_matrix = num_data.corr()
plt.figure(figsize=(8, 6))
sns.heatmap(corr_matrix, annot=True, cmap="coolwarm", fmt=".2f")
plt.title("Student Correlation Matrix Heatmap")
plt.show()

ouput:<img width="473" height="362" alt="Screenshot 2026-09-04 192024" src="https://github.com/user-attachments/assets/edc5f7a8-54e9-4895-92d7-e2f6e18848ae" />

program 3:identify highly correlation variables

import pandas as pd
df=pd.read_csv("student_dataset.csv")
num_data = df.select_dtypes(include=['number'])
corr_matrix = num_data.corr()
print("highly correlation variable pairs\n")
for i in range(len(corr_matrix.columns)):
for j in range(i+1 len(corr_matrix.columns)):
value=corr_matrix.iloc[i,j]
if value>0.8 or value<-0.8:
print(corr_matrix.columns[i],"<-->",corr_matrix.columns[j],"=",round(value,2))

output:<img width="207" height="81" alt="Screenshot 2026-09-04 192845" src="https://github.com/user-attachments/assets/6aec6f8f-0d21-460d-82a0-700d9e3cff19" />
