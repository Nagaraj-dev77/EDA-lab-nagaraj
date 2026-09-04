Program 1: Bar Chart – Student Count by Department

import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("student_dataset.csv")
department_count = df["Department"].value_counts()
plt.figure(figsize=(8, 5))
department_count.plot(kind="bar")
plt.title("Student Count by Department")
plt.xlabel("Department")
plt.ylabel("Number of Students")
plt.show()

output:<img width="602" height="347" alt="Screenshot 2026-09-04 215338" src="https://github.com/user-attachments/assets/f131eb6d-0b52-494c-bd08-740fa781b332" />


Program 2: Pie Chart – Student Department Distribution

import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("student_dataset.csv")
department_count = df["Department"].value_counts()
plt.figure(figsize=(7, 7))
department_count.plot(kind="pie", autopct="%1.1f%%")
plt.title("Student Department Distribution")
plt.ylabel("")
plt.show()

output:<img width="284" height="197" alt="Screenshot 2026-09-04 215434" src="https://github.com/user-attachments/assets/236e88db-4d29-4574-ae64-ebb7b22e4048" />


Program 3: Histogram – Math Marks Distribution

import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("student_dataset.csv")
plt.figure(figsize=(8, 5))
plt.hist(df["Math_Marks"], bins=10, edgecolor="black")
plt.title("Distribution of Math Marks")
plt.xlabel("Math Marks")
plt.ylabel("Frequency")
plt.grid(True)
plt.show()

output:<img width="578" height="359" alt="Screenshot 2026-09-04 215510" src="https://github.com/user-attachments/assets/358ac025-5da0-4182-940b-994de43cab44" />


Program 4: Box Plot – Math Marks

import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("student_dataset.csv")
plt.figure(figsize=(6, 5))
plt.boxplot(df["Math_Marks"])
plt.title("Box Plot of Math Marks")
plt.ylabel("Math Marks")
plt.grid(True)
plt.show()

output:<img width="480" height="338" alt="Screenshot 2026-09-04 215545" src="https://github.com/user-attachments/assets/52f03686-bf34-4b8e-949e-8e05e58e4892" />


Program 5: Scatter Plot – Age vs Math Marks

import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("student_dataset.csv")
plt.figure(figsize=(8, 5))
plt.scatter(df["Age"], df["Math_Marks"])
plt.title("Age vs Math Marks")
plt.xlabel("Age")
plt.ylabel("Math Marks")
plt.grid(True)
plt.show()

output:<img width="613" height="346" alt="Screenshot 2026-09-04 215617" src="https://github.com/user-attachments/assets/7d749182-5a11-4f00-8d3c-afd917cc6d1e" />
