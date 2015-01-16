---
title: "Reproducible Research: Peer Assessment 1"
output: 
  html_document:
    keep_md: true
---


## Loading and preprocessing the data


```r
library("knitr")
activity <- read.csv("activity.csv")
activity$date <- as.Date(as.character(activity$date),"%Y-%m-%d")
```


## What is mean total number of steps taken per day?

```r
stepsDaily<- with(activity,tapply(activity$steps,activity$date,sum))
hist(stepsDaily)
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2-1.png) 

Mean steps by day

```r
data.frame(with(activity,tapply(activity$steps,activity$date,mean)))
```

```
##            with.activity..tapply.activity.steps..activity.date..mean..
## 2012-10-01                                                          NA
## 2012-10-02                                                   0.4375000
## 2012-10-03                                                  39.4166667
## 2012-10-04                                                  42.0694444
## 2012-10-05                                                  46.1597222
## 2012-10-06                                                  53.5416667
## 2012-10-07                                                  38.2465278
## 2012-10-08                                                          NA
## 2012-10-09                                                  44.4826389
## 2012-10-10                                                  34.3750000
## 2012-10-11                                                  35.7777778
## 2012-10-12                                                  60.3541667
## 2012-10-13                                                  43.1458333
## 2012-10-14                                                  52.4236111
## 2012-10-15                                                  35.2048611
## 2012-10-16                                                  52.3750000
## 2012-10-17                                                  46.7083333
## 2012-10-18                                                  34.9166667
## 2012-10-19                                                  41.0729167
## 2012-10-20                                                  36.0937500
## 2012-10-21                                                  30.6284722
## 2012-10-22                                                  46.7361111
## 2012-10-23                                                  30.9652778
## 2012-10-24                                                  29.0104167
## 2012-10-25                                                   8.6527778
## 2012-10-26                                                  23.5347222
## 2012-10-27                                                  35.1354167
## 2012-10-28                                                  39.7847222
## 2012-10-29                                                  17.4236111
## 2012-10-30                                                  34.0937500
## 2012-10-31                                                  53.5208333
## 2012-11-01                                                          NA
## 2012-11-02                                                  36.8055556
## 2012-11-03                                                  36.7048611
## 2012-11-04                                                          NA
## 2012-11-05                                                  36.2465278
## 2012-11-06                                                  28.9375000
## 2012-11-07                                                  44.7326389
## 2012-11-08                                                  11.1770833
## 2012-11-09                                                          NA
## 2012-11-10                                                          NA
## 2012-11-11                                                  43.7777778
## 2012-11-12                                                  37.3784722
## 2012-11-13                                                  25.4722222
## 2012-11-14                                                          NA
## 2012-11-15                                                   0.1423611
## 2012-11-16                                                  18.8923611
## 2012-11-17                                                  49.7881944
## 2012-11-18                                                  52.4652778
## 2012-11-19                                                  30.6979167
## 2012-11-20                                                  15.5277778
## 2012-11-21                                                  44.3993056
## 2012-11-22                                                  70.9270833
## 2012-11-23                                                  73.5902778
## 2012-11-24                                                  50.2708333
## 2012-11-25                                                  41.0902778
## 2012-11-26                                                  38.7569444
## 2012-11-27                                                  47.3819444
## 2012-11-28                                                  35.3576389
## 2012-11-29                                                  24.4687500
## 2012-11-30                                                          NA
```

Median steps by day

```r
data.frame(with(activity,tapply(activity$steps,activity$date,median)))
```

```
##            with.activity..tapply.activity.steps..activity.date..median..
## 2012-10-01                                                            NA
## 2012-10-02                                                             0
## 2012-10-03                                                             0
## 2012-10-04                                                             0
## 2012-10-05                                                             0
## 2012-10-06                                                             0
## 2012-10-07                                                             0
## 2012-10-08                                                            NA
## 2012-10-09                                                             0
## 2012-10-10                                                             0
## 2012-10-11                                                             0
## 2012-10-12                                                             0
## 2012-10-13                                                             0
## 2012-10-14                                                             0
## 2012-10-15                                                             0
## 2012-10-16                                                             0
## 2012-10-17                                                             0
## 2012-10-18                                                             0
## 2012-10-19                                                             0
## 2012-10-20                                                             0
## 2012-10-21                                                             0
## 2012-10-22                                                             0
## 2012-10-23                                                             0
## 2012-10-24                                                             0
## 2012-10-25                                                             0
## 2012-10-26                                                             0
## 2012-10-27                                                             0
## 2012-10-28                                                             0
## 2012-10-29                                                             0
## 2012-10-30                                                             0
## 2012-10-31                                                             0
## 2012-11-01                                                            NA
## 2012-11-02                                                             0
## 2012-11-03                                                             0
## 2012-11-04                                                            NA
## 2012-11-05                                                             0
## 2012-11-06                                                             0
## 2012-11-07                                                             0
## 2012-11-08                                                             0
## 2012-11-09                                                            NA
## 2012-11-10                                                            NA
## 2012-11-11                                                             0
## 2012-11-12                                                             0
## 2012-11-13                                                             0
## 2012-11-14                                                            NA
## 2012-11-15                                                             0
## 2012-11-16                                                             0
## 2012-11-17                                                             0
## 2012-11-18                                                             0
## 2012-11-19                                                             0
## 2012-11-20                                                             0
## 2012-11-21                                                             0
## 2012-11-22                                                             0
## 2012-11-23                                                             0
## 2012-11-24                                                             0
## 2012-11-25                                                             0
## 2012-11-26                                                             0
## 2012-11-27                                                             0
## 2012-11-28                                                             0
## 2012-11-29                                                             0
## 2012-11-30                                                            NA
```

## What is the average daily activity pattern?

Average number of steps taken, averaged across all days (y-axis)

```r
byMinuteInterval <- with(activity,tapply(activity$steps,activity$interval,mean,na.rm=TRUE))
plot(byMinuteInterval,type='l')
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-5-1.png) 

