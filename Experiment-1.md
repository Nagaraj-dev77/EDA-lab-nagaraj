Program 1: Load and Display the Student Dataset

import pandas as pd
df_student = pd.read_csv("student_dataset.csv")
display(df_student)

output:<img width="628" height="367" alt="Screenshot 2026-09-04 221507" src="https://github.com/user-attachments/assets/7162088d-3446-42e4-9f56-412af4d5d3f5" />


Program 2: Display the First Five Records

import pandas as pd
df_student = pd.read_csv("student_dataset.csv")
display(df_student.head())

output:<img width="572" height="143" alt="Screenshot 2026-09-04 221536" src="https://github.com/user-attachments/assets/96e0fdac-adf1-4b8a-9651-b3447815ecad" />


Program 3: Display the Last Five Records

import pandas as pd
df_student = pd.read_csv("student_dataset.csv")
display(df_student.tail())

output:<img width="560" height="146" alt="Screenshot 2026-09-04 221600" src="https://github.com/user-attachments/assets/e8a49a68-27ae-4630-b519-7f10626633ae" />


Program 4: Display Dataset Information

import pandas as pd
df_student = pd.read_csv("student_dataset.csv")
display(df_student.info())

output:<img width="291" height="197" alt="Screenshot 2026-09-04 221637" src="https://github.com/user-attachments/assets/9de3a7ec-188e-4c73-8649-7bc847151771" />


Program 5: Display Dataset Dimensions

import pandas as pd
df_student = pd.read_csv("student_dataset.csv")
display(df_student.shape)

output:(15, 8)

Program 6: Display Statistical Summary

import pandas as pd
df_student = pd.read_csv("student_dataset.csv")
display(df_student.describe())

output:<img width="508" height="212" alt="Screenshot 2026-09-04 221802" src="https://github.com/user-attachments/assets/89c1911b-599c-4d6d-8b93-e43a89ac5163" />
