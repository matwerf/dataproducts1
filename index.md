---
title       : How many days old are you?
subtitle    : Data science slidfy/shiny project
author      : C S S
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## What can you calculate

The program provides three options:

1. How many days have passed between when men walked on the moon and the date in question (inclusive).
2. What day is 100 days later?
3. Or you can calculate how many days you've been alive - or between two points inclusive.

--- .class #id 

## Set-up

- Entering the first date in question into the first date box, adds the selected date into the date variable, (the default is Jan 20, 2014 if it is not changed).



- The next step is to pick an option, there are three choices provided as Radio Buttons.

- If choice 3 is picked, a new date can be selected (the default is todays date).

- Then the submit button should be clicked to calculate the number of days difference or the new date.



--- .class #id

## Options
Selecting option #1 calculates the days between the selected date and the date of the first man on the moon (July 16, 1969).

The data is then passed through the following function.

```r
daysbetween <- function(date1,date2) {
  if(date2 > date1) (date2-date1 +1)
  else if(date2 < date1) ((date1-date2 +1)*-1)
  else if(date2 == date1) 1
}
```
Giving an output of the inclusive time difference.

```r
daysbetween(date1,as.Date("1969-07-16"))
```

```
## Time difference of -16260 days
```

--- .class #id

## How many days have you been alive?
Selecting option#2 calcultes the date that would be 100 days later that the starting date inclusive.

```r
date1 + 99
```

```
## [1] "2014-04-29"
```
Selecting option #3 calculates the days between the selected date and a second date - by using your birthday for the inital date and todays date as the second date (the default), the number of days you have been alive can be calculated.

Giving an output of the inclusive time difference.

```r
daysbetween(date1,date2)
```

```
## Time difference of 275 days
```


