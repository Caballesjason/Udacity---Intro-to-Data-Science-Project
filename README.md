# Analysis of NYC Citi Bike Share System

The aim of this project is to analyze New York City's [Citi Bike Share system](https://citibikenyc.com/), a staple in the city's culture. The analysis will follow the CRISP-DM process, or the _Cross-Industry Standard Process for Data Mining_ framework.

This README.md file provides an overview of each section. The technical analysis and code will be in `analysis.ipynb`, and a casual presentation will be provided in this [Medium article]().

This will be the start of many analysis projects for the bike share system. While very useful, there are a variety of issues related to the bike share system that need to be addressed and could not fit in one presentation. For more information on issues related to the Citi Bike Share system, click [here](https://comptroller.nyc.gov/reports/riding-forward-overhauling-citi-bikes-contract-for-better-more-equitable-service/).

---

# CRISP-DM Process

## Business Understanding
We aim to describe bike rider behavior in July of 2024, posing the four questions below:

1. Which stations have longer trip times on average?
2. When are bikers most actively riding bikes?
3. Which stations receive bikes from the most stations? Which stations send bikes to the most stations?
4. Can we identify any monotonic relationships for future modeling?

## Data Understanding
Confusingly, the Citi Bike Share system is managed by Lyft, and its historical data can be obtained [here](https://s3.amazonaws.com/tripdata/index.html).

To execute `analysis.ipynb` with the data, please download `202404-citibike-tripdata.csv.zip`. General information about each bike station can also be obtained [here](https://gbfs.lyft.com/gbfs/2.3/bkn/en/station_information.json).

## Data Preparation
The following data transformation steps were executed:

- Encode categorical data.
- Create fields that capture the start/end date and time riders begin/end their trips.
- Create a field that describes trip durations.
- Create a field that describes trip durations using the _Manhattan Distance_.
- Drop any rows with missing station IDs.
- Create a network to capture station relationships.

## Data Modeling
One aim of this analysis was to better understand trip duration and determine whether it could be predicted based on various features. Upon analysis, it was shown that the data had weak monotonic relationships; therefore, more examples or new features must be introduced for modeling.

## Results
After analysis, it was shown that:

1. The station with `ID = 8153.1` had substantially longer trip durations than any other station on average.
2. Riders are most active in the evening, specifically between 5:00 PM and 8:59 PM.
3. In the month of July, the station `6822.09` had the most incoming bikes, while the station `5308.04` had the most outgoing bikes.

## Deployment
The casual analysis will be posted on Medium, while the technical analysis will be in `analysis.ipynb`.
