<h3 align="center">Cyclistic-Case-Study-Using-R</h3>

  <p align="center">
    Google Data Analytics Capstone Project - Cyclistic Bike-Share Case Study
   </p>
</div>

<p align="left">Scenario<br>
You are a junior data analyst working on the marketing analyst team at Cyclistic, a bike-share company in Chicago. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, your team wants to
understand how casual riders and annual members use Cyclistic bikes differently. From these insights, your team will design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve your recommendations, so they must be backed up with compelling data insights and professional data visualizations.</p>
------------------------------------------------------------------------
<p align="left">Characters and teams<br>

● Cyclistic: A bike-share program that features more than 5,800 bicycles and 600 docking stations. Cyclistic sets itself apart by also offering reclining bikes, hand tricycles, and cargo bikes, making bike-share more inclusive to people with disabilities and riders who can’t use a standard two-wheeled bike. The majority of riders opt for traditional bikes; about 8% of riders use the assistive options. Cyclistic users are more likely to ride for leisure, but about 30% use the bikes to commute to work each day.

● Lily Moreno: The director of marketing and your manager. Moreno is responsible for the development of campaigns and initiatives to promote the bike-share program. These may include email, social media, and other channels.

● Cyclistic marketing analytics team: A team of data analysts who are responsible for collecting, analyzing, and reporting data that helps guide Cyclistic marketing strategy. You joined this team six months ago and have been busy learning about Cyclistic’s
mission and business goals—as well as how you, as a junior data analyst, can help Cyclistic achieve them.

● Cyclistic executive team: The notoriously detail-oriented executive team will decide whether to approve the recommended marketing program.</p>

<p align="left">About the company<br>
In 2016, Cyclistic launched a successful bike-share offering. Since then, the program has grown to a fleet of 5,824 bicycles that are geotracked and locked into a network of 692 stations across Chicago. The bikes can be unlocked from one station and returned to any other station in the system anytime.<br>
Until now, Cyclistic’s marketing strategy relied on building general awareness and appealing to broad consumer segments. One approach that helped make these things possible was the flexibility of its pricing plans: single-ride passes, full-day passes, and annual memberships. Customers who purchase single-ride or full-day passes are referred to as casual riders. Customers who purchase annual memberships are Cyclistic members. Cyclistic’s finance analysts have concluded that annual members are much more profitable than casual riders. Although the pricing flexibility helps Cyclistic attract more customers, Moreno believes that maximizing the number of annual members will be key to future growth. Rather than creating a marketing campaign that targets all-new customers, Moreno believes there is a solid opportunity to convert casual riders into members. She notes that casual riders are already aware of the Cyclistic program and have chosen Cyclistic for their mobility needs. Moreno has set a clear goal: Design marketing strategies aimed at converting casual riders into annual members. In order to do that, however, the team needs to better understand how annual members and casual riders differ, why casual riders would buy a membership, and how digital media could affect their marketing tactics. Moreno and her team are interested in analyzing the Cyclistic historical bike trip data to identify trends.</p>

# Ask<br>
<p align="left">
Three questions will guide the future marketing program:<br><br>
1. How do annual members and casual riders use Cyclistic bikes differently?<br>
2. Why would casual riders buy Cyclistic annual memberships?<br>
3. How can Cyclistic use digital media to influence casual riders to become members?<br><br>
Moreno has assigned you the first question to answer: How do annual members and casual riders use Cyclistic bikes differently?<br><br>
You will produce a report with the following deliverables:<br>
1. A clear statement of the business task<br>
2. A description of all data sources used<br>
3. Documentation of any cleaning or manipulation of data<br>
4. A summary of your analysis<br>
5. Supporting visualizations and key findings<br>
6. Your top three recommendations based on your analysis</p>

### Key tasks<br>
● Identify the business task<br>
● Consider key stakeholders<br>
### Deliverable<br>
● A clear statement of the business task<br>
## Business Task<br>
<i>Analyze the 2024 trip data for Cyclistic to understand how casual riders and annual members use the service differently to provide recommendations on how to convert casual riders to annual members.</i><br><br>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

