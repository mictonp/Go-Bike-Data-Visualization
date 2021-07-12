# Go Bike Data Visualization
## by Victor Pham


## General Description

This is a dataset of the bikeshare program called Go Bike that is run in San Francisco, California. The dataset shares individual bike ride trips in a specific time frame, from when a bike is rented from a start station, to when it is docked at an end station. 

The entirety of this database is for the trips in February of 2019.

The dataset shares information about the time of user using the ride-share program, including gender, age and type of customer.

The intent of this data visualization is to understand the properties of the rider that composes the majority of the customer base, and if there are common properties that lead to the increased number of trips and the duration of trips. This is only a data visualization and no statistical findings will be presented in this project. During this anaylsis key variables will be the focus. 

The categorical data includes:

- user_type
- weekday
- member_gender

The numerical data includes:

- duration_min
- Distance between stations (distance_km)
- Age
- Number of count of trips (not a column, but using aggregate data)


## Summary of Findings
Before performing any data visualization, some data wrangling was required for the Go Bike database for proper visualization. A summary of the wrangling includes:

- Converting some variables to proper data type. This includes start_time and end_time to datetime structures, member_birth_year as integer
- Calculating the distance of each trip based on the start and end location. This is assuming a linear distance between points and does not take into account any deviation in pathing. As such this should be used more of a relative indicator of distance and not an accurate measurement of where riders actually went.
- Calculate duration in minutes.
- Calculating age from the member birth years using 2019 as the present year.
- Adding an additional column for weekday for further analysis.
- Filter out extremely old or null value age participants (i.e. Member_age is zero, or age calculated is above 100 years of age to remove outliers from the visualizations.

### Univariate Exploration

Sample variables were plotted to understand the distribution in the data or relative proportions of certain customer segments. From the univariate exploration of the numerical variables, the age, distance and duration of the individual trips when plotted as a histogram, showed a right-skewed distribution. This tends to express a higher number of trips are typically shorter in distance and time, and the service is more popular with younger adults. 

When plotting pie charts to understand the relative proportions of the user base, it was found that there are more subscribers to the service than customers, and generally about 75% of the userbase is male, with the remaining being female and other.

When comparing which days are the most popular for trips, Thursday is the most popular day, with the lowest frequency of trips occuring on Sunday or Saturday. 

Lastly, a sample barchart was used to determine the top 20 trip locations to determine the most popular trip locations. Unsurprisingly the trips from the start and end paths shared common stations.

### Bivariate Exploration

During the bivariate exploration, two variables were compared to understand any trends, these include:

- Barplot - Average Duration (mins) vs. Member Gender 
- Barplot - Average Duration of trips based on Age
- Scatter plot & Line plot - Duration of Trips (min) versus Age
- Scatter plot & Line plot - Distance of Trips (km) versus Age
- Scatter plot - Distance of Trips (km) versus Duration (min)
- Countplot - Weekday and User type
- Countplot - Weekday and Member Gender

The barplots were used to visualize any main differences between the catogorical data and the duration of the trips or distance (km). Generally to see if one category or user type stands out more in terms of bike usage.

The scatter plot and line plots were plotted to see if there could be a relationship between two numerical variables. Generally these compared age, duration of trip and distance between stations (km). While the scatter plot shows the entirety of the data, the line plot shows the mean of the data with 95% confidence interval to help provide more clarity to the data. 

Lastly countplots were used to compare if there is any changes in the categorical data between different days of the week.

### Multivariate Exploration

Finally during the multivariate exploration, the various numeric variables are plotted together against different subgroups (categorical  user type, gender and weekday) as the third variable to understand if the different group types have an effect on the bike trips in obvious ways.


## Key Insights for Presentation

There are some trends that immediately stick out from all three explorations. In terms of understanding the custormer base, we can see that subscribers outnumber the customer and there are several more males (almost 75%) using the program versus females or other.

-When observing the combination of the two, the same proportions apply for male/female ratios. For the age groups, it seems the 25 to 45 age groups are more popular than the older age groups.

-When observing categorically, accross the board, interestingly the bikeshare is used significantly less on weekends (Sunday and Saturday) compared to the other weekdays, with Thursday seeing the most usage accross genders and subcribers. The people who are "customers" see little variance between weekends and weekdays.

-When observing age groups, the younger age groups tend to have steady distances and duration of trips with little variance (i.e. between 20 to 50) and are thus more consistent, but as the age group gets older, the average distance and duration varies tremendously. This would makes sense if the bike share program is being used for commuting then random bike trips. Older age gropus will likely be using the ride share for trips rather than commutes which can lead high variation in trip distances and durations. Lower age groups on the other hand likely use the program for communiting where the most popular central routes will have a fixed distance and duration during the month. 

The more data provided in the younger age groups also would lead to lower variance in the averages by age group compared to the older age
groups.

Based on what is observed in the data visualization, the bike share program is primarily used by younger age groups, typically males, and is likely used for communting with a higher density within certain bike stations.

Understanding these factors could lead to recommendations to adding incentives for improved usage of the bike share program over the weekends to encourage bike trips as their is lower usage over the weekend. For example, it is clear that people who use the service as a "customer" versus a "subscriber" are using the bikes for longer timeframe and distance. Depending on how the bikes are being used and the capacity there may be incentives to encourage more usage for subscribers or identifying areas where more bike stations may need to be installed.

For the presentation, the focus will be showing the distinct difference between the customer user type versus the subscriber user type, as well as shown how age impacts the duration and distance of the trips.

## List of Relevant and required software
- Python - Jupyter Notebook
- Numpy, Pandas, Matplotlib, Seaborn, Datetime, Geopy and Math

## List of Files in the Report
1) 201902-fordgobike-tripdata.csv - Original raw data file
2) cleaned_GoBike_Data.csv - Cleaned data file
3) GoBike_Data_Visualizations.ipynb - Go Bike visualization analysis Jupyter Notebook
4) GoBike_Dat_Visualization HTML File
5) GoBike_Slides.ipynb - Go Bike Slide Jupyer Notebook
6) GoBike_Slides HTML File
7) readme.md

## Acknowledgements and credits

The above analysis was taken from the GoBike data source provided by Udacity. The analysis was supplemented by Udacity courses and stackoverflow discussions. The visualizations were produced by myself, Victor Pham. Feedback was provided by Udacity.

## Bugs

-Some warnings using the seaborn.Pairgrid plot