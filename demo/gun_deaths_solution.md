Exploring Gun Deaths in America
================
Benjamin Soltoff
October 3, 2017

Get the data
------------

``` r
library(tidyverse)    # load tidyverse packages, including ggplot2
```

    ## + ggplot2 2.2.1             Date: 2017-10-03
    ## + tibble  1.3.4                R: 3.4.1
    ## + tidyr   0.7.0               OS: macOS Sierra 10.12.6
    ## + readr   1.1.1              GUI: X11
    ## + purrr   0.2.3           Locale: en_US.UTF-8
    ## + dplyr   0.7.2.9000          TZ: America/Chicago
    ## + stringr 1.2.0           
    ## + forcats 0.2.0

    ## ── Conflicts ────────────────────────────────────────────────────

    ## * filter(),  from dplyr, masks stats::filter()
    ## * lag(),     from dplyr, masks stats::lag()

``` r
library(knitr)        # load functions for formatting tables

# get data from rcfss package
# install latest version if not already installed
# devtools::install_github("uc-cfss/rcfss")
library(rcfss)

# load the data
data("gun_deaths")
gun_deaths
```

    ## # A tibble: 100,798 x 10
    ##       id  year month       intent police   sex   age
    ##    <int> <int> <dbl>        <chr>  <int> <chr> <int>
    ##  1     1  2012     1      Suicide      0     M    34
    ##  2     2  2012     1      Suicide      0     F    21
    ##  3     3  2012     1      Suicide      0     M    60
    ##  4     4  2012     2      Suicide      0     M    64
    ##  5     5  2012     2      Suicide      0     M    31
    ##  6     6  2012     2      Suicide      0     M    17
    ##  7     7  2012     2 Undetermined      0     M    48
    ##  8     8  2012     3      Suicide      0     M    41
    ##  9     9  2012     2   Accidental      0     M    50
    ## 10    10  2012     2      Suicide      0     M    NA
    ## # ... with 100,788 more rows, and 3 more variables: race <chr>,
    ## #   place <chr>, education <fctr>

In what month do the most gun deaths occur?
-------------------------------------------

|  Month|  Number of Deaths|
|------:|-----------------:|
|      1|              8273|
|      2|              7093|
|      3|              8289|
|      4|              8455|
|      5|              8669|
|      6|              8677|
|      7|              8989|
|      8|              8783|
|      9|              8508|
|     10|              8406|
|     11|              8243|
|     12|              8413|

### With a bar chart

![](gun_deaths_solution_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-3-1.png)

### With a line chart

![](gun_deaths_solution_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-4-1.png)

What is the most common intent in gun deaths? Do most people killed by guns die in suicides, homicides, or accidental shootings?
--------------------------------------------------------------------------------------------------------------------------------

| Intent of Shooting |  Number of Deaths|
|:-------------------|-----------------:|
| Accidental         |              1639|
| Homicide           |             35176|
| Suicide            |             63175|
| Undetermined       |               807|
| NA                 |                 1|

![](gun_deaths_solution_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-5-1.png)

What is the average age of females killed by guns?
--------------------------------------------------

| Sex    |  Average Age|
|:-------|------------:|
| Female |        43.70|
| Male   |        43.88|

### Using a bar graph

![](gun_deaths_solution_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-7-1.png)

### Using a boxplot

    ## Warning: Removed 18 rows containing non-finite values (stat_boxplot).

![](gun_deaths_solution_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-8-1.png)

### Using a violin plot

    ## Warning: Removed 18 rows containing non-finite values (stat_ydensity).

![](gun_deaths_solution_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-9-1.png)

### Using a [letter-value boxplot](https://github.com/hadley/lvplot)

![](gun_deaths_solution_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-10-1.png)

How many white males with at least a high school education were killed by guns in 2012?
---------------------------------------------------------------------------------------

There were 15199 white males with at least a high school education killed by guns in 2012.

Which season of the year has the most gun deaths?
-------------------------------------------------

Assume that:

-   Winter = January-March
-   Spring = April-June
-   Summer = July-September
-   Fall = October-December

| Season |  Number of Deaths|
|:-------|-----------------:|
| Winter |             23655|
| Spring |             25801|
| Summer |             26280|
| Fall   |             25062|

![](gun_deaths_solution_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-12-1.png)

What is the relationship between race and intent?
=================================================

For example, are whites who are killed by guns more likely to die because of suicide or homicide? How does this compare to blacks and hispanics?

| Race of Victim                 | Intent of Shooting |  Number of Deaths|
|:-------------------------------|:-------------------|-----------------:|
| Asian/Pacific Islander         | Accidental         |                12|
| Asian/Pacific Islander         | Homicide           |               559|
| Asian/Pacific Islander         | Suicide            |               745|
| Asian/Pacific Islander         | Undetermined       |                10|
| Black                          | Accidental         |               328|
| Black                          | Homicide           |             19510|
| Black                          | Suicide            |              3332|
| Black                          | Undetermined       |               126|
| Hispanic                       | Accidental         |               145|
| Hispanic                       | Homicide           |              5634|
| Hispanic                       | Suicide            |              3171|
| Hispanic                       | Undetermined       |                72|
| Native American/Native Alaskan | Accidental         |                22|
| Native American/Native Alaskan | Homicide           |               326|
| Native American/Native Alaskan | Suicide            |               555|
| Native American/Native Alaskan | Undetermined       |                14|
| White                          | Accidental         |              1132|
| White                          | Homicide           |              9147|
| White                          | Suicide            |             55372|
| White                          | Undetermined       |               585|
| White                          | NA                 |                 1|

