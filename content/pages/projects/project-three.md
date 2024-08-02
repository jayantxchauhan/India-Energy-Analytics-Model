---
type: ProjectLayout
title: ANALYSIS 2
colors: colors-a
date: '2022-01-22'
client: Awesome client
description: >-
  The analysis consists of renewable and non renewable sources of electricity
  including hydro , wind, solar , coal , Natural gas. its share in the total
  energy  production in india of past 5 years
featuredImage:
  type: ImageBlock
  url: /images/bg3.jpg
  altText: Project thumbnail image
media:
  type: ImageBlock
  altText: Project image
  url: /images/Screenshot (86).png
---


import pandas as pd

import matplotlib.pyplot as plt
\# Create a dictionary with all your data

data = {    'Date': \['2018-12-31', '2019-12-31', '2020-12-31', '2021-12-31', '2022-12-31', '2023-12-31'],    'SolarGen': \[None, 43219.0000, 53054.0000, 65292.0000, 88956.0000, 105399.8670],    'WindGen': \[56199.000, 57428.000, 53237.000, 64328.000, 69223.000, 79448.989],    'HydroGen': \[136905.00000, 159799.00000, 164436.00000, 162418.00000, 175381.00000, 151236.15665],    'NuclearGen': \[34240.0000, 37241.0000, 39480.0000, 39396.0000, 43260.0000, 48953.4300],    'CoalGen': \[85660.0000, 922684.0000, 877524.0000, 1000573.0000, 1096671.0000, 1258929.0000]}

df = pd.DataFrame(data)

df\['Date'] = pd.to\_datetime(df\['Date'])
\# Fill any missing data points with 0 to ensure the stack plot works

df = df.fillna(0)

plt.figure(figsize=(12, 8))

plt.stackplot(df\['Date'],    

df\['SolarGen'],            

  df\['WindGen'],            

df\['HydroGen'],    

 df\['NuclearGen'],          

 df\['CoalGen'],              

labels=\['Solar Generation', 'Wind Generation', 'Hydro Generation', 'Nuclear Generation', 'Coal Generation'],           

colors=\['#ff9999','#66b3ff','#99ff99','#ffcc99','#c2c2f0'])

plt.title('total Energy Generation Over Time in India')

plt.xlabel('Date')plt.ylabel('Energy Generation')

plt.legend(loc='upper left')

plt.grid(True)

plt.show()
