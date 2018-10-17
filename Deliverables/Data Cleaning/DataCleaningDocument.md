DataCleaningDocument
================
Tarun Chaturvedi
October 17, 2018

-   [**Team Name: *Mavs***](#team-name-mavs)
-   [Task 1 - Data description](#task-1---data-description)
    -   [The headers are as follows:](#the-headers-are-as-follows)
-   [Task 2 - Policy](#task-2---policy)
-   [Task 3 - Meta data](#task-3---meta-data)
-   [Task 4 - Issues](#task-4---issues)
-   [Task 5 - Steps taken to remediate data](#task-5---steps-taken-to-remediate-data)
-   [Task 6 - Data Cleaning Scripts](#task-6---data-cleaning-scripts)
    -   [Temperature Data](#temperature-data)
    -   [Spat Bag Data](#spat-bag-data)
-   [Task 7 - Contributors](#task-7---contributors)

**Team Name: *Mavs***
---------------------

-   **Team Project: Hurricane Island for Scallop Growth**
-   **Team Members:**

-   **Srishty**
-   **Tarun**
-   **Bobo**

Task 1 - Data description
-------------------------

The Data Displyed here is about the Scallop Growth in Hurricane Island. There are three important dataset we got from the client with the help of which we are doing the analysis of scallop growth. The dataset we have are Spat bag, Scallop growth and Temperature data. The details of these basic dataset are as follows:

-   Spat bags Data: Spat is basically the small baby scallop which is recruit to an area. This is a planktonic stage for scallop which helps us understand what population dynamics are in an area, it also gives us an idea of recruitments to that area. Spat data are from north of the closures, south of the closures and within the closure. The data are from the years 2016, 2017 and 2018. Based on data present with us the average height of cage 1 scallop in oct 2017 was 24.87 and cage 2 was 43.7333. This was Random Sampled Measurements of 20 Individual scallops taken randomly. Also, the annual average growth(mm) of the scallops for the years 2016-2017 is approximately 20.86, with this data we can check for further variation over the following years. This data will help us understand which area is good for settlement around the closed area. Spat data is also gathered from ocean point area which is another closed area, but a larger closed area for long term which has been managed by Department of Rain fishery.
-   Scallop growth data: Scallop growth data is about growing scallops which are involved in aquaculture research. This data set is used to understand the impact of different gear types on the growth rate of scallops. Scallops has been put in different type of gear and cages and the size of scallops are measured every year, month and some time by weekly. By doing this measurement we can understand the impact of density and gear type on scallop growth. All the scallops are tagged, to differentiate them from one another which also helps to follow their growth as an individual throughout their lifetime in the cages where scallops are grown. The decisions can be taken based on the growth rate analysis.
-   Temperature Data: Temperature data are some from spat bags which were deployed, and some are from gear and cages which is deployed in Hurricane Island. The variables present in temperature data help us understand spat, population dynamic, popular influences on growth rate of scallops. Also, the temperature of water can be obtained from the temperature data.

The data contains

-   Spat data: 17 Columns and 22 rows

-   Temperature: 15024 columns and 3 rows each in 2016 and 30045 rows in 2017 data.

-   ScallopGrowth: 7 excel sheets containing raw data, height , width , depth information.

### The headers are as follows:

-   Spat Data:

<table style="width:61%;">
<colgroup>
<col width="5%" />
<col width="5%" />
<col width="5%" />
<col width="5%" />
<col width="5%" />
<col width="5%" />
<col width="5%" />
<col width="5%" />
<col width="5%" />
<col width="5%" />
<col width="5%" />
</colgroup>
<thead>
<tr class="header">
<th>Date</th>
<th>Line_Bag</th>
<th>zip Color</th>
<th>Latitude</th>
<th>Longitude</th>
<th>Area</th>
<th>Closure</th>
<th>Scallop Size</th>
<th>Size Count</th>
<th>Total Scallop</th>
<th>Count</th>
</tr>
</thead>
<tbody>
</tbody>
</table>

-   Temp:

| ID  | Date Time | Temp |
|-----|-----------|------|

Task 2 - Policy
---------------

The information is provided here and the site makes no warranties on the information provided. Any damages resulting from its use are disclaimed. We encourage the use of our open data commons licenses but we cannot give any warranty that they will work in the way expected or should be used for any specific purpose. For more information on license, please visit the link below.
License: This is simply a handy reference for understanding the ODbL 1.0 - it is a human-readable expression of some of its key terms. This document has no legal value, and its contents do not appear in the actual license. Please see the disclaimer below.
You are free:
To Share: To copy, distribute and use the database.
To Create: To produce works from the database.
To Adapt: To modify, transform and build upon the database.
[See here for more information](http://opendefinition.org/licenses/odc-odbl/)

Task 3 - Meta data
------------------

The Data Displayed here is about the growth of scallop.There are many factors that affect scallop growth like temperature, location, closure zone, density and so on by these factors we will be analyzing how the scallop growth happen in certain area, which is best location for their growth, how the temperature affect the growth, which area the scallop are dying the most, what is the suitable latitude and longitude of certain area, what should be the suitable water temperature. Below are the dataset available:

-   2018 Spat data
-   ScallopGrowth\_2016-17\_TaggedCage
-   Temperature2\_2016\_TaggedCage and
-   Temperature2\_2017\_TaggedCage

Task 4 - Issues
---------------

The main issue that was encountered with the data was missing fields. In the spat data 2018, there was a big gap with not enough information. Thus, it was removed. Some fields needs more precise description to make it easier to interpret during the analysis part. The data should follow identical format: for date field use mm/dd/yyyy standardized etc.

Task 5 - Steps taken to remediate data
--------------------------------------

For the missing date we approximated the date based on the observation of other date feilds. Thus, we encountered that there is a 2-3 days gap between each record. Some entries that were missing more than one field was completely removed, since the data is not precise.

Task 6 - Data Cleaning Scripts
------------------------------

#### Temperature Data

Steps:

1.  Create New Excel Sheet named "Temperature.xlsx"
2.  Open Temperature2\_2016\_TaggedCage.xls and delete Columns D,E,F,G,H. There are just 1 or 2 entries in each column, which can't help us in our analysis because there are 15026 entries for temperature to be considered and there isn't sufficient data in rest of the columns to even assume.
3.  Delete entry number 15024, 15025 and 15026 because they all have the same time and also the temperature wasn't recorded at that time.
4.  Copy Paste Data from Temperature2\_2016\_TaggedCage.xls to Temperature.xlsx
5.  Open Temperature2\_2017\_TaggedCage.xls and delete Columns D,E,F,G,H. There are just 1 or 2 entries in each column, which can't help us in our analysis because there are 30048 entries for temperature to be considered and there isn't sufficient data in rest of the columns to even assume.
6.  Delete entry number 30046, 30047 and 30048 because they all have the same time and also the temperature wasn't recorded at that time.
7.  Copy Paste Data from Temperature2\_2017\_TaggedCage.xls to Temperature.xlsx

#### Spat Bag Data

Steps:

1.  All the fields from row 16 to 25 should be removed, there is no data on Primary Zip Color, Line Number, Closure, and the location that was is not precise with long and lat compare to other entries.
2.  Sorting dates must be sorted in the same format, therefore, the standard we pick will be mm/dd/yyyy.
3.  Missing date on row 12 column H, was filled with 8/13/18. This is due to the fact, that other entries have 2-3 days interval in between. Therefore, it is assumed that the entry was collected around this date.
4.  Date field is formated using excel short date format.
5.  Should get the total count of all Scallops found and base a regression model. Since the research is around the total Scallop growth over the year.

Task 7 - Contributors
---------------------

1.  Bobodzhon Isamov - Cleaned Spat Data. Task 2,4 and 6
2.  Srishty Nayak - Document Layout. Task 1,3, 5. Proofreader.
3.  Tarun Chaturvedi - Cleaned Temperature data. Contributed to Task 6 and 7. R markdown documentation and knitted to html and github.
