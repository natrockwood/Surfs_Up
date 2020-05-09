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

From this table, the only huge difference is the Minimum Temperature. December is 9 degrees lower than June, and this would definitely affect the number of customers that come by the shop. Not that many people would want to be in the water in that cold weather. However, the maximum temperatures are relatively close together. They're also ample temperatures for customers to visit the beach and surf, leading to good business for the shop. The average temperatures are in the lower 70s. This range doesn't cater to the likings of many customers, but there are people that like to surf in this weather. Either way, if the temperatures range from average to maximum temperatures, at least in the months of June and December, there will be enough business. However, when temperatures drop, that is when business will most likely be slow. I think it's still worth keeping the shop open during December since "-ber" months are normally the best months for surfing in tropical countries.

Temperature, however, is not the only thing that would drive traffic and business. There are a few other factors that are worth analyzing.

#### Festivites
One would be to check the festivities that happen in Oahu that revolve around surfing and beaches. Knowing what goes on in the city would be helpful to determine which months the shop should expect more traffic.

#### Wave / Swell Data
If there is access to this data, looking at the peak months of swells and waves would be helpful to look at. Knowing when the waves are highest will definitely be information W. Avy would want to know to be more invested.

These are two things that would be useful for further analysis, and would be worth looking into.
