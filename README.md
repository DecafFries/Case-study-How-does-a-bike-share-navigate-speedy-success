# GDAC Case Study 1: How does a bike-share navigate speedy success?
This repository keeps track of my progress in completing Google Data Analytics Professional Certificate Capstone case study 1: "How does a bike-share navigate speedy success?"

## Ask
### Guiding questions:
1. What is the problem you are trying to solve?
    - Assist in finding solutions to maximising the number of annual members, considering annual members are much more profitable than casual riders.
2. How can your insights drive business decisions?
    - Provide data-driven analysis to provide evidence supporting marketing strategies in converting casual riders into annual members.

### Key tasks:
1. Identify the business task
    - The task of the current stage is understanding how annual members and casual riders use Cyclistic bikes differently. 
2. Consider key stakeholders
    - Casual riders: Customers who purchase single-ride or full-day passes;
    - Annual members: Customers who purchase annual memberships.

### Deliverable
Given that annual members are much more profitable than casual riders, the problem I am trying to solve is to assist in finding solutions to maximising the number of annual members. By providing data-driven analysis, my insights could potentially provide evidence supporting the marketing strategy decision to convert casual riders into annual members. Currently, the main focus is understanding the differences in using Cyclistic bikes between the key stakeholders, namely the casual riders and the annual members, where casual riders are customers who only purchase single-ride or full-day passes and annual members are customers who purchase annual memberships.

## Prepare
### Guiding questions:
1. Where is your data located?
    - The data is available via link: https://divvy-tripdata.s3.amazonaws.com/index.html.
2. How is the data organised?
    - The data was organised into several batches of compressed folders:
        - Data for the year 2013 was stored in one compressed folder;
        - For data between 2014 and 2017, each compressed folder contains semi-annual data;
        - For data between 2018 and 2020 quarter 1, each compressed folder contains quarterly data;
        - For data from April 2020 to date, each compressed folder contains monthly data.
    - Under each compressed folder there is a CSV file, which keeps the records of the corresponding period with information on:
        - ride_id: unique id of each ride;
        - rideable_type: type of the bicycle of the ride;
        - started_at: starting date and time for the ride;
        - ended_at: ending date and time for the ride;
        - start_station_name: name of the starting station;
        - start_station_id: id of the starting station;
        - end_station_name: name of the ending station;
        - end_station_id: id of the ending station;
        - start_lat: latitude of the starting station;
        - start_lng: longitude of the starting station;
        - end_lat: latitude of the ending station;
        - end_lng: longitude of the ending station;
        - member_casual: identifier of the user, whether they are casual riders or annual members.
    - Since the project requires focusing on the past 12 months, data from April 2023 to March 2024 was downloaded from the given website.

3. Are there issues with bias or credibility in this data? Does your data ROCCC?
    - So far it looks like the data for the past year was automatically collected by the preset mechanism, and   
4. How are you addressing licensing, privacy, security, and accessibility?
5. How did you verify the data's integrity?
6. How does it help you answer your question?
7. Are there any problems with the data?
    - According to the observation of the sample set data, it looks like the original data was not 

### Key tasks:
1. Download data and store it appropriately.
2. Identify how it's organised.
3. Sort and filter the data.
4. Determine the credibility of the data

## Process
