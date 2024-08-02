---
type: ProjectLayout
title: ANALYSIS 3
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
  url: /images/Screenshot (89).png
  altText: Project image
---
                                         JUPYTER NOTEBOOK PROGRAM

import pandas as pd

import numpy as np

import matplotlib.pyplot as plt

df = pd.read\_csv(r'C:/Users/Sumit/OneDrive/Documents/GITHUB IBM DA/India-Energy-Analytics-Model/Average\_Elecricity\_Cost.csv')

cost = df\["Average Electricity Cost"]

year= df.Year

plt.plot(df\['Year'], df\['Average Electricity Cost'], marker='o', linestyle='-')
plt.xlabel('Year')

plt.ylabel('Electricity Cost')

plt.title('Electricity Cost Trend')

plt.grid(True)

plt.show()


