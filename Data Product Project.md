Data Product Project
========================================================
author: Khalid Saeed
date: 17 August, 2019
autosize: true

Introduction
========================================================

For the Developing Data Products Course Project, I have developed a Shiny Application for use with the mtcars data package in R.

Application Purpose
========================================================

My Shiny application allows the user to choose a car manufacturer from the list, along with an associated feature of the car (please see below for a list of the available features). After doing to, the application will reactively display:

1. All records in the dataset associated with the chosen car manufacturer

2. An average value of the chosen car feature across all of the records associated with the chosen car manufacturer


Code
========================================================


```r
library(datasets)
data(mtcars)

#Extract the row names as a column in the dataset
mtcars$makemodel <- rownames(mtcars)

#Extract the manufacturer/make from the rownames
mtcars$make <- gsub( " .*$", "", mtcars$makemodel)
```


result
========================================================

For the chosen manufacturer and feature, the mean value was then derived in the way shown below. The variables "make" and "feature" in the code below represent the input values selected by the application user:


```r
make <- "Mazda"
feature <- "qsec"

data <- mtcars[mtcars$make==make,feature]
paste("The mean value of",feature,"for",make,"cars is",print(mean(data)))
```

```
[1] 16.74
```

```
[1] "The mean value of qsec for Mazda cars is 16.74"
```

Refrence to the Code and Presentaion
https://github.com/Khalid429/Developing-Product-Project

Shiny Application
https://khalid429.shinyapps.io/mtCars_ShinyApp/