# Prepare<br>
Use Cyclistic’s historical trip data to analyze and identify trends.<br>
#### Important Notes<br>
The datasets have a different name, Divvy, because Cyclistic is a fictional company. For the purposes of this case study, the datasets are appropriate and will enable you to answer the business questions. The data has been made available by Motivate International Inc. under this license. This is public data that you can use to explore how different customer types are using Cyclistic bikes.<br>
Data-privacy issues prohibit you from using riders’ personally identifiable information. This means that you won’t be able to connect pass purchases to credit card numbers to determine if casual riders live in the Cyclistic service area or if they have purchased multiple single passes.

### Key tasks<br>
● Download data and store it appropriately.<br>
● Identify how it’s organized.<br>
● Sort and filter the data.<br>
● Determine the credibility of the data.<br>
### Deliverable<br>
● A description of all data sources used<br>

## Description of data sources used<br>
<i>I used the most recent twelve-month historical trip datasets provided by Cyclistic (Divvy) to perform this analysis. This includes twelve files each containing a month of data from Janaury 2024 to December 2024. For the purpose of this case study, the datasets are appropriate and creditable, enabling me to address the business task.</i>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

# Process<br>
Process your data for analysis<br>
### Key tasks<br>
● Check the data for errors.<br>
● Choose your tools.<br>
● Transform the data so you can work with it effectively.<br>
● Document the cleaning process.<br>
### Deliverable<br>
● Documentation of any cleaning or manipulation of data<br>

