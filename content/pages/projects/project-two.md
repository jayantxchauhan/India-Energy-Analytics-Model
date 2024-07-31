---
type: ProjectLayout
title: ANALYSIS 1
colors: colors-a
date: '2021-12-20'
client: Awesome client
description: the analysis consists of electricity production in india in one year
featuredImage:
  type: ImageBlock
  url: /images/bg2.jpg
  altText: Project thumbnail image
media:
  type: ImageBlock
  url: /images/Snapchat-57632016.jpg
  altText: altText of the image
  caption: Caption of the image
  elementId: ''
---
code





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





