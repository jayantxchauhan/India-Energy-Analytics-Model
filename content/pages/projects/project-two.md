---
type: ProjectLayout
title: PREDICTION 2
colors: colors-a
date: '2021-12-20'
client: Awesome client
description: The prediction consists of average electricity prices of future years
featuredImage:
  type: ImageBlock
  url: /images/bg2.jpg
  altText: Project thumbnail image
media:
  type: ImageBlock
  url: /images/Screenshot 2024-08-03 000742.png
  altText: altText of the image
  caption: Caption of the image
  elementId: ''
bottomSections: []
---
                            JUPYTER NOTEBOOK PROGRAM

import pandas as pd

import numpy as np

import matplotlib.pyplot as plt 

 from sklearn.model\_selection

 import train\_test\_split

from sklearn.linear\_model

import LinearRegressionfrom sklearn.metrics

import mean\_squared\_error

data = pd.read\_csv('/Users/stone/Documents/GitHub/India-Energy-Analytics-Model/Average\_Elecricity\_Cost.csv')

data.set\_index('Year', inplace=True)

X = data.index.values.reshape(-1, 1)  # Features (Year)

y = data\['Average Electricity Cost'].values  # Target variable

X\_train, X\_test, y\_train, y\_test = train\_test\_split(X, y, test\_size=0.2, random\_state=42)

\# Creating a linear regression model

model = LinearRegression()

\# Fitting the model to the training data

model.fit(X\_train, y\_train)

\# Making predictions on the testing data

y\_pred = model.predict(X\_test)

\# Evaluating the model

mse = mean\_squared\_error(y\_test, y\_pred)print('Mean Squared Error:', mse)

\#Visualizing the data and predictions

plt.scatter(X, y, label='Actual')

plt.plot(X\_test, y\_pred, color='red', label='Predicted')

plt.xlabel('Year')plt.ylabel('Average Electricity Cost')

plt.legend()

plt.show()

\#Visualizing the data and predictions

plt.scatter(X, y, label='Actual')

plt.plot(X\_test, y\_pred, color='red', label='Predicted')

plt.xlabel('Year')

plt.ylabel('Average Electricity Cost')

plt.legend()

plt.show()


