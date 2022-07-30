# Google Data Studio Capstone Project 1
## How does a bike-share navigate speedy success?

This is my case study on Google Data Analytics Certificate - Capstone Project (Cyclistic bike-share analysis) as a junior data analyst. 

<b>Scenario:</b><br>
A bike-share program that features more than 5,800 bicycles and 600 docking stations. Cyclistic sets itself apart by also offering reclining bikes, hand tricycles, and cargo bikes, making bike-share more inclusive to people with disabilities and riders who can’t use a standard two-wheeled bike. The majority of riders opt for traditional bikes; about 8% of riders use the assistive options. Cyclistic users are more likely to ride for leisure, but about 30% use them to commute to work each day. The data used in this analysis are real data collection in between April 2020 and March 2021.

### ASK

Problem trying to solve: Find out the casual riders bike usability and how to convert them to annual member.

My insights will helps marketing team to run targeted marketing campaign to increase more annual membership.

Business task: How do annual members and casual riders use Cyclistic bikes differently?

**Stakeholders:**
- Lily Moreno, Director of marketing at Cyclistic.
- Cyclistic marketing analytics team
- Cyclistic executive team

**Deliverable:** Find out how casual riders uses bikes differently then annual member 

### Prepare
Data used in this case study were made available by Motivate International Inc. under the [licence](https://www.divvybikes.com/data-license-agreement).
Data location - [here](https://divvy-tripdata.s3.amazonaws.com/index.html) downloaded and stored on personal computer.
Data collected on csv file on every month. April 2020 to March 2021 twelve months data has been used in this case study. Each file contain 13 columns that includes ids, bike type, start and end date and time, start and end station name, station ids, members type.

There are some typical issues with data in each file such as blank, duplicate data etc.

### Process
Tools used in this process is Microsoft Excel, R Studio and Tableau. 
All csv file convered into excel formate(.xlsx) and saved in separate folder so that all calculated fields remain saved in excel file.  
Started with cleaning data in each file, removing missing value rows, removing duplicate data by “rider_id” attribute and removing short or large ride duration data.

Once cleaning done, I added two new column at the end of the table-
“Ride_length” = for total ride length calculation (ending time minus starting time) and format calculated column to hh:mm:ss to show result in time format.
“Day_of_week” = calculated day of the week for each trip and formatted in integer value.
Once cleaning data, I checked and make sure that all column names in all files are consist. 

### Analyze
After cleaning data I started analysis process with R Studio desktop. Because of the file sizes, in my opinion this is quick way to process data. Clean data contain 3295475 rows and 15 columns.

Columns name

![](https://github.com/palmultimedia/google-data-analytics-cap1/blob/main/4-colname.jpg)

1st 15 rows of combine data.

![](https://github.com/palmultimedia/google-data-analytics-cap1/blob/main/4-1st15row.png)

List of columns and data type

![](https://github.com/palmultimedia/google-data-analytics-cap1/blob/main/4-list.png)

Group members data

![](https://github.com/palmultimedia/google-data-analytics-cap1/blob/main/4-group.png)

Group meners by casual vs registered members usages different rideable bikes

![](https://github.com/palmultimedia/google-data-analytics-cap1/blob/main/4-group2.png)

Rideable bike usage - by this data it shows that docked_bikes has mode usage in compare to other.

![](https://github.com/palmultimedia/google-data-analytics-cap1/blob/main/4-riderusage.png)

Week days bike usage by casual and registered members.

![](https://github.com/palmultimedia/google-data-analytics-cap1/blob/main/4-weeksday.png)

Below graph shows casual customer vs members comparison in total for 12 month.
It appears that registered members has arround 43% more usage compare to casual customers.

![](https://github.com/palmultimedia/google-data-analytics-cap1/blob/main/4-below1.png)


![](https://github.com/palmultimedia/google-data-analytics-cap1/blob/main/4member01.png)


By month analysis it it shows that summer time has more usage of bikes with August has highest usage.

```
cyclistic_data %>%
  ggplot(aes(year_month, fill=member_casual)) +
    geom_bar() +
    labs(x="Month", title="By monthly usaage") +
    coord_flip()
```
<br>
![](https://github.com/palmultimedia/google-data-analytics-cap1/blob/main/4-cyclistdata.png)



**Number of rides by members vs casual riders by weekday.**

Key findings in weekdays bike usage are overall riders has used bikes in weekend (days 6 and 7) in compare to the weekdays.


![](https://github.com/palmultimedia/google-data-analytics-cap1/blob/main/count-of%20ride.png)

**Number of rides by casual riders vs members by month**

In 12 month period overall highest bike used in between July to September months which is summer time and fewer usage during winter time. Data also shows thaat from August month until year end bike usage by members are higher then the casual riders.

![](https://github.com/palmultimedia/google-data-analytics-cap1/blob/main/casual%20and%20member.png)

Average ride trip time by month vs rider type - casual & member
Data shows that overall average trip time by casual rider are much higher then the members.

![](https://github.com/palmultimedia/google-data-analytics-cap1/blob/main/avg-ride-time.png)

**Summary**<br>
-Casual rider tend to use the bikes for leisure, preferred to use more during summer time and weekend. Their average usage by time is about 2x longer then members.
-Members are tend to use bike more likely for commuting with shorter journey all year round by month. Their average usage time is half the average time of casual rider.

### Share
The project documants found here: Google Data Analytics - [Capston Project](https://github.com/palmultimedia/google-data-analytics-cap1)

### Act
Witht this analysis of casual rider vs annual members the marketing department can start a strategy to convert casual riders into annual members.
Large number of casual rider are most likely tourists, hanse recommandation would be either running some partial membership targeting summer time and weekends.
Summer time has most amount of causal riders therefore ideal recommandaiton would be to ran marketing campaign during this time to get more attention from casual rider.