An okay graph
-------------

![](gun_deaths_solution_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-14-1.png)

A better graph
--------------

![](gun_deaths_solution_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-15-1.png)

Are police-involved gun deaths significantly different from other gun deaths? Assess the relationship between police involvement and age, police involvement and race, and the intersection of all three variables.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

    ## # A tibble: 172 x 3
    ##             police   age     n
    ##             <fctr> <int> <int>
    ##  1 Police involved    12     1
    ##  2 Police involved    13     1
    ##  3 Police involved    14     1
    ##  4 Police involved    15     5
    ##  5 Police involved    16     7
    ##  6 Police involved    17    13
    ##  7 Police involved    18    24
    ##  8 Police involved    19    28
    ##  9 Police involved    20    34
    ## 10 Police involved    21    43
    ## # ... with 162 more rows

    ## Warning: Removed 18 rows containing non-finite values (stat_boxplot).

![](gun_deaths_solution_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-16-1.png)

    ## # A tibble: 10 x 3
    ##                police                           race     n
    ##                <fctr>                          <chr> <int>
    ##  1    Police involved         Asian/Pacific Islander    30
    ##  2    Police involved                          Black   356
    ##  3    Police involved                       Hispanic   282
    ##  4    Police involved Native American/Native Alaskan    25
    ##  5    Police involved                          White   709
    ##  6 No police involved         Asian/Pacific Islander  1296
    ##  7 No police involved                          Black 22940
    ##  8 No police involved                       Hispanic  8740
    ##  9 No police involved Native American/Native Alaskan   892
    ## 10 No police involved                          White 65528

![](gun_deaths_solution_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-16-2.png)

    ## # A tibble: 671 x 4
    ##             police                   race   age     n
    ##             <fctr>                  <chr> <int> <int>
    ##  1 Police involved Asian/Pacific Islander    19     1
    ##  2 Police involved Asian/Pacific Islander    20     1
    ##  3 Police involved Asian/Pacific Islander    21     3
    ##  4 Police involved Asian/Pacific Islander    22     4
    ##  5 Police involved Asian/Pacific Islander    25     2
    ##  6 Police involved Asian/Pacific Islander    27     3
    ##  7 Police involved Asian/Pacific Islander    29     1
    ##  8 Police involved Asian/Pacific Islander    31     1
    ##  9 Police involved Asian/Pacific Islander    32     1
    ## 10 Police involved Asian/Pacific Islander    34     2
    ## # ... with 661 more rows

    ## Warning: Removed 18 rows containing non-finite values (stat_boxplot).

![](gun_deaths_solution_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-16-3.png)

    ## Warning: Removed 18 rows containing non-finite values (stat_boxplot).

![](gun_deaths_solution_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-16-4.png)

Session info
------------

