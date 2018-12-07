R Scripts
================
Tarun Chaturvedi
October 31, 2018

-   [**Team Name: *Mavs***](#team-name-mavs)
    -   [Contributors](#contributors)

------------------------------------------------------------------------

**Team Name: *Mavs***
---------------------

-   **Team Project: Hurricane Island for scallop Growth**
-   **Dataset: Scallop Growth dataset**

We have addressed the main research questions.

1.  Find the mean of Scallops in each region
2.  Find the stadard deviation of scallop size which will be used for scallop growth analysis
3.  Query: Group by the closure and outputs the mean, by doing some we can find out with closure had better perfomance
4.  Missing data for 2017 SpatData were deleted, because they were not usefull for the analysis

``` r
spatbag <- read.csv("Spat_Data.csv", header = TRUE, stringsAsFactors = FALSE)
```

``` r
library(dplyr)
```

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

``` r
closurezone <- split(spatbag, spatbag$Closure.zone)
```

``` r
spatbag%>%
  group_by(Closure.zone)%>%
  summarise(Mean=mean(Scallop.size..mm.), Max=max(Scallop.size..mm.), Min=min(Scallop.size..mm.), Sum=sum(Total.Scallops))
```

    ## # A tibble: 3 x 5
    ##   Closure.zone  Mean   Max   Min   Sum
    ##   <chr>        <dbl> <dbl> <dbl> <int>
    ## 1 closure       6.92    14     1   671
    ## 2 north         6.89    15     2   186
    ## 3 south         7.97    15     3   212

``` r
Area <- split(spatbag, spatbag$AREA)
```

``` r
sum(Area$MR$Total.Scallops)
```

    ## [1] 972

``` r
sum(Area$VC$Total.Scallops)
```

    ## [1] 97

``` r
Year2015 <- read.csv("2015 SpatData.csv", header = TRUE, stringsAsFactors = FALSE)
```

``` r
Year2016 <- read.csv("2016 SpatData.csv", header = TRUE, stringsAsFactors = FALSE)
```

``` r
Year2017 <- read.csv("2017 SpatData.csv", header = TRUE, stringsAsFactors = FALSE)
```

``` r
MR15 <- split(Year2015, Year2015$Area)
```

``` r
MR16 <- split(Year2016, Year2016$Area)
```

``` r
MR17 <- split(Year2017, Year2017$Area)
```

``` r
sum(MR15$MR$Scallop.count)
```

    ## [1] 16125

``` r
sum(MR16$MR$Scallop.count)
```

    ## [1] 3560

``` r
sum(MR17$MR$Scallop.count)
```

    ## [1] 2444

``` r
Year2017 <- read.csv("2017 SpatData.csv", header = TRUE, stringsAsFactors = FALSE)
```

### Contributors

1.  Bobodzhon Isamov - R Script and documentation proofreading
2.  Tarun Chaturvedi - R Script and further data cleaning
3.  Srishty Nayak - Analysis questions and documentation
