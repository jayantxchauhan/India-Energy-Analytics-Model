---
type: ProjectLayout
title: PREDICTION 1
colors: colors-a
date: '2021-10-15'
client: Awesome client
description: 'The analysis consists of the electricity prices of past 12 years. '
featuredImage:
  type: ImageBlock
  url: /images/bg1.jpg
  altText: Project thumbnail image
media:
  type: ImageBlock
  url: /images/Screenshot 2024-08-03 000649.png
  altText: Project image
---
import pandas as pd

import numpy as np

import matplotlib.pyplot as plt

from sklearn.linear\_model

 import LinearRegressionfrom sklearn.model\_selection 

import train\_test\_split


datadata = {    'Date': \['2018-12-31', '2019-12-31', '2020-12-31', '2021-12-31', '2022-12-31', '2023-12-31', '2024-12-31'],    'SolarGen': \[None, 43219.0000, 53054.0000, 65292.0000, 88956.0000, 105399.8670, 71647.3789],    'WindGen': \[56199.000, 57428.000, 53237.000, 64328.000, 69223.000, 79448.989, 46314.673],    'HydroGen': \[136905.00000, 159799.00000, 164436.00000, 162418.00000, 175381.00000, 151236.15665, None]}

df = pd.DataFrame(data)

df = df\[df\['Date'] != '2024-12-31']

df\['Date'] = pd.to\_datetime(df\['Date'])df\['Date\_ordinal'] = df\['Date'].apply(lambda x: x.toordinal())

df\['TotalRenewable'] = df\[\['SolarGen', 'WindGen', 'HydroGen']].sum(axis=1)
X = df\[\['Date\_ordinal']]y = df\['TotalRenewable']

X\_train, X\_test, y\_train, y\_test = train\_test\_split(X, y, test\_size=0.2, random\_state=42)

model = LinearRegression()model.fit(X\_train, y\_train)

future\_dates = pd.date\_range(start='2025-01-01', periods=5, freq='Y')future\_dates\_ordinal = future\_dates.map(lambda x: x.toordinal())future\_X = pd.DataFrame(future\_dates\_ordinal, columns=\['Date\_ordinal'])future\_predictions = model.predict(future\_X)
\# Plot historical data

plt.figure(figsize=(12, 8))

plt.plot(df\['Date'], df\['TotalRenewable'], label='Historical Total Renewable Energy', marker='o')
\# Plot future predictions

plt.plot(future\_dates, future\_predictions, label='Predicted Total Renewable Energy', linestyle='--', marker='o')
\# Add titles and labels

plt.title('Total Renewable Energy Generation and Future Predictions')

plt.xlabel('Date')

plt.ylabel('Total Renewable Energy')

plt.legend()

plt.grid(True)

plt.show()


