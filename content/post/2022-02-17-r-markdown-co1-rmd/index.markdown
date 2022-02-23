---
title: R Markdown CO1 RMD
author: R package build
date: '2022-02-17'
slug: r-markdown-co1-rmd
categories: []
tags: []
---


```r
library(datasets)
data(iris)
#load packages
pkgs <- c("rstatix","emmeans","psych","tidyr","tidyverse","psych","dplyr","ggplot2","lm.beta","car","Hmisc","skimr","janitor")
lapply(pkgs, library, character.only = TRUE)
setwd("/Users/aman/OneDrive/Junior2/git/website_AmanShaan/content/post/2022-02-17-r-markdown-co1-rmd")
```


# Intro


## Code Chunks


* Most common
* Use ` (backquote) not ' (apostophe)


```r
#Sum of 2 + 2
2+2
```

```
## [1] 4
```

```r
#Average Sepal Length
mean(iris$Sepal.Length)
```

```
## [1] 5.843333
```
* When exporting you will see both of these outputs, but will only see the last one within rmd.  
* You can also click the x on the upper right corner of the output to remove the output.


```r
#Levels of Species
unique(iris$Species)
```

```
## [1] setosa     versicolor virginica 
## Levels: setosa versicolor virginica
```

## Inline Code
Two plus two equals 4.  
The average Sepal Length is 5.8433333.  
The three levels of Species are setosa, versicolor, virginica.  

# Basics

## Text

Plain text  
End a line with two spaces to start a new paragraph.  
*italics* and _italics_  
**bold** and __bold__  
superscript^2^  
~~strikethrough~~  
[link](www.rstudio.com)  

## Headers (level 2)

```r
Make sure to leave a space between the # and your text  
# Header 1
## Header 2
```
### Header 3
#### Header 4
##### Header 5
###### Header 6

## Symbols
endash: --  
emdash: ---  
ellipsis: ...  
inline equation: `\(A = \pi*r^{2}\)`  

horizontal rule (or slide break):  

***

## Formatting

> block quote  


* unordered list  
* item 2  
  + sub-item 1  (one tab)
  + sub-item 2  (one tab)


1. ordered list  
2. item 2
    + sub-item 1 (two tabs)
    + sub-item 2 (two tabs)
  
First Header | Second Header
------------- | -------------
Table Cell 1 | Cell 2
Cell 3 | Cell 4 

## Date

```r
#Add this to date so that today's date is printed whenever doc is knitted
title: "Rmarkdown_Intro"
author: "Aman Shaan"
date: "`2/17/2021`"
```

>Most of this information was taken from this useful [cheatsheet](https://www.rstudio.com/wp-content/uploads/2015/02/rmarkdown-cheatsheet.pdf)

# Code Specifications

## Display Code



```
##   Sepal.Length    Sepal.Width     Petal.Length    Petal.Width   
##  Min.   :4.300   Min.   :2.000   Min.   :1.000   Min.   :0.100  
##  1st Qu.:5.100   1st Qu.:2.800   1st Qu.:1.600   1st Qu.:0.300  
##  Median :5.800   Median :3.000   Median :4.350   Median :1.300  
##  Mean   :5.843   Mean   :3.057   Mean   :3.758   Mean   :1.199  
##  3rd Qu.:6.400   3rd Qu.:3.300   3rd Qu.:5.100   3rd Qu.:1.800  
##  Max.   :7.900   Max.   :4.400   Max.   :6.900   Max.   :2.500  
##        Species  
##  setosa    :50  
##  versicolor:50  
##  virginica :50  
##                 
##                 
## 
```

## Display Warnings

```r
warning=TRUE: Whether to display warnings
```

### With Warning

```r
data <- data.frame(x = 1:5,         # Create example data
                   y = 1:5)
ggp <- ggplot(data, aes(x, y)) +    # Create ggplot2 with default axis limits
  geom_point()

ggp +                               # Modify axis limits
  scale_x_continuous(limits = c(2, 5))
```

```
## Warning: Removed 1 rows containing missing values (geom_point).
```

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-10-1.png" width="672" />
