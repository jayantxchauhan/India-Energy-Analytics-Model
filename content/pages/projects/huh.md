---
type: ProjectLayout
title: ANALYSIS 3
date: '2024-08-15'
client: Awesome client
description: THE Analysis consists of average electricity cost of past 12 yeasr
featuredImage:
  type: ImageBlock
  altText: Project thumbnail image
  caption: ''
  elementId: ''
media:
  type: ImageBlock
  url: /images/Screenshot (89).png
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
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```

```
df = pd.read_csv(r'C:/Users/Sumit/OneDrive/Documents/GITHUB IBM DA/India-Energy-Analytics-Model/Average_Elecricity_Cost.csv')
```

```
cost = df["Average Electricity Cost"]
year= df.Year
```

```
plt.plot(df['Year'], df['Average Electricity Cost'], marker='o', linestyle='-')

plt.xlabel('Year')
plt.ylabel('Electricity Cost')
plt.title('Electricity Cost Trend')
plt.grid(True)
plt.show()
```



     



