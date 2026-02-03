# SMS, Call, and Internet Activity Analysis
##  Introduction

This assignment analyzes SMS, call, and internet activity data collected in Milano over three different days in November 2013. The dataset contains information about communication activity aggregated by spatial grid cells and time intervals.
#### Datasets Used
The data consists of three CSV files:
* sms-call-internet-mi-2013-11-02.csv, sms-call-internet-mi-2013-11-04.csv, and sms-call-internet-mi-2013-11-06.csv


#### Dataset content
Each file contains communication activity information, about:

* received SMS, sent SMS, incoming calls, outgoing calls, and Internet activity  and their metadata. 

## Overview of the Approach

The three datasets were loaded separately and then concatenated into a single dataset since they all shared the same structure. Date and time features were extracted to support time-based analysis. Aggregate columns for total SMS, total calls, and total internet activity were created to simplify analysis.

## Key Decisions Made

After merging the data, the dataset was checked for missing values. Missing values were handled by filling each column with its mean, which is a robust approach that avoids data loss and reduces bias. This ensured the dataset remained complete and suitable for analysis.

From the timestamp column, Hour and Date features were drived to support the analysis of hourly patterns, peak activity times, and differences between daytime and nighttime usage.

5.2 Aggregate Activity Columns

The following aggregate columns were created:

total_sms: sum of incoming and outgoing SMS

total_calls: sum of incoming and outgoing calls

total_internet: total internet activity

These columns simplify analysis by allowing total activity comparisons instead of working with multiple raw columns.


## Summary of key findings
 Spatial Coverage

 Dataset contains `10000` unique CellIDs


Number of unique Country Codes

There is `302` unique country codes

##### Temporal Activity Patterns

The Most common peak hour accross all grids is `18:00` while the lowest activities was found to be `4:00`. Hourly activity follows normal daily routines: usage peaks around `18:00` after work hours, while the lowest activity occurs around `4:00`, when most people are inactive.

##### Call Statistics by Hour

For total call activity, the following statistics were calculated
![call statistics](results/statis_total_calls_by_hour.png)

##### Daytime vs Nighttime Activity

Activity was divided into: Daytime: 6:00 AM – 8:00 PM and Nighttime: 8:00 PM – 6:00 AM. The percentage of total activity occurring during each period was calculated.

Daytime activity percentage:
__________

Nighttime activity percentage:
__________

Interpretation of these results:
__________

10. Domestic vs International Activity
10.1 Call Timing Comparison

Calls were categorized as:

Domestic (Italy, country code 39)

International (all other country codes)

Hourly patterns for domestic and international calls were compared to see if they occur at different times of day.

Key differences observed:
__________

10.2 Call Volume Percentages

Percentage of domestic calls:
__________

Percentage of international calls:
__________

10.3 SMS Volume Percentages

Percentage of domestic SMS:
__________

Percentage of international SMS:
__________

10.4 Incoming vs Outgoing International Calls

The ratio of incoming to outgoing international calls was calculated.

Incoming to outgoing ratio:
__________

Interpretation:
__________

11. Statistical Analysis Using NumPy

NumPy was used to perform statistical comparisons between different conditions, including:

Domestic vs international call volumes

Differences in activity distributions

Statistical method used:
__________

Key results and interpretation:
__________

12. Correlation Analysis

To understand the relationship between SMS and call activity, data was aggregated at the grid (CellID) level.

The correlation between total SMS volume and total call volume was calculated.

Correlation value:
__________

Interpretation of correlation:
__________

13. Tools and Libraries Used

Python

Pandas

NumPy

Matplotlib

Seaborn

14. Repository Information

All code, analysis, and results are hosted on my GitHub account as required.