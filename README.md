# GDAC Case Study 1: How does a bike-share navigate speedy success?
This repository keeps track of my progress in completing Google Data Analytics Professional Certificate Capstone case study 1: "How does a bike-share navigate speedy success?"

## I. Ask
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
- A clear statement of the business task.
    - Given that annual members are much more profitable than casual riders, the problem I am trying to solve is to assist in finding solutions to maximising the number of annual members. By providing data-driven analysis, my insights could potentially provide evidence supporting the marketing strategy decision to convert casual riders into annual members. Currently, the main focus is understanding the differences in using Cyclistic bikes between the key stakeholders, namely the casual riders and the annual members, where casual riders are customers who only purchase single-ride or full-day passes and annual members are customers who purchase annual memberships.

## II. Prepare
### Guiding questions:
1. Where is your data located?
    - The data is available via link: https://divvy-tripdata.s3.amazonaws.com/index.html.
    - A brief description of the data is available via: https://divvybikes-marketing-staging.lyft.net/system-data.  
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
    - Bias
        - According to the given information, the data was automatically collected by a preset mechanism. Since the data is likely to be collected for every ride, there is no sign showing sampling bias.
        - Also, there's no evidence confirming there could be availability bias.
        - Although it was introduced that the available data was processed by staff, as all rides below 60 seconds were removed considering they are less likely to result from a real trip, there are still chances 
        - After all, it is assumed that the data has less likelihood to be biased and won't affect the further analysis.    
    - Credibility (ROCCC)
        - Reliable: The data is retrieved from the company's official data archive, which is trustworthy and reliable.
        - Original: Considering that the data is retrieved from the company's official data archive, it is considered first-hand data rather than copies or summaries of other data sources and can be treated as original; 
        - Comprehensive: The data used in this analysis covers the full 12 months' length of data, ensures its comprehensive;
        - Current: The data is current as it contains the last 12 months' records;
        - Cited: Although it was not mentioned in the case study, the selected data has been widely recognised and cited by analytics professionals as a case study example. 
4. How are you addressing licensing, privacy, security, and accessibility?
    - Licensing: My analyses will strictly follow the enclosed licensing agreement: https://divvybikes.com/data-license-agreement.
    - Privacy: Since the data does not contain PII, it will not breach real-life users' privacy.
    - Security and accessibility: Considering this case study is considered to test and showcase my analytics knowledge and skills, the security issue is not a major concern here and the content is openly accessible. **_However, anyone's unauthorised copying/plagiarising activities from my answers for any purposes are strictly prohibited._**
5. How did you verify the data's integrity?
    - The main concerns have been addressed in the above answers, including but not limited to checking the source, looking for documentation, checking potential biases and credibility, etc. 
6. How does it help you answer your question?
    - By having a thorough check of the data and verifying the data's integrity, I can gain a deeper understanding of what is available from the data, and then work out a more comprehensive solution in answering the question.  
7. Are there any problems with the data?
    - According to the observation of the sample set data, it looks like the original data was not in the order of date and time.
    - Since the data was available in 12 separate files, it cannot be directly used for analysis and will require wrangling beforehand.
    - The data could be inconsistent throughout the entire timeline (from 2013 to date), however, this issue does not interfere with the current research as the data of the last 12 months are quite consistent.
    - Inconsistent naming system for station IDs, additionally, station IDs and names for a certain number of rides were not made available, although it is not clear whether they will affect the upcoming analysis. 

### Key tasks:
1. Download data and store it appropriately.
    - Done.
2. Identify how it's organised.
    - Done. 
3. Sort and filter the data.
    - Done.
4. Determine the credibility of the data
    - Done.

### Deliverable 
- A description of all data sources used
    - Details have already been provided in the "guiding questions" section. 

## III. Process
### Guiding questions
1. What tools are you choosing and why?
    - Excel and R.
        - Excel can be used to preview data and process simple conversion tasks.
        - R can be used to process more advanced wrangling and bind all 12 datasets into a single one for further analysis. 
2. Have you ensured your data’s integrity?
    - Yes, I went through all the datasets and ensured the columns were named consistently before they were merged. 
3. What steps have you taken to ensure that your data is clean?
    - After the data had been fully merged, I checked the structure of the data and noticed date time variables were recognised as character values by R. I then converted them as POSIXct values to ensure tasks at a later stage wouldn't be affected by misaligned data types. 
    - After creating new variables, I sorted the data based on the ascending order of starting date time and filtered out all the records whose key variables contained null values. It turned out that out of 5750177 observations, there are 7566 records missing latitude and longitude data of the ending points, which would result in biased/incorrect interpretations of ride duration, and they have been removed to ensure the data is clean.
    - I also checked the counts of distinct values of ride_id, the variable that is supposed to be unique for every record. It turned out that the data does not have any duplicates since the distinct counts of ride_id equals the counts of the entire observations.
4. How can you verify that your data is clean and ready to analyze? Have you documented your cleaning process so you can review and share those
results?
    - The above answer has proven that my awareness of data cleanness, and all the mentioned anomalies have been addressed.
    - Yes I have documented my cleaning process in my R markdown file created for data processing and analysis. 

### Key tasks
1. Check the data for errors.
    - Done.
2. Choose your tools.
    - Done. 
3. Transform the data so you can work with it effectively.
    - Done.
4. Document the cleaning process.
    - Done.

### Deliverable 
- Documentation of any cleaning or manipulation of data
    - All 12 spreadsheets have been renamed to the format of "yyyymm.csv" to ensure naming simplicity and consistency.
    - An R markdown file has been created to process and analyse data.
    - All 12 spreadsheets have been imported to R and merged into a single dataset.
    - The dataset has been sorted based on the ascending order of starting date time.
    - New variables have been created for the convenience of the later analysis:
        - ride_length: Difference between the starting date time and ending date time.
        - day_of_week: Indicating the day of the week information of the corresponding observation.
    - All records containing null values in key variables have been removed to ensure analysis accuracy.
    - Data duplication has also been checked to ensure no duplicates will affect the result of analysis.
 
## IV. Analyse
### Guiding questions
1. How should you organise your data to perform analysis on it?
2. Has your data been properly formatted?
3. What surprises did you discover in the data?
4. What trends or relationships did you find in the data?
5. How will these insights help answer your business questions?

### Key tasks
1. Aggregate your data so it’s useful and accessible.
2. Organise and format your data.
3. Perform calculations.
4. Identify trends and relationships.

### Deliverable 
- A summary of your analysis

## V. Share
### Guiding questions
1. Were you able to answer the question of how annual members and casual riders use Cyclistic bikes differently?
2. What story does your data tell?
3. How do your findings relate to your original question?
4. Who is your audience? What is the best way to communicate with them?
5. Can data visualization help you share your findings?
6. Is your presentation accessible to your audience?

### Key tasks
1. Determine the best way to share your findings.
2. Create effective data visualizations.
3. Present your findings.
4. Ensure your work is accessible.

### Deliverable 
- Supporting visualizations and key findings

## VI. Act
### Guiding questions
1. What is your final conclusion based on your analysis?
2. How could your team and business apply your insights?
3. What next steps would you or your stakeholders take based on your findings?
4. Is there additional data you could use to expand on your findings?

### Key tasks
1. Create your portfolio.
2. Add your case study.
3. Practice presenting your case study to a friend or family member.

### Deliverable 
- Your top three recommendations based on your analysis
