R Scripts
================
Tarun Chaturvedi
October 31, 2018

-   [R Markdown](#r-markdown)
-   [**Team Name: *Mavs***](#team-name-mavs)
    -   [Read the csv file](#read-the-csv-file)
    -   [Create a closure zones](#create-a-closure-zones)
    -   [Group by closure zones](#group-by-closure-zones)
    -   [Split the spatbag by areas](#split-the-spatbag-by-areas)
    -   [get the total count of scallops in MR area](#get-the-total-count-of-scallops-in-mr-area)
    -   [get the total count of scallops in VC area](#get-the-total-count-of-scallops-in-vc-area)
    -   [open 2015 csv file](#open-2015-csv-file)
    -   [open 2016 csv file](#open-2016-csv-file)
    -   [open 2017 csv file](#open-2017-csv-file)
    -   [Split the 2015 by the area](#split-the-2015-by-the-area)
    -   [Split the 2016 by the area](#split-the-2016-by-the-area)
    -   [Split the 2017 by the area](#split-the-2017-by-the-area)
    -   [get the sum of scallops in MR for 2015](#get-the-sum-of-scallops-in-mr-for-2015)
    -   [get the Sum of scallops in MR for 2016](#get-the-sum-of-scallops-in-mr-for-2016)
    -   [get the sum of scallops in MR for 2017](#get-the-sum-of-scallops-in-mr-for-2017)
    -   [Contributors](#contributors)

------------------------------------------------------------------------

R Markdown
----------

**Team Name: *Mavs***
---------------------

-   **Team Project: Hurricane Island for scallop Growth**
-   **Dataset: Scallop Growth dataset**

We have addressed the main research questions.

1.  Find the mean of Scallops in each region
2.  Find the stadard deviation of scallop size which will be used for scallop growth analysis
3.  Query: Group by the closure and outputs the mean, by doing some we can find out with closure had better perfomance
4.  Missing data for 2017 SpatData were deleted, because they were not usefull for the analysis

#### Read the csv file

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

#### Create a closure zones

``` r
closurezone <- split(spatbag, spatbag$Closure.zone)
```

#### Group by closure zones

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

#### Split the spatbag by areas

``` r
Area <- split(spatbag, spatbag$AREA)
```

#### get the total count of scallops in MR area

``` r
sum(Area$MR$Total.Scallops)
```

    ## [1] 972

#### get the total count of scallops in VC area

``` r
sum(Area$VC$Total.Scallops)
```

    ## [1] 97

#### open 2015 csv file

``` r
Year2015 <- read.csv("2015 SpatData.csv", header = TRUE, stringsAsFactors = FALSE)
```

#### open 2016 csv file

``` r
Year2016 <- read.csv("2016 SpatData.csv", header = TRUE, stringsAsFactors = FALSE)
```

#### open 2017 csv file

``` r
Year2017 <- read.csv("2017 SpatData.csv", header = TRUE, stringsAsFactors = FALSE)
```

#### Split the 2015 by the area

``` r
MR15 <- split(Year2015, Year2015$Area)
```

#### Split the 2016 by the area

``` r
MR16 <- split(Year2016, Year2016$Area)
```

#### Split the 2017 by the area

``` r
MR17 <- split(Year2017, Year2017$Area)
```

#### get the sum of scallops in MR for 2015

``` r
sum(MR15$MR$Scallop.count)
```

    ## [1] 16125

#### get the Sum of scallops in MR for 2016

``` r
sum(MR16$MR$Scallop.count)
```

    ## [1] 3560

#### get the sum of scallops in MR for 2017

``` r
sum(MR17$MR$Scallop.count)
```

    ## [1] 2444

### Contributors

1.  Bobodzhon Isamov - R Script and documentation proofreading
2.  Tarun Chaturvedi - R Script and further data cleaning
3.  Srishty Nayak - Analysis questions and documentation
