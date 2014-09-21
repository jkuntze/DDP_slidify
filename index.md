---
title       : Dataset Explorer
subtitle    : An example using the mtcars dataset
author      : JKuntze
job         : 
framework   : revealjs        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

# Dataset Explorer

## An example using the mtcars dataset
### JKuntze

---

## What it is

This application provides a framework that could be easily modified to explore any dataset. 
Once it's modified by an user who knows the R language, the application becomes a tool for users who understand statistics but are not necessarily familiar with R. 

The mtcars dataset was used to develop the functionalities. 

---

## What it does

The application provides means to perform basic data exploration, via:
- Histogram
- Scatter plot
- Correlation

Moreover, linear models can be fitted and evaluated, using confidence intervals and plotting residuals.

The next slide shows some of the application outputs. The model suggested by Henderson and Velleman (see references) was chosen to produce this example.

---

## Linear regression outputs




```r
model<-lm(gp100m~wt+hppwt,data=dataset)
kable(summary(model)$coefficients, format="html")
```

<table>
 <thead>
  <tr>
   <th align="left">   </th>
   <th align="right"> Estimate </th>
   <th align="right"> Std. Error </th>
   <th align="right"> t value </th>
   <th align="right"> Pr(>|t|) </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td align="left"> (Intercept) </td>
   <td align="right"> -0.4015 </td>
   <td align="right"> 0.5120 </td>
   <td align="right"> -0.7842 </td>
   <td align="right"> 0.4393 </td>
  </tr>
  <tr>
   <td align="left"> wt </td>
   <td align="right"> 1.4722 </td>
   <td align="right"> 0.1216 </td>
   <td align="right"> 12.1113 </td>
   <td align="right"> 0.0000 </td>
  </tr>
  <tr>
   <td align="left"> hppwt </td>
   <td align="right"> 0.0240 </td>
   <td align="right"> 0.0073 </td>
   <td align="right"> 3.2863 </td>
   <td align="right"> 0.0027 </td>
  </tr>
</tbody>
</table>

```r
summary(model)$adj.r.squared
```

[1] 0.8379

```r
kable(confint(model), format="html")
```

<table>
 <thead>
  <tr>
   <th align="left">   </th>
   <th align="right"> 2.5 % </th>
   <th align="right"> 97.5 % </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td align="left"> (Intercept) </td>
   <td align="right"> -1.4488 </td>
   <td align="right"> 0.6457 </td>
  </tr>
  <tr>
   <td align="left"> wt </td>
   <td align="right"> 1.2236 </td>
   <td align="right"> 1.7208 </td>
  </tr>
  <tr>
   <td align="left"> hppwt </td>
   <td align="right"> 0.0091 </td>
   <td align="right"> 0.0389 </td>
  </tr>
</tbody>
</table>

---

## To know more about it

The application can be found at 
https://jkuntze.shinyapps.io/DDP_shinyapp/

The source code is available at
https://github.com/jkuntze/DDP_shinyapp

### References
- Brian Caffo, PhD, Jeff Leek, PhD, Roger D. Peng, PhD, Developing Data Products - Coursera
- mtcars help file, R Documentation
- Henderson and Velleman (1981), Building multiple regression models interactively. Biometrics, 37, 391–411.