Which 5-minute interval, on average across all the days in the dataset, contains the maximum number of steps?


```r
max(byMinuteInterval)
```

```
## [1] 206.1698
```

Knowing the maximum value, we look for the minute interval.

```r
maxByMinute<-byMinuteInterval[byMinuteInterval>206]
```

The minute interval is 835.

## Imputing missing values


```r
total_nas <- sum(is.na(activity[,1]))
```
The total number NA steps data is 2304

Filling NA values with the *mean* by minute interval.


```r
for (i in 1:length(activity$steps)) {
    if(is.na(activity$steps[i])){
        boolInterval <- activity$interval[i]==as.numeric(as.character(names(byMinuteInterval)));
        activityFilled[i,1]<-byMinuteInterval[boolInterval]
    } else {
        activityFilled[i,1]<-activity$steps[i]
    }
    if(exists("boolInterval")) rm(boolInterval)
}
```

Creating a new dataset that is equal to the original dataset but with the missing data filled in.


```r
activityFilled2<-data.frame()
activityFilled2<-cbind(as.double(activityFilled[,1]),as.character(activity$date),as.integer(activity$interval))
colnames(activityFilled2)<-colnames(activity)
activityFilled2<-as.data.frame(activityFilled2)
```

Histogram of steps by day with the filled data.


```r
activityFilled2$date <- as.Date(as.character(activityFilled2$date),"%Y-%m-%d")
rm(stepsDaily)
stepsDaily<- with(activityFilled2,tapply(as.numeric(activityFilled2$steps),activityFilled2$date,sum))
hist(stepsDaily)
```

![plot of chunk unnamed-chunk-11](figure/unnamed-chunk-11-1.png) 

Mean steps by day with the filled data.


```r
data.frame(with(activityFilled2,tapply(as.numeric(activityFilled2$steps),activityFilled2$date,mean)))
```

```
##            with.activityFilled2..tapply.as.numeric.activityFilled2.steps...
## 2012-10-01                                                       363.111111
## 2012-10-02                                                         4.138889
## 2012-10-03                                                       128.059028
## 2012-10-04                                                       147.118056
## 2012-10-05                                                       128.423611
## 2012-10-06                                                       156.524306
## 2012-10-07                                                       151.059028
## 2012-10-08                                                       363.111111
## 2012-10-09                                                       129.027778
## 2012-10-10                                                       144.170139
## 2012-10-11                                                       118.368056
## 2012-10-12                                                       175.149306
## 2012-10-13                                                       161.909722
## 2012-10-14                                                       146.892361
## 2012-10-15                                                       132.486111
## 2012-10-16                                                       143.878472
## 2012-10-17                                                       139.156250
## 2012-10-18                                                       101.586806
## 2012-10-19                                                       134.420139
## 2012-10-20                                                       128.944444
## 2012-10-21                                                       130.131944
## 2012-10-22                                                       129.743056
## 2012-10-23                                                       119.250000
## 2012-10-24                                                       115.625000
## 2012-10-25                                                        66.180556
## 2012-10-26                                                        96.791667
## 2012-10-27                                                       102.902778
## 2012-10-28                                                       148.482639
## 2012-10-29                                                        90.371528
## 2012-10-30                                                       119.923611
## 2012-10-31                                                       130.440972
## 2012-11-01                                                       363.111111
## 2012-11-02                                                       120.364583
## 2012-11-03                                                       141.940972
## 2012-11-04                                                       363.111111
## 2012-11-05                                                       115.461806
## 2012-11-06                                                       109.461806
## 2012-11-07                                                       130.121528
## 2012-11-08                                                        79.979167
## 2012-11-09                                                       363.111111
## 2012-11-10                                                       363.111111
## 2012-11-11                                                       148.579861
## 2012-11-12                                                        97.326389
## 2012-11-13                                                       119.357639
## 2012-11-14                                                       363.111111
## 2012-11-15                                                         5.052083
## 2012-11-16                                                        84.444444
## 2012-11-17                                                       130.295139
## 2012-11-18                                                       141.548611
## 2012-11-19                                                       118.861111
## 2012-11-20                                                        63.927083
## 2012-11-21                                                       111.010417
## 2012-11-22                                                       173.010417
## 2012-11-23                                                       132.614583
## 2012-11-24                                                       122.250000
## 2012-11-25                                                       117.572917
## 2012-11-26                                                       143.479167
## 2012-11-27                                                       129.833333
## 2012-11-28                                                        79.618056
## 2012-11-29                                                        86.854167
## 2012-11-30                                                       363.111111
```

