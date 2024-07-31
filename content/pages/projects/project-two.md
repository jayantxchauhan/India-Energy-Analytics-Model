---
type: ProjectLayout
title: ANALYSIS 1
colors: colors-a
date: '2021-12-20'
client: Awesome client
description: >-
  The analysis consists of electricity production in India in one year. Analysis
  is represented in bar graph.In analyzing India's energy production over the
  past year, it’s evident that the country relies heavily on coal, while also
  making significant strides in renewable sources like solar and wind. The
  energy mix showcases a transition towards greener alternatives, though
  challenges remain with supply and infrastructure. Government initiatives and
  technological advancements are shaping the future landscape, aiming to balance
  growth with environmental sustainability and economic impact.
featuredImage:
  type: ImageBlock
  url: /images/bg2.jpg
  altText: Project thumbnail image
media:
  type: ImageBlock
  url: /images/Screenshot (85).png
  altText: altText of the image
  caption: Caption of the image
  elementId: ''
---
```
                         JUPYTER NOTEBOOK PROGRAM
```

import numpy as ny

import pandas as py

import matplotlib.pyplot as plot

|

|

df=pd.read\_csv(r'C:/Users/Sumit/OneDrive/Documents/GITHUB IBM DA/India-Energy-Analytics-Model/India\_monthly\_data.csv')

|

|

electricity = df\["IDY.PRD.OEA.ELY"]

year= df.yyyymmdf\['Year'] = df\['yyyymm'] // 100

df\['Month'] = df\['yyyymm'] % 100

df\['Financial\_Year'] = df.apply( 

  lambda row: f"{row\['Year']}-{row\['Year'] + 1}" if row\['Month'] >= 4 else f"{row\['Year'] - 1}-{row\['Year']}",    axis=1)

ap = df.groupby('Financial\_Year')\['IDY.PRD.OEA.ELY'].sum().reset\_index()

ap.columns = \['Financial\_Year', 'Total\_Electricity\_Production']
print(ap)

ap=ap.drop(index=range(0, 16))
ap=ap.reset\_index(drop=True)

ap=ap.drop(index=10)

print(ap)

|

|

plt.figure(figsize=(10, 6))

plt.bar(ap\['Financial\_Year'], ap\['Total\_Electricity\_Production'], color='skyblue', edgecolor='black')

plt.xlabel('Financial Year')

plt.ylabel('Total Electricity Production in Million kWh')

plt.title('Total Electricity Production per Financial Year')

plt.xticks(rotation=45, ha='right')

plt.tight\_layout()

plt.show()
