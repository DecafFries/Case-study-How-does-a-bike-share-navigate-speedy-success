# Processed Data
- This folder stores the processed data containing cleaned and converted ride records from April 2023 to March 2024.
- The dataset has been sorted based on the ascending order of starting date time.
- New variables have been created for the convenience of the later analysis:
  - ride_length: Difference between the starting date time and ending date time.
  - day_of_week: Indicating the day of the week information of the corresponding observation.
  - month: Indicating the month information of the corresponding observation.
- All records containing null values in key variables/negative or zero valued ride_length have been removed to ensure analysis accuracy.
- Data duplication has also been checked to ensure no duplicates will affect the result of analysis.
- Note the size of decompressed data is approximately 1.19GB.  
