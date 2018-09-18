Homework01\_gapminder
================
Conrad Tsang
18/09/2018

Part of Homework 1 has asked us to create an R Markdown for exploration.
I decided to use Gapminder mainly because the plots at the end were
quite mesmerizing to look at. That and there’s *some* relevance to my
work in public health.

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

Then, we can plot Life Expectancy against the year, GDP/capita, and the
log of GDP/capita for some visualization.

``` r
plot(lifeExp ~ year, gapminder)
```

![](hw01_gapminder_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

``` r
plot(lifeExp ~ gdpPercap, gapminder)
```

![](hw01_gapminder_files/figure-gfm/unnamed-chunk-2-2.png)<!-- -->

``` r
plot(lifeExp ~ log(gdpPercap), gapminder)
```

![](hw01_gapminder_files/figure-gfm/unnamed-chunk-2-3.png)<!-- -->

Lastly, I just thought it was cool how ggplot could be used to create
some gorgeous graphics, although I actually do not truly understand the
economic significance behind it – just very pretty
    :)

``` r
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────────────────────────── tidyverse 1.2.1 ──

    ## ✔ ggplot2 3.0.0     ✔ purrr   0.2.5
    ## ✔ tibble  1.4.2     ✔ dplyr   0.7.6
    ## ✔ tidyr   0.8.1     ✔ stringr 1.3.1
    ## ✔ readr   1.1.1     ✔ forcats 0.3.0

    ## ── Conflicts ────────────────────────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
p <- ggplot(filter(gapminder, continent != "Oceania"),
            aes(x = gdpPercap, y = lifeExp))
p <- p + scale_x_log10()
p + geom_point(aes(color = continent))
```

![](hw01_gapminder_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->
