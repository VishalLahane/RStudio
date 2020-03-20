What is R?
R is a lanaguage and environment for statistical computing and graphics.

Who uses R?
- People deal with Data.
   - Spreadsheet Users.
   - Programmers.
   - Statisticians.
   - Data Scientists.
   
```   
> require('ggplot2')
> data(package='ggplot2')
> help("diamonds")
```

# diamonds
```
> diamonds

# A tibble: 53,940 x 10
   carat cut   color clarity depth table price     x
   <dbl> <ord> <ord> <ord>   <dbl> <dbl> <int> <dbl>
 1 0.23  Ideal E     SI2      61.5    55   326  3.95
 2 0.21  Prem~ E     SI1      59.8    61   326  3.89
 3 0.23  Good  E     VS1      56.9    65   327  4.05
 4 0.290 Prem~ I     VS2      62.4    58   334  4.2 
 5 0.31  Good  J     SI2      63.3    58   335  4.34
 6 0.24  Very~ J     VVS2     62.8    57   336  3.94
 7 0.24  Very~ I     VVS1     62.3    57   336  3.95
 8 0.26  Very~ H     SI1      61.9    55   337  4.07
 9 0.22  Fair  E     VS2      65.1    61   337  3.87
10 0.23  Very~ H     VS1      59.4    61   338  4   
# ... with 53,930 more rows, and 2 more variables:
#   y <dbl>, z <dbl>
```

#head
```
head(diamonds)
# A tibble: 6 x 10
  carat cut   color clarity depth table price     x     y
  <dbl> <ord> <ord> <ord>   <dbl> <dbl> <int> <dbl> <dbl>
1 0.23  Ideal E     SI2      61.5    55   326  3.95  3.98
2 0.21  Prem~ E     SI1      59.8    61   326  3.89  3.84
3 0.23  Good  E     VS1      56.9    65   327  4.05  4.07
4 0.290 Prem~ I     VS2      62.4    58   334  4.2   4.23
5 0.31  Good  J     SI2      63.3    58   335  4.34  4.35
6 0.24  Very~ J     VVS2     62.8    57   336  3.94  3.96
# ... with 1 more variable: z <dbl>
```

#summary
```
> summary(diamonds)
     carat               cut        color    
 Min.   :0.2000   Fair     : 1610   D: 6775  
 1st Qu.:0.4000   Good     : 4906   E: 9797  
 Median :0.7000   Very Good:12082   F: 9542  
 Mean   :0.7979   Premium  :13791   G:11292  
 3rd Qu.:1.0400   Ideal    :21551   H: 8304  
 Max.   :5.0100                     I: 5422  
                                    J: 2808  
    clarity          depth           table      
 SI1    :13065   Min.   :43.00   Min.   :43.00  
 VS2    :12258   1st Qu.:61.00   1st Qu.:56.00  
 SI2    : 9194   Median :61.80   Median :57.00  
 VS1    : 8171   Mean   :61.75   Mean   :57.46  
 VVS2   : 5066   3rd Qu.:62.50   3rd Qu.:59.00  
 VVS1   : 3655   Max.   :79.00   Max.   :95.00  
 (Other): 2531                                  
     price             x                y         
 Min.   :  326   Min.   : 0.000   Min.   : 0.000  
 1st Qu.:  950   1st Qu.: 4.710   1st Qu.: 4.720  
 Median : 2401   Median : 5.700   Median : 5.710  
 Mean   : 3933   Mean   : 5.731   Mean   : 5.735  
 3rd Qu.: 5324   3rd Qu.: 6.540   3rd Qu.: 6.540  
 Max.   :18823   Max.   :10.740   Max.   :58.900  
                                                  
       z         
 Min.   : 0.000  
 1st Qu.: 2.910  
 Median : 3.530  
 Mean   : 3.539  
 3rd Qu.: 4.040  
 Max.   :31.800  
```

#subset
```
> subset(diamonds,cut %in% 'Fair')
# A tibble: 1,610 x 10
   carat cut   color clarity depth table price     x
   <dbl> <ord> <ord> <ord>   <dbl> <dbl> <int> <dbl>
 1  0.22 Fair  E     VS2      65.1    61   337  3.87
 2  0.86 Fair  E     SI2      55.1    69  2757  6.45
 3  0.96 Fair  F     SI2      66.3    62  2759  6.27
 4  0.7  Fair  F     VS2      64.5    57  2762  5.57
 5  0.7  Fair  F     VS2      65.3    55  2762  5.63
 6  0.91 Fair  H     SI2      64.4    57  2763  6.11
 7  0.91 Fair  H     SI2      65.7    60  2763  6.03
 8  0.98 Fair  H     SI2      67.9    60  2777  6.05
 9  0.84 Fair  G     SI1      55.1    67  2782  6.39
10  1.01 Fair  E     I1       64.5    58  2788  6.29
# ... with 1,600 more rows, and 2 more variables:
#   y <dbl>, z <dbl>
```

#subset
```
> subset(diamonds,cut %in% 'Fair'& color %in% 'J' & price<1000)
# A tibble: 4 x 10
  carat cut   color clarity depth table price     x     y
  <dbl> <ord> <ord> <ord>   <dbl> <dbl> <int> <dbl> <dbl>
1  0.3  Fair  J     VS2      64.8    58   416  4.24  4.16
2  0.5  Fair  J     VS1      66.8    57   949  4.89  4.84
3  0.51 Fair  J     VS2      65.3    55   996  4.97  4.96
4  0.34 Fair  J     SI1      64.5    57   497  4.38  4.36
# ... with 1 more variable: z <dbl>
```

#subset
```
> subset(diamonds,cut %in% 'Fair'& color %in% 'J' & price<1000)$price
[1] 416 949 996 497
```

#mean
```
> mean(subset(diamonds,cut %in% 'Fair'& color %in% 'J' & price<1000)$price)
[1] 714.5
```
