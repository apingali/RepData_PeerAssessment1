# Reproducible Research: Peer Assessment 1
Ashwin Pingali  


## Loading and preprocessing the data
Before begining the analysis we need to unzip the data file activity.zip. I have forked the assignment into a local directory and have created this as a the local repository for GITHUB. 
We will set the working directory to this local repository. We will then use the unzip command to unzip the activity.zip file which is in this local directory.
We will list the files in the directory to ensure that there is a file called activity.csv in the working directory.


```r
setwd("~/GitHub/Reproduceable-Research/RepData_PeerAssessment1")
unzip("activity.zip")
list.files(pattern="*.csv")
```

```
## [1] "activity.csv"
```

We will load the data in the file into a dataframe called Activity.
We will then use the head command to review the data in the dataframe


```r
Activity <- read.csv("activity.csv")
head(Activity)
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

We now have the data all stored in the dataframe ready to process.
Before we begin the analysis we wil install some packages and then load the package data.table and the package dplyr


```r
library(data.table)
library(plyr)
```

## What is mean total number of steps taken per day?
I will use two methods to calculate the mean steps taken per day as I am trying to learn the package data.table and the package plyr.

###Method 1: Using the data.table package
In this method we will convert the Activity dataframe into a table and then arrive at the mean steps per day


```r
library(data.table)
ActivityTable <- data.table(Activity)
MeanSteps1 <- ActivityTable[,list(mean=mean(steps)),by=date]
head(MeanSteps1)
```

```
##          date     mean
## 1: 2012-10-01       NA
## 2: 2012-10-02  0.43750
## 3: 2012-10-03 39.41667
## 4: 2012-10-04 42.06944
## 5: 2012-10-05 46.15972
## 6: 2012-10-06 53.54167
```






## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
