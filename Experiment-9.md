program 1:

import pandas as pd
from scipy.stats import ttest_ind
data = {
    "Date": [
        "01/01/2024", "01/02/2024", "01/03/2024",
        "01/04/2024", "01/05/2024", "01/06/2024",
        "01/07/2024", "01/08/2024", "01/09/2024",
        "01/10/2024", "01/11/2024", "01/12/2024",
        "01/01/2024", "01/02/2024", "01/03/2024",
        "01/04/2024", "01/05/2024", "01/06/2024",
        "01/07/2024", "01/08/2024", "01/09/2024",
        "01/10/2024", "01/11/2024", "01/12/2024"
    ],

    "Location": ["Chennai"] * 24,

    "House_Type": [
        "Apartment"] * 12 + ["Villa"] * 12,

    "House_Price": [
        4500000, 4600000, 4750000, 4700000,
        4900000, 5050000, 5200000, 5350000,
        5500000, 5450000, 5700000, 5900000,

        6500000, 6700000, 6900000, 6800000,
        7100000, 7300000, 7500000, 7700000,
        7900000, 7800000, 8100000, 8400000
    ]
}
df = pd.DataFrame(data)
df.to_csv("Monthly_House_Price.csv", index=False)
apartment = df[df["House_Type"] == "Apartment"]["House_Price"]
villa = df[df["House_Type"] == "Villa"]["House_Price"]
t_value, p_value = ttest_ind(apartment, villa)
print("t-value :", t_value)
print("p-value :", p_value)

output:<img width="181" height="47" alt="Screenshot 2026-09-03 185201" src="https://github.com/user-attachments/assets/7350d82a-55cc-410f-b8d6-1e5b7a6ad05d" />

program 2:

import pandas as pd
from scipy.stats import ttest_ind
df = pd.read_csv("Monthly_House_Price.csv")
apartment = df[df["House_Type"] == "Apartment"]["House_Price"]
villa = df[df["House_Type"] == "Villa"]["House_Price"]
t_value, p_value = ttest_ind(apartment, villa)
alpha = 0.05
print("t-value :", t_value)
print("p-value :", p_value)
if p_value < alpha:
    print("\nConclusion:")
    print("Reject the Null Hypothesis (H0)")
    print("There is a significant difference between")
    print("the prices of Apartments and Villas.")
else:
    print("\nConclusion:")
    print("Fail to Reject the Null Hypothesis (H0)")
    print("There is no significant difference between")
    print("the prices of Apartments and Villas.")

output:<img width="250" height="107" alt="Screenshot 2026-09-03 185508" src="https://github.com/user-attachments/assets/051bde82-524c-42f7-b58d-c1e9ccd76ada" />


program 3:

import pandas as pd
df = pd.read_csv("Monthly_House_Price.csv")
stats = df.groupby("House_Type")["House_Price"].agg(
    ["count", "mean", "std", "min", "max"]
)

print("House Price Statistics by House Type")
print(stats)

output:<img width="396" height="77" alt="Screenshot 2026-09-03 185633" src="https://github.com/user-attachments/assets/0039a4e4-7b32-4776-8894-08babc785578" />
