---
type: ProjectLayout
title: Analysis 1
date: '2024-08-05'
client: Awesome client
description: The analysis consis
media:
  type: ImageBlock
  url: /images/Screenshot (85).png
  altText: Project image
  caption: Caption of the image
  elementId: ''
addTitleSuffix: true
colors: colors-a
backgroundImage:
  type: BackgroundImage
  url: /images/bg2.jpg
  backgroundSize: cover
  backgroundPosition: center
  backgroundRepeat: no-repeat
  opacity: 100
---

import numpy as ny

import pandas as pd

import matplotlib.pyplot as plt

electricity = df\["IDY.PRD.OEA.ELY"]

year= df.yyyymmdf

\['Year'] = df\['yyyymm'] // 100

df\['Month'] = df\['yyyymm'] % 100

df\['Financial\_Year'] = df.apply(    lambda row: f"{row\['Year']}-{row\['Year'] + 1}" if row\['Month'] >= 4 else f"{row\['Year'] - 1}-{row\['Year']}",    axis=1)

ap = df.groupby('Financial\_Year')\['IDY.PRD.OEA.ELY'].sum().reset\_index()

ap.columns = \['Financial\_Year', 'Total\_Electricity\_Production']
print(ap)

\# Remove rows from index 0 to 10 (inclusive)

ap=ap.drop(index=range(0, 16))
\# Reset the index if needed

ap=ap.reset\_index(drop=True)print(ap)ap=ap.drop(index=10)ap

plt.figure(figsize=(10, 6))

plt.bar(ap\['Financial\_Year'], ap\['Total\_Electricity\_Production'], color='skyblue', edgecolor='black')

plt.xlabel('Financial Year')

plt.ylabel('Total Electricity Production in Million kWh')

plt.title('Total Electricity Production per Financial Year')

plt.xticks(rotation=45, ha='right')

plt.tight\_layout()

plt.show()
