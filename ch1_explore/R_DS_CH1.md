R Data Science Chapter 1
================
Shaun Jackson

-   [Data visualisation](#data-visualisation)
    -   [Data we are working with](#data-we-are-working-with)
    -   [Plotting `mpg` by putting `displ` on the x-axis and `hwy` on the y-axis:](#plotting-mpg-by-putting-displ-on-the-x-axis-and-hwy-on-the-y-axis)

The below notes are from Hadley Wickham's R for Data Science. This is a summary of my main takeaways from the sections that I thought were the most important

Data visualisation
==================

-   The section of the book teaches us how to use ggplot2. In order to make sure all the required packages are available:

``` r
library(tidyverse)
```

Data we are working with
------------------------

We are using the **mpg** dataframe that is found within ggplot2.

``` r
mpg
```

    ## # A tibble: 234 x 11
    ##    manufacturer model displ  year   cyl trans drv     cty   hwy fl    cla…
    ##    <chr>        <chr> <dbl> <int> <int> <chr> <chr> <int> <int> <chr> <ch>
    ##  1 audi         a4      1.8  1999     4 auto… f        18    29 p     com…
    ##  2 audi         a4      1.8  1999     4 manu… f        21    29 p     com…
    ##  3 audi         a4      2    2008     4 manu… f        20    31 p     com…
    ##  4 audi         a4      2    2008     4 auto… f        21    30 p     com…
    ##  5 audi         a4      2.8  1999     6 auto… f        16    26 p     com…
    ##  6 audi         a4      2.8  1999     6 manu… f        18    26 p     com…
    ##  7 audi         a4      3.1  2008     6 auto… f        18    27 p     com…
    ##  8 audi         a4 q…   1.8  1999     4 manu… 4        18    26 p     com…
    ##  9 audi         a4 q…   1.8  1999     4 auto… 4        16    25 p     com…
    ## 10 audi         a4 q…   2    2008     4 manu… 4        20    28 p     com…
    ## # ... with 224 more rows

-   Note: mpg is a tibble. Tibbles are

> "a modern reimagining of the data.frame." "Tibbles are data.frames that are lazy and surly: they do less" "and complain more." - from <https://tibble.tidyverse.org>

Plotting `mpg` by putting `displ` on the x-axis and `hwy` on the y-axis:
------------------------------------------------------------------------

``` r
ggplot(data = mpg) +
  geom_point(mapping = aes(x = displ, y = hwy))
```

![](R_DS_CH1_files/figure-markdown_github/unnamed-chunk-3-1.png)

In the above plot,

-   `geom_point()` produces points on the graph.
-   Define x and y axes by setting the x and y parameters within the aesthetic function `aes()` to `x = displ` and `y = hwy`.