## Documentation of cleaning and manipulation of data<br>
<i>Tools<br>I chose to use R programming in RStudio as the datasets are extremely large (+5M rows of data), which are not handled well in spreadsheets. Additionally, R allows for cleaning, transforming, analysing, and visualizing the data in one place.</i><br><br>
<i>Cleaning and transforming data</i><br>
<i>Preparing RStudio and loading the datasets</i><br>
```
install.packages("tidyverse")
install.packages("lubridate")
install.packages("ggplot2")
install.packages("dplyr")
install.packages("geosphere")
```
```
library(tidyverse)
library(lubridate)
library(ggplot2)
library(dplyr)
library(geosphere)
```
```
Jan24<-read.csv("202401-divvy-tripdata.csv")
Feb24<-read.csv("202402-divvy-tripdata.csv")
Mar24<-read.csv("202403-divvy-tripdata.csv")
Apr24<-read.csv("202404-divvy-tripdata.csv")
May24<-read.csv("202406-divvy-tripdata.csv")
Jun24<-read.csv("202406-divvy-tripdata.csv")
Jul24<-read.csv("202407-divvy-tripdata.csv")
Aug24<-read.csv("202408-divvy-tripdata.csv")
Sep24<-read.csv("202409-divvy-tripdata.csv")
Oct24<-read.csv("202410-divvy-tripdata.csv")
Nov24<-read.csv("202411-divvy-tripdata.csv")
Dec24<-read.csv("202412-divvy-tripdata.csv")
```
<i>Once the datasets were loaded I inspected each file to verify consistency by running colnames() and str()</i><br>
<img width="1103" height="316" alt="Example Colnames and Str-Jan2024" src="https://github.com/user-attachments/assets/334f2fd0-7aaf-4202-b920-5c197c7f9a5e" /><br><br>
<i>Then I merged the files into one dataframe</i><br>
```
trip_data <- rbind(Jan24, Feb24, Mar24, Apr24, May24, Jun24, Jul24, Aug24, Sep24, Oct24, Nov24, Dec24)
```
<i>Checking and removing Null/NA values</i><br>
```
trip_data_null <- na.omit(trip_data)
```
<i>Calculating the length of each trip in minutes by adding a new column called “ride_length”</i><br>
```
trip_data_null$ride_length <- difftime(trip_data_null$ended_at, trip_data_null$started_at, units="mins")
```
<i>Changing ride_length column to numeric for calculations</i><br>
```
trip_data_null$ride_length <- as.numeric(as.character(trip_data_null$ride_length))
```
<i>Adding columns for date, month, day, day of the week, hour, year for analysis</i><br>
```
trip_data_null$date <- as.Date(trip_data_null$started_at) 
trip_data_null$month <- format(as.Date(trip_data_null$date), "%m")
trip_data_null$day <- format(as.Date(trip_data_null$date), "%d")
trip_data_null$day_of_week <- format(as.Date(trip_data_null$date), "%w")
trip_data_null$hour <- format(as_datetime(all_trips$date), "%H")
trip_data_null$year <- format(as.Date(trip_data_null$date), "%y")
```
<i>Final cleaning step to remove negative ride lengths</i><br>
```
trip_data_clean <- trip_data_null[!trip_data_null$ride_length < 0,]
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

# Analyze<br>
Now that your data is stored appropriately and has been prepared for analysis start putting it to work<br>
### Key tasks<br>
● Aggregate your data so it’s useful and accessible.<br>
● Organize and format your data.<br>
● Perform calculations.<br>
● Identify trends and relationships.<br>
### Deliverable<br>
● A summary of your analysis

<i>Using Summary to obtain min, median, mean, and max for ride length</i><br>
```
summary(trip_data_clean$ride_length)
```
<i>Performing aggregate comparison of members and casual riders</i><br>
```
aggregate(trip_data_clean$ride_length ~ trip_data_clean$member_casual, FUN=mean)
aggregate(trip_data_clean$ride_length ~ trip_data_clean$member_casual, FUN=max)
aggregate(trip_data_clean$ride_length ~ trip_data_clean$member_casual, FUN=min)
aggregate(trip_data_clean$ride_length ~ trip_data_clean$member_casual, FUN=median)
```
<i>Arranging days of week Sunday through Saturday for clarity</i><br>
```
trip_data_clean$day_of_week <- ordered(trip_data_clean$day_of_week, levels=c("Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"))
```
<i>Summary of Analysis</i><br>
<i>Multiple variables were explored to identify the differences in behavior between annual members and casual riders including total rides of members and casual riders combined, preferred month for rides, preferred hours for rides, and preferred bike type.</i><br>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

# Share<br>
Now that you have performed your analysis and gained some insights into your data, create visualizations to share your findings. Moreno has reminded you that they should be sophisticated and polished in order to effectively communicate to the executive team.<br>
### Key tasks<br>
● Determine the best way to share your findings.<br>
● Create effective data visualizations.<br>
● Present your findings.<br>
● Ensure your work is accessible.<br>
### Deliverable<br>
● Supporting visualizations and key findings

<i>The bar chart below demonstrates that significantly more rides are taken by members than casual riders.</i><br>
<img width="748" height="547" alt="Cyclistic-TotalRides" src="https://github.com/user-attachments/assets/e743f937-5011-404e-93cd-88da1106cf76" /><br><br><br>
<i>The line chart below indicates that June is the preferred month for both members and casual riders, followed by September. May appears to be least preferred by both as well.</i><br>
<img width="748" height="547" alt="Cyclistic-TotalRidesMonth" src="https://github.com/user-attachments/assets/d3a83911-cab1-4d40-bf7b-f3893f41df4e" /><br><br><br>
<i>The bar chart below shows that members tend to have a higher frequency of rides between 7:00-9:00 and 16:00-18:00, which appears to indicate that members use the bikes to commute to and from work. The spike in number of rides around 16:00-18:00 for casual riders appears to indicate they are using the bikes for activities after work.</i><br>
<img width="748" height="547" alt="Cyclistic-TotalRidesHour" src="https://github.com/user-attachments/assets/8f477704-7627-4f4f-a2d9-0c4119bc868d" /><br><br><br>
<i>The stacked bar chart below suggests a slight preference for electric bikes for both members and casual riders over the classic bike type and both groups use the electric scooter significantly less.</i><br>
<img width="748" height="547" alt="Cyclistic-TotalBikeType" src="https://github.com/user-attachments/assets/eebb53b4-52dc-4324-9bf0-91f7ea2c7576" /><br><br><br>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

# Act<br>
Now that you have finished creating your visualizations, act on your findings. Prepare the deliverables Morena asked you to create, including the three top recommendations based on your analysis.<br>
### Key tasks<br>
● Create your portfolio.<br>
● Add your case study.<br>
● Practice presenting your case study to a friend or family member.<br>
### Deliverable<br>
● Your top three recommendations based on your analysis<br>
## Top Three Recommendations based on analysis<br>
<i>Advertising during the hours of 7:00-9:00 and 16:00-18:00 to encourage casual riders to use the bikes for their commutes.</i><br><br>
<i>Offering customizable or tiered memberships including weekday only, weekend only, and month-to-month options so casual users can choose a level that suits their requirements.</i><br><br>
<i>Sponsoring bike competitions with discounted memberships to participants and other prizes to raise awareness among casual riders and potential customers who haven't used a Cyclistic bike before.</i><br><br>

<p align="right">(<a href="#readme-top">back to top</a>)</p>
