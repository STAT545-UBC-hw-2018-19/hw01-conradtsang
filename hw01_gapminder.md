Homework01\_gapminder
================
Conrad Tsang
18/09/2018

Part of Homework 1 has asked us to create an R Markdown for exploration.
I decided to use Gapminder mainly because the plots at the end were
quite mesmerizing to look at. That and there’s *some* relevance to my
work in public health, so I’m using this as an opportunity to explore
the basics of looking at data if I was thinking about someday analyzing
this..

First we can look at some of the summary statistics of Gapminder.

``` r
library(gapminder)
summary(gapminder)
```

    ##         country        continent        year         lifeExp     
    ##  Afghanistan:  12   Africa  :624   Min.   :1952   Min.   :23.60  
    ##  Albania    :  12   Americas:300   1st Qu.:1966   1st Qu.:48.20  
    ##  Algeria    :  12   Asia    :396   Median :1980   Median :60.71  
    ##  Angola     :  12   Europe  :360   Mean   :1980   Mean   :59.47  
    ##  Argentina  :  12   Oceania : 24   3rd Qu.:1993   3rd Qu.:70.85  
    ##  Australia  :  12                  Max.   :2007   Max.   :82.60  
    ##  (Other)    :1632                                                
    ##       pop              gdpPercap       
    ##  Min.   :6.001e+04   Min.   :   241.2  
    ##  1st Qu.:2.794e+06   1st Qu.:  1202.1  
    ##  Median :7.024e+06   Median :  3531.8  
    ##  Mean   :2.960e+07   Mean   :  7215.3  
    ##  3rd Qu.:1.959e+07   3rd Qu.:  9325.5  
    ##  Max.   :1.319e+09   Max.   :113523.1  
    ## 

In particular, I’d need to know how many rows and columns there are
without needing to add or count the above.

``` r
nrow(gapminder)
```

    ## [1] 1704

``` r
ncol(gapminder)
```

    ## [1] 6

Let’s just make sure the data contains the most important country:
Canada\!

``` r
attach(gapminder)
any(country == "Canada")
```

    ## [1] TRUE

Phew\! How many countries are there in gapminder anyway?

``` r
length(levels(country))
```

    ## [1] 142

Lastly, just wanted to get a sense if there was data missing.

``` r
any(is.na(gapminder))
```

    ## [1] FALSE

That took more trial-and-error trying to look up some of the later
things above. I’m glad we’ll eventually start to learn how to do this\!