Median steps by day with the filled data.


```r
data.frame(with(activityFilled2,tapply(as.numeric(activityFilled2$steps),activityFilled2$date,median)))
```

```
##            with.activityFilled2..tapply.as.numeric.activityFilled2.steps...
## 2012-10-01                                                              352
## 2012-10-02                                                                1
## 2012-10-03                                                                1
## 2012-10-04                                                                1
## 2012-10-05                                                                1
## 2012-10-06                                                                1
## 2012-10-07                                                                1
## 2012-10-08                                                              352
## 2012-10-09                                                                1
## 2012-10-10                                                                1
## 2012-10-11                                                                1
## 2012-10-12                                                                1
## 2012-10-13                                                                1
## 2012-10-14                                                                1
## 2012-10-15                                                                1
## 2012-10-16                                                                1
## 2012-10-17                                                                1
## 2012-10-18                                                                1
## 2012-10-19                                                                1
## 2012-10-20                                                                1
## 2012-10-21                                                                1
## 2012-10-22                                                                1
## 2012-10-23                                                                1
## 2012-10-24                                                                1
## 2012-10-25                                                                1
## 2012-10-26                                                                1
## 2012-10-27                                                                1
## 2012-10-28                                                                1
## 2012-10-29                                                                1
## 2012-10-30                                                                1
## 2012-10-31                                                                1
## 2012-11-01                                                              352
## 2012-11-02                                                                1
## 2012-11-03                                                                1
## 2012-11-04                                                              352
## 2012-11-05                                                                1
## 2012-11-06                                                                1
## 2012-11-07                                                                1
## 2012-11-08                                                                1
## 2012-11-09                                                              352
## 2012-11-10                                                              352
## 2012-11-11                                                                1
## 2012-11-12                                                                1
## 2012-11-13                                                                1
## 2012-11-14                                                              352
## 2012-11-15                                                                1
## 2012-11-16                                                                1
## 2012-11-17                                                                1
## 2012-11-18                                                                1
## 2012-11-19                                                                1
## 2012-11-20                                                                1
## 2012-11-21                                                                1
## 2012-11-22                                                                1
## 2012-11-23                                                                1
## 2012-11-24                                                                1
## 2012-11-25                                                                1
## 2012-11-26                                                                1
## 2012-11-27                                                                1
## 2012-11-28                                                                1
## 2012-11-29                                                                1
## 2012-11-30                                                              352
```
RJOF: Do these values differ from the estimates from the first part of the assignment?

RJOF: What is the impact of imputing missing data on the estimates of the total daily number of steps?


## Are there differences in activity patterns between weekdays and weekends?

New variable indicating if is *weekday* or *weekend*


```r
activityFilled2$w <- ifelse((weekdays(activityFilled2$date) == "Saturday") | (weekdays(activityFilled2$date) == "Sunday"), "weekend", "weekday")
```

Subseting for *weekdays* and *weekends*


```r
activityWeekend <- activityFilled2[activityFilled2$w=='weekend',]
activityWeekday <- activityFilled2[activityFilled2$w=='weekday',]
```

Generating the mean by minutes interval.


```r
byMinuteIntervalWeekend <- with(activityWeekend,tapply(as.numeric(activityWeekend$steps),activityWeekend$interval,mean))

byMinuteIntervalWeekday <- with(activityWeekday,tapply(as.numeric(activityWeekday$steps),activityWeekday$interval,mean))
```

Ploting.


```r
par(mfcol=c(2,1))
plot(byMinuteIntervalWeekday,type='l',xlab='weekday')
plot(byMinuteIntervalWeekend,type='l',xlab='weekend')
```

![plot of chunk unnamed-chunk-17](figure/unnamed-chunk-17-1.png) 
