# BayWheels Data
## by Anna-Anastasiia Balatska
This project is the last part of the "Data Analyst Nanodegree" by Udacity. In this Project, I wrangled and thoroughly analysed a dataset of the bike company BayWheels. The two main goals of this project were:

1. Perform Exploratory Data Visualisation (`baywheel_project.ipynb`)
2. Perform Explanatory Data Visualisation (`slide_presentation.ipynb` and `slide_presentation.slides.html`)

## Dataset

### Data Wrangling 
I downloaded files about individual rides made since January 2019 until August 2020 from Ford GoBike System Data. These files were in 20 zip archieves. I unzipped all them simultaneously and programatically with zip and os libraries. Then I read all files in one dataframe with glob Python package. 

To save time running cells, I randomly sampled the dataframe (left 1 million observations out of 16.4 millions).

### Data Cleaning
- dropped unnecessary columns
- combined columns that had different names but the same purpose
- fixed wrong datatypes
- replaced duration in seconds for duration in minutes
- removed outliers
- created new columns for hours, days, months, years (as part of data tidiness)
- sorted data in chronological order

## Summary of Findings

BayWheels has 2 types of users: subscribers and usual customers. Almost 70% of users of the bike sharing system are subscribers.

I analysed data since January 2019 and it was interesting to see how popularity of BayWheels spiked in January and February 2020 compared to previous year. It looks like they had great potential for this year but due to the global COVID-19 pandemy they had almost 60% fall in March and it fell down even more in April (twice less bike rides compared to March). 

Another interesting observation is that duration of trips has a long-tailed distribution. 99,5 % of trips are made in 2 hours or less and 90% are done in 20 minutes or less. But it differs depending on user type and day of week. 

The average duration of rides is shorter for subscribers than for customers. For the members it's around 10 minutes, while for usual customers - 15. I also noticed that customers use Bay Wheels' bikes on weekends more often then members but they are less active during rush hour (right before and after work). I believe that it depend on how people use the app. Subscribers use it on regular basis for shorter trips to get to / from work, while customers can have different preferences.

On weekends the average trip for all users takes from 12-15 minutes (for early mornings) up to 20 minutes (around 2 pm). And during weekdays it takes from 10 to 14 minutes depending on time of the day. 

## Key Insights for Presentation

In order to polish a presentation:
- combined 2 plots for ride counts in 2019 and 2020 into one:
    - created a new month_year list (i.e. Jan '19, Feb '19)
    - fixed tick positions and bin size
- switched from the line plot with lines for all 7 days to 2-line plot for weekdays and weekends. It removed data junk and increased data-ink ratio. To do this:
    - created a new column that specifies if it is a weekday or a weekend
    - replaced title
- Finally, increased space between titles and plots in the last visualization using:
    - g.fig.subplots_adjust(top=.9)
