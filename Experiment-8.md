Program 1: Calculate Rolling Mean and Standard Deviation

import pandas as pd
df = pd.read_csv("Monthly_House_Price.csv")
df["Date"] = pd.to_datetime(df["Date"])
df.set_index("Date", inplace=True)
df["Rolling_Mean"] = df["House_Price"].rolling(window=3).mean()
df["Rolling_SD"] = df["House_Price"].rolling(window=3).std()
print(df[["House_Price", "Rolling_Mean", "Rolling_SD"]])

output:<img width="314" height="350" alt="Screenshot 2026-09-02 220604" src="https://github.com/user-attachments/assets/145ac55a-3dc0-48de-84d6-556e085132b5" />

Program 2: Plot House Price and Rolling Mean

import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("Monthly_House_Price.csv")
df["Date"] = pd.to_datetime(df["Date"])
df.set_index("Date", inplace=True)
df["Rolling_Mean"] = df["House_Price"].rolling(window=3).mean()
plt.figure(figsize=(10, 5))
plt.plot(df.index, df["House_Price"], label="Original House Price")
plt.plot(df.index, df["Rolling_Mean"], linewidth=3, label="3-Month Rolling Mean")
plt.title("House Price vs 3-Month Rolling Mean")
plt.xlabel("Month")
plt.ylabel("House Price")
plt.legend()
plt.show()

ouput:<img width="653" height="335" alt="Screenshot 2026-09-02 220702" src="https://github.com/user-attachments/assets/97eefa2d-890a-45a1-bedd-e04e4bcf5780" />

Program 3: Plot Rolling Standard Deviation

import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("Monthly_House_Price.csv")
df["Date"] = pd.to_datetime(df["Date"])
df.set_index("Date", inplace=True)
df["Rolling_SD"] = df["House_Price"].rolling(window=3).std()
plt.figure(figsize=(10, 5))
plt.plot(df.index, df["Rolling_SD"], linewidth=3)
plt.title("3-Month Rolling Standard Deviation of House Prices")
plt.xlabel("Month")
plt.ylabel("Standard Deviation")
plt.show()

output:<img width="668" height="343" alt="Screenshot 2026-09-02 220804" src="https://github.com/user-attachments/assets/3c923b28-08b7-4a2f-871f-5e8531d26131" />
