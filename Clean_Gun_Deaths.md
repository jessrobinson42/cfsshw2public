Exploring Gun Deaths in America
================
By [Jessica Robinson](https://github.com/jessrobinson42/hw01/blob/master/README.md)

Get the data 
------------

    ## ── Attaching packages ─────────────────────────── tidyverse 1.2.1 ──

    ## ✔ ggplot2 3.0.0     ✔ purrr   0.2.5
    ## ✔ tibble  1.4.2     ✔ dplyr   0.7.6
    ## ✔ tidyr   0.8.1     ✔ stringr 1.3.1
    ## ✔ readr   1.1.1     ✔ forcats 0.3.0

    ## Warning: package 'dplyr' was built under R version 3.5.1

    ## ── Conflicts ────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

Generate a data frame that summarizes the number of gun deaths per month.
-------------------------------------------------------------------------

### Print the data frame as a formatted `kable()` table.

| Month |  Number of Gun Deaths|
|:------|---------------------:|
| Jan   |                  8273|
| Feb   |                  7093|
| Mar   |                  8289|
| Apr   |                  8455|
| May   |                  8669|
| Jun   |                  8677|
| Jul   |                  8989|
| Aug   |                  8783|
| Sep   |                  8508|
| Oct   |                  8406|
| Nov   |                  8243|
| Dec   |                  8413|

### Generate a bar chart with human-readable labels on the x-axis. That is, each month should be labeled "Jan", "Feb", "Mar" (full or abbreviated month names are fine), not `1`, `2`, `3`.

![](Clean_Gun_Deaths_files/figure-markdown_github/unnamed-chunk-3-1.png)

Generate a bar chart that identifies the number of gun deaths associated with each type of intent cause of death. The bars should be sorted from highest to lowest values.
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

![](Clean_Gun_Deaths_files/figure-markdown_github/unnamed-chunk-4-1.png)

Suicide is the most common form of gun death, followed by homicide.

Generate a boxplot visualizing the age of gun death victims, by sex. Print the average age of female gun death victims.
-----------------------------------------------------------------------------------------------------------------------

    ## Warning: Removed 18 rows containing non-finite values (stat_boxplot).

![](Clean_Gun_Deaths_files/figure-markdown_github/unnamed-chunk-5-1.png)

Men and women are killed at approximately the same age.

|  Average Age of Female Gun Death Victims|
|----------------------------------------:|
|                                 43.69507|

On average, female gun deaths victims are **43.7** years old.

How many white males with at least a high school education were killed by guns in 2012?
---------------------------------------------------------------------------------------

|      n|
|------:|
|  15199|

There were **15199** white males with at least a high school education killed by guns in 2012.

Which season of the year has the most gun deaths?
-------------------------------------------------

Assume that:

-   Winter = January-March
-   Spring = April-June
-   Summer = July-September
-   Fall = October-December

| Season |  Number of Gun Deaths|
|:-------|---------------------:|
| Winter |                 23655|
| Spring |                 25801|
| Summer |                 26280|
| Fall   |                 25062|

![](Clean_Gun_Deaths_files/figure-markdown_github/unnamed-chunk-9-1.png)

Are whites who are killed by guns more likely to die because of suicide or homicide? How does this compare to blacks and hispanics?
===================================================================================================================================

![](Clean_Gun_Deaths_files/figure-markdown_github/unnamed-chunk-10-1.png)

White are more likely to die by because suicide than homicide. In comparison, blacks and hispanics are both more likely to die by homicide than suicide.

Are police-involved gun deaths significantly different from other gun deaths? Assess the relationship between police involvement and age, police involvement and race, and the intersection of all three variables.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

![](Clean_Gun_Deaths_files/figure-markdown_github/unnamed-chunk-11-1.png)

Police involved deaths involve Black and Hispanic victims at a greater rate than non-police involved deaths.

    ## Warning: Removed 18 rows containing non-finite values (stat_boxplot).

![](Clean_Gun_Deaths_files/figure-markdown_github/unnamed-chunk-12-1.png)

Police involved deaths generally involve younger victims than non-police involved deaths.

    ## Warning: Removed 18 rows containing non-finite values (stat_boxplot).

![](Clean_Gun_Deaths_files/figure-markdown_github/unnamed-chunk-13-1.png)

Police involved deaths are most signficantly different in age from non-police involved in deaths for White victims. For non-White vicitms, the age of victims does not signficantly vary between police-involved and non-police involved deaths.

Session info
------------

    ## ─ Session info ──────────────────────────────────────────────────────────
    ##  setting  value                       
    ##  version  R version 3.5.0 (2018-04-23)
    ##  os       OS X El Capitan 10.11.6     
    ##  system   x86_64, darwin15.6.0        
    ##  ui       X11                         
    ##  language (EN)                        
    ##  collate  en_US.UTF-8                 
    ##  ctype    en_US.UTF-8                 
    ##  tz       America/Chicago             
    ##  date     2019-04-14                  
    ## 
    ## ─ Packages ──────────────────────────────────────────────────────────────
    ##  package     * version date       lib source                        
    ##  assertthat    0.2.0   2017-04-11 [1] CRAN (R 3.5.0)                
    ##  backports     1.1.2   2017-12-13 [1] CRAN (R 3.5.0)                
    ##  base64enc     0.1-3   2015-07-28 [1] CRAN (R 3.5.0)                
    ##  bindr         0.1.1   2018-03-13 [1] CRAN (R 3.5.0)                
    ##  bindrcpp    * 0.2.2   2018-03-29 [1] CRAN (R 3.5.0)                
    ##  broom         0.5.0   2018-07-17 [1] CRAN (R 3.5.0)                
    ##  callr         3.0.0   2018-08-24 [1] CRAN (R 3.5.0)                
    ##  cellranger    1.1.0   2016-07-27 [1] CRAN (R 3.5.0)                
    ##  cli           1.0.0   2017-11-05 [1] CRAN (R 3.5.0)                
    ##  colorspace    1.3-2   2016-12-14 [1] CRAN (R 3.5.0)                
    ##  crayon        1.3.4   2017-09-16 [1] CRAN (R 3.5.0)                
    ##  desc          1.2.0   2018-05-01 [1] CRAN (R 3.5.0)                
    ##  devtools      2.0.1   2018-10-26 [1] CRAN (R 3.5.0)                
    ##  digest        0.6.15  2018-01-28 [1] CRAN (R 3.5.0)                
    ##  dplyr       * 0.7.6   2018-06-29 [1] CRAN (R 3.5.1)                
    ##  evaluate      0.10.1  2017-06-24 [1] CRAN (R 3.5.0)                
    ##  forcats     * 0.3.0   2018-02-19 [1] CRAN (R 3.5.0)                
    ##  fs            1.2.6   2018-08-23 [1] CRAN (R 3.5.0)                
    ##  ggplot2     * 3.0.0   2018-07-03 [1] CRAN (R 3.5.0)                
    ##  glue          1.2.0   2017-10-29 [1] CRAN (R 3.5.0)                
    ##  gtable        0.2.0   2016-02-26 [1] CRAN (R 3.5.0)                
    ##  haven         1.1.2   2018-06-27 [1] CRAN (R 3.5.0)                
    ##  highr         0.7     2018-06-09 [1] CRAN (R 3.5.0)                
    ##  hms           0.4.2   2018-03-10 [1] CRAN (R 3.5.0)                
    ##  htmltools     0.3.6   2017-04-28 [1] CRAN (R 3.5.0)                
    ##  httr          1.3.1   2017-08-20 [1] CRAN (R 3.5.0)                
    ##  jsonlite      1.5     2017-06-01 [1] CRAN (R 3.5.0)                
    ##  knitr       * 1.20    2018-02-20 [1] CRAN (R 3.5.0)                
    ##  labeling      0.3     2014-08-23 [1] CRAN (R 3.5.0)                
    ##  lattice       0.20-35 2017-03-25 [1] CRAN (R 3.5.0)                
    ##  lazyeval      0.2.1   2017-10-29 [1] CRAN (R 3.5.0)                
    ##  lubridate     1.7.4   2018-04-11 [1] CRAN (R 3.5.0)                
    ##  magrittr      1.5     2014-11-22 [1] CRAN (R 3.5.0)                
    ##  memoise       1.1.0   2017-04-21 [1] CRAN (R 3.5.0)                
    ##  modelr        0.1.2   2018-05-11 [1] CRAN (R 3.5.0)                
    ##  munsell       0.5.0   2018-06-12 [1] CRAN (R 3.5.0)                
    ##  nlme          3.1-137 2018-04-07 [1] CRAN (R 3.5.0)                
    ##  pillar        1.2.3   2018-05-25 [1] CRAN (R 3.5.0)                
    ##  pkgbuild      1.0.2   2018-10-16 [1] CRAN (R 3.5.0)                
    ##  pkgconfig     2.0.1   2017-03-21 [1] CRAN (R 3.5.0)                
    ##  pkgload       1.0.2   2018-10-29 [1] CRAN (R 3.5.0)                
    ##  plyr          1.8.4   2016-06-08 [1] CRAN (R 3.5.0)                
    ##  prettyunits   1.0.2   2015-07-13 [1] CRAN (R 3.5.0)                
    ##  processx      3.2.0   2018-08-16 [1] CRAN (R 3.5.0)                
    ##  ps            1.1.0   2018-08-10 [1] CRAN (R 3.5.0)                
    ##  purrr       * 0.2.5   2018-05-29 [1] CRAN (R 3.5.0)                
    ##  R6            2.2.2   2017-06-17 [1] CRAN (R 3.5.0)                
    ##  rcfss       * 0.1.5   2019-04-08 [1] Github (uc-cfss/rcfss@90a1b9d)
    ##  Rcpp          0.12.17 2018-05-18 [1] CRAN (R 3.5.0)                
    ##  readr       * 1.1.1   2017-05-16 [1] CRAN (R 3.5.0)                
    ##  readxl        1.1.0   2018-04-20 [1] CRAN (R 3.5.0)                
    ##  remotes       2.0.2   2018-10-30 [1] CRAN (R 3.5.0)                
    ##  rlang         0.3.0.1 2018-10-25 [1] CRAN (R 3.5.0)                
    ##  rmarkdown     1.10    2018-06-11 [1] CRAN (R 3.5.0)                
    ##  rprojroot     1.3-2   2018-01-03 [1] CRAN (R 3.5.0)                
    ##  rstudioapi    0.8     2018-10-02 [1] CRAN (R 3.5.0)                
    ##  rvest         0.3.2   2016-06-17 [1] CRAN (R 3.5.0)                
    ##  scales        0.5.0   2017-08-24 [1] CRAN (R 3.5.0)                
    ##  sessioninfo   1.1.1   2018-11-05 [1] CRAN (R 3.5.0)                
    ##  stringi       1.2.3   2018-06-12 [1] CRAN (R 3.5.0)                
    ##  stringr     * 1.3.1   2018-05-10 [1] CRAN (R 3.5.0)                
    ##  testthat      2.0.0   2017-12-13 [1] CRAN (R 3.5.0)                
    ##  tibble      * 1.4.2   2018-01-22 [1] CRAN (R 3.5.0)                
    ##  tidyr       * 0.8.1   2018-05-18 [1] CRAN (R 3.5.0)                
    ##  tidyselect    0.2.4   2018-02-26 [1] CRAN (R 3.5.0)                
    ##  tidyverse   * 1.2.1   2017-11-14 [1] CRAN (R 3.5.0)                
    ##  usethis       1.4.0   2018-08-14 [1] CRAN (R 3.5.0)                
    ##  withr         2.1.2   2018-03-15 [1] CRAN (R 3.5.0)                
    ##  xml2          1.2.0   2018-01-24 [1] CRAN (R 3.5.0)                
    ##  yaml          2.1.19  2018-05-01 [1] CRAN (R 3.5.0)                
    ## 
    ## [1] /Library/Frameworks/R.framework/Versions/3.5/Resources/library
