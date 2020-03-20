```
> require(ggplot2)
> data(package='ggplot2')
> help(mpg)
> summary(diamonds$price)
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    326     950    2401    3933    5324   18823 
	
> dim(diamondsWithPrice)
[1] 29733    10

> g <- ggplot(diamondsWithPrice, aes(x=table,y=price))
> 
> g <- g + geom_point(aes(color=color))
> g
> options( scipen = 20)
> library(scales)
> g
> g <- g + scale_y_continuous(labels =  comma)
> g

```
