R Plots
================
Tarun Chaturvedi
November 7, 2018

-   [**Team Name: *Mavs***](#team-name-mavs)
    -   [Read the .csv file](#read-the-.csv-file)
    -   [attach dataframe for plotting.](#attach-dataframe-for-plotting.)
-   [Scallop Count Per Year](#scallop-count-per-year)
    -   [barplot(Scallop.Count,Year)](#barplotscallop.countyear)
-   [Scallop Count per Year (Better visualized)](#scallop-count-per-year-better-visualized)
    -   [ggplot(spatstats, aes(x=Year, y=Scallop.Count)) + geom\_bar(stat = "identity")](#ggplotspatstats-aesxyear-yscallop.count-geom_barstat-identity)
-   [Scallops in each Closure Zone](#scallops-in-each-closure-zone)
    -   [ggplot(spatbag, aes(x=Closure.zone, y=Total.Scallops)) + geom\_bar(stat = "identity")](#ggplotspatbag-aesxclosure.zone-ytotal.scallops-geom_barstat-identity)
-   [Scallops in different Areas (2015)](#scallops-in-different-areas-2015)
    -   [ggplot(Year2015, aes(x=Area, y=Scallop.count)) + geom\_bar(stat = "identity")](#ggplotyear2015-aesxarea-yscallop.count-geom_barstat-identity)
-   [Scallops in different Areas (2016)](#scallops-in-different-areas-2016)
    -   [ggplot(Year2016, aes(x=Area, y=Scallop.count)) + geom\_bar(stat = "identity")](#ggplotyear2016-aesxarea-yscallop.count-geom_barstat-identity)
-   [Scallops in different Areas (2017)](#scallops-in-different-areas-2017)
    -   [ggplot(Year2017, aes(x=Area, y=Scallop.count)) + geom\_bar(stat = "identity")](#ggplotyear2017-aesxarea-yscallop.count-geom_barstat-identity)
    -   [Contributors](#contributors)

------------------------------------------------------------------------

**Team Name: *Mavs***
---------------------

-   **Team Project: Hurricane Island for scallop Growth**
-   **Dataset: Scallop Growth dataset**

We have addressed the main research questions.

1.  Compare Scallop growth from years 2015-2018.(using ggplot)
2.  Scallops in each closure zone for the most recent year.
3.  Comparing Scallops in each area for the year 2015,2016 and 2017
4.  New Excel Stats sheet was created having records of year 2015,2016, 2017 and 2018

#### Read the .csv file

``` r
spatstats <- read.csv("Stats.csv", header = TRUE, stringsAsFactors = FALSE)
```

#### attach dataframe for plotting.

``` r
attach(spatstats)
```

##### Note:- Run the .Rmd file to generate the graphs. We have attached graph images in this file.

Scallop Count Per Year
----------------------

### barplot(Scallop.Count,Year)

#### Using barplot for plotting number of scallops each year

![](Rplots_files/figure-markdown_github/spat-1.png)

![](https://github.com/Wolverine7/Team-Mavs-ISQA8086-002/blob/master/Deliverables/R-Plot/Graphs/ScallopCount.PNG)
#### Adding a new library for better visualization.

``` r
library(ggplot2)
```

#### attaching

``` r
head(spatstats)
```

    ##   Year Scallop.Count
    ## 1 2018          1069
    ## 2 2017          2637
    ## 3 2016          4120
    ## 4 2015         17706

Scallop Count per Year (Better visualized)
------------------------------------------

### ggplot(spatstats, aes(x=Year, y=Scallop.Count)) + geom\_bar(stat = "identity")

#### In the current research data, we tried to analyze the growth and the size of each scallop in the different closures. For our sample, we got the total Scallop Counts across 2018, 2017, 2016, and 2015 year. According, to the result we gathered, and the calculation provided, the total counts of Scallops actually decreased from 2015 onwards. This graph shows that the Scallop distribution across the years

![](Rplots_files/figure-markdown_github/yearly-1.png)

![](https://github.com/Wolverine7/Team-Mavs-ISQA8086-002/blob/master/Deliverables/R-Plot/Graphs/Scallops.PNG)

``` r
spatbag <- read.csv("Spat_Data.csv", header = TRUE, stringsAsFactors = FALSE)
```

``` r
head(spatbag)
```

Scallops in each Closure Zone
-----------------------------

### ggplot(spatbag, aes(x=Closure.zone, y=Total.Scallops)) + geom\_bar(stat = "identity")

#### In this data sample, we took the counts of total scallops across different closure zones. Based on the analysis, we noticed that the distribution was not even. First closure has far more total scallops counts compare to the south and the north. As far the graph we decided to show bar chart dividing scallops based on the zones.

![](Rplots_files/figure-markdown_github/closure-1.png)

![](https://github.com/Wolverine7/Team-Mavs-ISQA8086-002/blob/master/Deliverables/R-Plot/Graphs/ClosureStats.PNG)

``` r
Year2015 <- read.csv("2015 SpatData.csv", header = TRUE, stringsAsFactors = FALSE)
```

``` r
head(Year2015)
```

Scallops in different Areas (2015)
----------------------------------

### ggplot(Year2015, aes(x=Area, y=Scallop.count)) + geom\_bar(stat = "identity")

#### This plot shows that for the year 2015, the MR (Mussel Ridge) area had more number of Scallops.

    ## Warning: Removed 446 rows containing missing values (position_stack).

![](Rplots_files/figure-markdown_github/yr15-1.png)

![](https://github.com/Wolverine7/Team-Mavs-ISQA8086-002/blob/master/Deliverables/R-Plot/Graphs/2015Scallops.PNG)


``` r
Year2016 <- read.csv("2016 SpatData.csv", header = TRUE, stringsAsFactors = FALSE)
```

``` r
head(Year2016)
```

Scallops in different Areas (2016)
----------------------------------

### ggplot(Year2016, aes(x=Area, y=Scallop.count)) + geom\_bar(stat = "identity")

#### This plot shows that for the year 2016, the MR (Mussel Ridge) area had more number of Scallops.

    ## Warning: Removed 631 rows containing missing values (position_stack).

![](Rplots_files/figure-markdown_github/yr16-1.png)

![](https://github.com/Wolverine7/Team-Mavs-ISQA8086-002/blob/master/Deliverables/R-Plot/Graphs/2016Scallops.PNG)

``` r
Year2017 <- read.csv("2017 SpatData.csv", header = TRUE, stringsAsFactors = FALSE)
```

``` r
head(Year2017)
```

Scallops in different Areas (2017)
----------------------------------

### ggplot(Year2017, aes(x=Area, y=Scallop.count)) + geom\_bar(stat = "identity")

#### This plot shows that for the year 2017, the MR (Mussel Ridge) area had more number of Scallops.

![](Rplots_files/figure-markdown_github/yr17-1.png)

![](https://github.com/Wolverine7/Team-Mavs-ISQA8086-002/blob/master/Deliverables/R-Plot/Graphs/2017Scallops.PNG)

### Contributors

1.  Bobodzhon Isamov - Plots description and Peer Review Discussion
2.  Tarun Chaturvedi - R Plotting and further Data cleaning.
3.  Srishty Nayak - Proofreader
