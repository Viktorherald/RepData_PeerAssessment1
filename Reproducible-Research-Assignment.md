---
title: "Reproducible Research: Peer Assessment 1"
author: "Viktor Ng"
date: "3/22/2021"
output: 
  html_document:
    keep_md: true
---

### Set-up Process

---

Welcome to my assignment report!

Firstly, we will unzip and load the data to a data frame.


```r
unzip("activity.zip")
df <- read.csv("activity.csv")
```

Before the rest of analysis is conducted, it is good to check on how the data looks like in the data frame and its structure, with below.


```r
head(df)
```

```
##   steps       date interval
## 1    NA 2012-10-01        0
## 2    NA 2012-10-01        5
## 3    NA 2012-10-01       10
## 4    NA 2012-10-01       15
## 5    NA 2012-10-01       20
## 6    NA 2012-10-01       25
```

```r
str(df)
```

```
## 'data.frame':	17568 obs. of  3 variables:
##  $ steps   : int  NA NA NA NA NA NA NA NA NA NA ...
##  $ date    : chr  "2012-10-01" "2012-10-01" "2012-10-01" "2012-10-01" ...
##  $ interval: int  0 5 10 15 20 25 30 35 40 45 ...
```

Notice that the date is in type "chr". We try to transform the date column into Date object first so we will have an easier time dealing with it later on. 
I will be using dplyr package for this.


```r
library(dplyr)
df <- df %>%
        mutate(date = as.Date(date))

str(df)
```

```
## 'data.frame':	17568 obs. of  3 variables:
##  $ steps   : int  NA NA NA NA NA NA NA NA NA NA ...
##  $ date    : Date, format: "2012-10-01" "2012-10-01" ...
##  $ interval: int  0 5 10 15 20 25 30 35 40 45 ...
```
### What is mean total number of steps taken per day?

### What is the average daily activity pattern?

### Imputing missing values

### Are there differences in activity patterns between weekdays and weekends?
