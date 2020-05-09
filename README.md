# Surf's Up!
We're setting up a Surf n' Shake Shop with a new invester--W. Avy. We're meeting with him to discuss how we can get our shop to Oahu. Analyzing some data sets are the first step to knowing what we can present to W. Avy.

### Precipitation Data
We know that it rains in Oahu, but we don't konw exactly when. To predict that, we look at previous data and retrieve precipitation data.

![Precipitation Data](https://github.com/natrockwood/Surfs_Up/blob/master/precipitation_data.png)

From the reseults we got, we can see, from the graph that...
- Some months have higher amounts of precipitation than others
- The levels of rain vary over the years, and there's no specific trend for months that have the most rain in a year
- There are, however, more peaks every 3 months in 2017.

However, W. Avy wasn't so sure our data was valid and he was confirming if we had enough data collection stations to be sure.

We ran this query ```session.query(func.count(Station.station)).all()``` to check how many stations we had. This returned ```9``` total stations where we were collecting data from. We also determined that these 9 stations are currently active.

Since we found out that ```Station USC00519281``` is the most active station, W. Avy wanted us to further investigate it. We checked the min, max, and average temperatures that that station records.
Using the below query, we determined that the **Minimum Temp is 54 degrees**, the **Maximum Temp is 85 degrees**, and the **Average Temp is 71.66 degerees**.

## Challenge
Aside from knowing key statistics for the most active station, we inspect the key statistics in the seasons of Oahu to determine when business will be slow and to determine which customers would be visiting.

To check the seasonal statistics, I retrieved key information from the months of June and December, since they are the peak months of summer and winter. I used dataframes to summarize my findings, and to easily show numbers that would be helpful to investors.

Below is the comparison between June and December summary statistics:
Statistic | June  | December|
----------|-------|---------|
Count     | 1,700 | 1,517   |
Mean      | 74.94 | 71.04   |
Std. Dev. | 3.26  | 3.75    |
Min.      | 64    | 56      |
Max.      | 85    | 83      |
1Q (25%)  | 73    | 69      |
2Q (50%)  | 75    | 71      |
3Q (75%)  | 77    | 74      |

Some other things to think about analyzing is
- Wave / Swell highs and lows
- Festivities in Oahu
- Surfing contests throughout the year
