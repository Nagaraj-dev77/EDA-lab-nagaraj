program 1:

import pandas as pd
df = pd.read_csv("House_Price_Dataset.csv")
df["Date"] = pd.to_datetime(df["Date"], format="%d/%m/%Y")
df.set_index("Date", inplace=True)
monthly_data = df.resample("ME").sum(numeric_only=True)
print("Monthly House Price Summary")
print(monthly_data)

output:<img width="167" height="56" alt="Screenshot 2026-09-03 190508" src="https://github.com/user-attachments/assets/5478f3b4-e1d5-484b-9d44-55723db393c8" />

program 2:

import pandas as pd
df = pd.read_csv("House_Price_Resample_Dataset.csv")
df["Date"] = pd.to_datetime(df["Date"], dayfirst=True)
df.set_index("Date", inplace=True)
monthly_data = df.resample("ME").mean(numeric_only=True)
daily_data = monthly_data.resample("D").ffill()
print("Up-Sampled Daily House Price Data")
print(daily_data.head(15))

output:<img width="196" height="53" alt="Screenshot 2026-09-03 192957" src="https://github.com/user-attachments/assets/3b31de23-6704-4af5-b367-b516ed84f81b" />