``` r
devtools::session_info()
```

    ## Session info -------------------------------------------------------------

    ##  setting  value                       
    ##  version  R version 3.4.1 (2017-06-30)
    ##  system   x86_64, darwin15.6.0        
    ##  ui       X11                         
    ##  language (EN)                        
    ##  collate  en_US.UTF-8                 
    ##  tz       America/Chicago             
    ##  date     2017-10-03

    ## Packages -----------------------------------------------------------------

    ##  package    * version    date       source                              
    ##  assertthat   0.2.0      2017-04-11 CRAN (R 3.4.0)                      
    ##  backports    1.1.0      2017-05-22 CRAN (R 3.4.0)                      
    ##  base       * 3.4.1      2017-07-07 local                               
    ##  bindr        0.1        2016-11-13 CRAN (R 3.4.0)                      
    ##  bindrcpp   * 0.2        2017-06-17 CRAN (R 3.4.0)                      
    ##  boxes        0.0.0.9000 2017-07-19 Github (r-pkgs/boxes@03098dc)       
    ##  broom        0.4.2      2017-08-09 local                               
    ##  cellranger   1.1.0      2016-07-27 CRAN (R 3.4.0)                      
    ##  clisymbols   1.2.0      2017-05-21 cran (@1.2.0)                       
    ##  colorspace   1.3-2      2016-12-14 CRAN (R 3.4.0)                      
    ##  compiler     3.4.1      2017-07-07 local                               
    ##  crayon       1.3.2.9000 2017-07-19 Github (gaborcsardi/crayon@750190f) 
    ##  datasets   * 3.4.1      2017-07-07 local                               
    ##  devtools     1.13.3     2017-08-02 CRAN (R 3.4.1)                      
    ##  digest       0.6.12     2017-01-27 CRAN (R 3.4.0)                      
    ##  dplyr      * 0.7.2.9000 2017-08-10 Github (tidyverse/dplyr@65db321)    
    ##  evaluate     0.10.1     2017-06-24 CRAN (R 3.4.1)                      
    ##  forcats    * 0.2.0      2017-01-23 CRAN (R 3.4.0)                      
    ##  foreign      0.8-69     2017-06-22 CRAN (R 3.4.1)                      
    ##  ggplot2    * 2.2.1      2016-12-30 CRAN (R 3.4.0)                      
    ##  glue         1.1.1      2017-06-21 CRAN (R 3.4.1)                      
    ##  graphics   * 3.4.1      2017-07-07 local                               
    ##  grDevices  * 3.4.1      2017-07-07 local                               
    ##  grid         3.4.1      2017-07-07 local                               
    ##  gtable       0.2.0      2016-02-26 CRAN (R 3.4.0)                      
    ##  haven        1.1.0      2017-07-09 CRAN (R 3.4.1)                      
    ##  highr        0.6        2016-05-09 CRAN (R 3.4.0)                      
    ##  hms          0.3        2016-11-22 CRAN (R 3.4.0)                      
    ##  htmltools    0.3.6      2017-04-28 CRAN (R 3.4.0)                      
    ##  httr         1.3.1      2017-08-20 CRAN (R 3.4.1)                      
    ##  jsonlite     1.5        2017-06-01 CRAN (R 3.4.0)                      
    ##  knitr      * 1.17       2017-08-10 cran (@1.17)                        
    ##  labeling     0.3        2014-08-23 CRAN (R 3.4.0)                      
    ##  lattice      0.20-35    2017-03-25 CRAN (R 3.4.1)                      
    ##  lazyeval     0.2.0      2016-06-12 CRAN (R 3.4.0)                      
    ##  lubridate    1.6.0      2016-09-13 CRAN (R 3.4.0)                      
    ##  lvplot     * 0.2.0      2016-05-01 CRAN (R 3.4.0)                      
    ##  magrittr     1.5        2014-11-22 CRAN (R 3.4.0)                      
    ##  memoise      1.1.0      2017-04-21 CRAN (R 3.4.0)                      
    ##  methods    * 3.4.1      2017-07-07 local                               
    ##  mnormt       1.5-5      2016-10-15 CRAN (R 3.4.0)                      
    ##  modelr       0.1.1      2017-08-10 local                               
    ##  munsell      0.4.3      2016-02-13 CRAN (R 3.4.0)                      
    ##  nlme         3.1-131    2017-02-06 CRAN (R 3.4.1)                      
    ##  parallel     3.4.1      2017-07-07 local                               
    ##  pkgconfig    2.0.1      2017-03-21 CRAN (R 3.4.0)                      
    ##  plyr         1.8.4      2016-06-08 CRAN (R 3.4.0)                      
    ##  psych        1.7.5      2017-05-03 CRAN (R 3.4.1)                      
    ##  purrr      * 0.2.3      2017-08-02 CRAN (R 3.4.1)                      
    ##  R6           2.2.2      2017-06-17 CRAN (R 3.4.0)                      
    ##  rcfss      * 0.1.5      2017-07-31 local                               
    ##  Rcpp         0.12.12    2017-07-15 CRAN (R 3.4.1)                      
    ##  readr      * 1.1.1      2017-05-16 CRAN (R 3.4.0)                      
    ##  readxl       1.0.0      2017-04-18 CRAN (R 3.4.0)                      
    ##  reshape2     1.4.2      2016-10-22 CRAN (R 3.4.0)                      
    ##  rlang        0.1.2      2017-08-09 CRAN (R 3.4.1)                      
    ##  rmarkdown    1.6        2017-06-15 CRAN (R 3.4.0)                      
    ##  rprojroot    1.2        2017-01-16 CRAN (R 3.4.0)                      
    ##  rstudioapi   0.6        2016-06-27 CRAN (R 3.4.0)                      
    ##  rvest        0.3.2      2016-06-17 CRAN (R 3.4.0)                      
    ##  scales       0.4.1      2016-11-09 CRAN (R 3.4.0)                      
    ##  stats      * 3.4.1      2017-07-07 local                               
    ##  stringi      1.1.5      2017-04-07 CRAN (R 3.4.0)                      
    ##  stringr    * 1.2.0      2017-02-18 CRAN (R 3.4.0)                      
    ##  tibble     * 1.3.4      2017-08-22 CRAN (R 3.4.1)                      
    ##  tidyr      * 0.7.0      2017-08-16 CRAN (R 3.4.1)                      
    ##  tidyverse  * 1.1.1.9000 2017-07-19 Github (tidyverse/tidyverse@a028619)
    ##  tools        3.4.1      2017-07-07 local                               
    ##  utils      * 3.4.1      2017-07-07 local                               
    ##  withr        2.0.0      2017-07-28 CRAN (R 3.4.1)                      
    ##  xml2         1.1.1      2017-01-24 CRAN (R 3.4.0)                      
    ##  yaml         2.1.14     2016-11-12 CRAN (R 3.4.0)
