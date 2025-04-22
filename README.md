
# Road Accident Analysis 

## Problem Statement
Road accidents remain a major safety concern in the united kingdom, with limited visibility into patterns and causes hindering effective intervention. This project addresses the need for a data driven approach by analyzing historical accident data to uncover trends in severity, location, and conditions. The goal is to support informed decision making and improve road safety through this dynamic Power BI dashboard.


### Software Used
- Power BI – Data modeling and interactive visualizations

- Power Query – Data cleaning and transformation

- DAX – For calculated measures and KPIs

### Key Objectives
The dashboard highlights key road safety indicators, focusing on:

- Current Year Casualties

- Current Year Accidents

- Current Year Fatal Casualties

- Current Year Serious Casualties

- Current Year Slight Casualties

### Steps Followed
- Step 1 : Obtained the dataset in cv file format.
- Step 2 :Open power query editor and reviewed the raw data to check "column distribution", "column quality" and understand its structure, key columns, and potential quality issues (for example the missing values and inconsistent formatting).
- Step 3 : Also since by default, profile will be opened only for 1000 rows, you need to select "column profiling based on the entire dataset".
 - Step 4 : Converted data types (e.g, date, number, text) to match analysis needs.
- Step 5 : Corrected a data entry error in the severity column by replacing the value 'fetal' with 'fatal' to ensure consistency and accuracy in classification.
- Step 6 : Ensured column headers and data were properly structured before closing and applying to load the dataset to Power BI.
- Step 7 : Loaded the cleaned dataset into Power BI for modeling and visualization.
- Step 8 : Created a calendar table covering the years 2021 to 2022 to enable time-based analysis.

  Screenshot of created a calendar table,

  ![Image](https://github.com/user-attachments/assets/c46092aa-c47b-4415-84da-ad945c1fee84)

- Step : 9 Added calculated columns to extract the year and month from the date field. In the model view, established a relationship (with appropriate cardinality) between the calendar table and the main dataset by linking the date column in the calendar table to the accident date field in the dataset.

  Screenshot chart of the established  relationship (appropriate cardinality) between the calendar table and the main dataset,

  ![Image](https://github.com/user-attachments/assets/cb615f9d-b5d5-4243-a47f-efca9ca5095c)

- Step 10 : Created and calculated meaningful DAX measures to track analysis KPIs.
  
  The folowing DAX measures expression were written:

  CY  Casualties = TOTALYTD(SUM('Data'[Number_of_Casualties]),'Calendar'[Date])

  Screenshot of CY Casualties Formula,

  ![Image](https://github.com/user-attachments/assets/9114533b-2526-4f14-a5cf-9248062b4b9a)

  CY Accidents = TOTALYTD(COUNT('Data'[Accident_Index]),'Calendar'[Date])

  Screenshot of CY Accidents Formula,

  ![Image](https://github.com/user-attachments/assets/f321bd90-d3c8-4be9-8327-00aa0bf91621)

  CY Fatal casualties = CALCULATE('Data'[CY  Casualties],'Data'[Accident_Severity]= "Fatal")

  Screenshot of CY Fatal casualties Formula,

  ![Image](https://github.com/user-attachments/assets/8f546d83-e4c3-4cc9-abd9-f3a1a8721f2d)

  CY casualties Serious = CALCULATE('Data'[CY  Casualties],'Data'[Accident_Severity]= "Serious")

  Screenshot of CY Serious casualties Formula,

  ![Image](https://github.com/user-attachments/assets/98b6e42f-3f42-4ffa-b49f-bf8d858bc883)

  CY Slight casualties = CALCULATE('Data'[CY  Casualties],'Data'[Accident_Severity]= "Slight")

  Screenshot of CY Slight casualties Formula,

  ![Image](https://github.com/user-attachments/assets/b816eac2-27f0-4f83-bc63-3fa82e30c8b7)


- Steps 11 : In the report view 5 card visuals(kpis) were to the canvas to display total number of employees, attrition count, attrition rate, active count and average age respectively.

  Screenshot of KPIs was added,

  ![Image](https://github.com/user-attachments/assets/9d99747f-2b16-43cb-8c48-1ad4cf4b5f94)

  ![Image](https://github.com/user-attachments/assets/fcca0e79-f9bf-4a10-a41f-fc173f40e40e)

  ![Image](https://github.com/user-attachments/assets/8896dacd-db8e-4517-9c2f-ed98c2aef603)

  ![Image](https://github.com/user-attachments/assets/0aecc113-464f-4fba-ad7f-64e6b7f09d10)

  ![Image](https://github.com/user-attachments/assets/49fad2a3-faea-45ef-a872-e91feedebca4)

- Step 12 : In the report view Visual two filters(slicers) were added for 'road surface conditions' and 'weather conditions'.
  Screenshot of the slicers(filters) was added,

  ![Image](https://github.com/user-attachments/assets/eb70582a-efc3-4998-8dba-47f6fe0c5b48)

- Step 13 : A multi-row-card chart was used to represent current year casualties by vehicle type. 

  Screenshot of CY casualties by vehicles type

  ![Image](https://github.com/user-attachments/assets/a428a1e4-bf40-4717-bd58-2e117ad08840)

- Step 14 : Area chart was used to analyze number of CY casualties vs PY casualties by monthly trends,while creating this visual, field named date hierarchy was also added to the legend bucket, thus the number of years are also seggregated according to specific year using colour coding.

  Screenshot of CY casualties vs PY casualties by monthly trends,

  ![Image](https://github.com/user-attachments/assets/b9ddc509-1a3b-48bd-9a1e-c5ab62f17e71)

- Step 15 : A stacked bar chart was used to showcase CY casualties by vehicle type in the  report view area.

  Screenshot of CY casualties by road type.

  ![Image](https://github.com/user-attachments/assets/9d8452af-b5a2-49db-a388-a6ddbd43bcbc)

- Step 16 : A donut chart chart was used to highlight CY casualties by light conditions.

  Screenshot of CY casualties by light conditions.


  ![Image](https://github.com/user-attachments/assets/eb42c07e-ae96-4f29-a98a-b78b6ab90aef)

- Step 17 : A donut chart chart was used to highlight CY casualties by urban/rural areas.

  Screenshot of CY casualties by urban/rural areas.

  ![Image](https://github.com/user-attachments/assets/6b14d500-db4b-4cb9-9deb-30f7715196d5)

- Step 18 : A map chart chart was used to highlight CY casualties by urban/rural areas.

  Screenshot of  CY casualties by location.

  ![Image](https://github.com/user-attachments/assets/54b62473-6afd-465f-bcc9-03d04ab61205)

- Step 19 : The report was then published to Power BI Service.

  # Screenshot of Dashboard (Power BI Service)

  ![Image](https://github.com/user-attachments/assets/d1eb7e45-3594-4c93-991d-1e569a466125)

  #  Key Insights

Following inferences can be drawn from the dashboard;

### [1]  Overall Casualties Are Declining.
- Total CY Casualties is 195.7K, down by 11.9% from the previous year.

- This signals a positive trend in road safety and improved response measures, though further analysis would be needed to confirm the cause (e.g., policy changes, roadworks, awareness campaigns).
### [2] Fatal Casualties Saw the Sharpest Drop.
- CY Fatal Casualties is 2.9K, a significant 33.3% decrease.

- This suggests critical life saving interventions and improved emergency services may be working effectively.

### [3] . Slight Casualties Dominate.
- With 165.8K slight casualties (85%+ of all casualties), minor accidents are the most common.
- Indicates that while accident frequency remains high, most incidents aren't severe, hinting at either better vehicle safety features or lower-speed collisions.


### [4]  Cars Are Involved in the Most Casualties.

- Car related casualties are dominant at 155K+, far ahead of all other vehicle types.

- Targeting driver behavior campaigns or regulations specifically for car drivers could be impactful.

### [5]  Casualty Peaks Around Summer Months.

- Monthly trend chart shows increases from May to October, peaking in warmer months.

- May suggest seasonal driving behavior, possibly more leisure travel or risk driving patterns in better weather.

### [6] Most Accidents Happen in Daylight.

- 74% of casualties occur during daylight, contradicting the assumption that darkness causes more accidents.

- Points to high traffic volume times (commuting hours or daytime travel) as major contributors.

### [7]  Urban Areas Are More Affected.

- 62% of casualties occur in urban areas, aligning with denser traffic zones and pedestrian activity.

- Could justify urban planning improvements or increased enforcement in cities.

📁 Project Status

✅ Completed and ready for review.

## Presented by : Lawrence Sila













                    
 
