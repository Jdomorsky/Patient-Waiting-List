---
# Patient Waiting List Analysis
---
## Table of Contents
---

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning](#data-cleaning)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results](#results)
- [Recommendations](#recommendations)
- [Limitations](#limitations)
- [References](#references)

---
### Project Overview
---

This data analysis project delves into the inpatient and outpatient trends of a hospital from 2018 to 2020. By thoroughly examining patient data across dimensions such as age, gender, department, and time periods, we aim to uncover patterns that have influenced fluctuations in patient care. Our goal is to identify key periods of inpatient and outpatient activity, understand the driving factors, and provide data-driven recommendations that shed light on the dynamics of the healthcare market. Through this comprehensive analysis, we will gain a deeper understanding of the industry's evolution and the elements that have propelled it forward.

![Patient Dashboard Snapshot](https://github.com/user-attachments/assets/46014c2b-e702-4dfa-8606-9eff0c9ca6eb)

![Patient Dashboard 2 Snapshot](https://github.com/user-attachments/assets/9b57c0ce-2f04-49d1-9920-4b25cad9e609)



---
### Data Sources
---

The foundation of this analysis is the "IN_WL 2018," "IN_WL 2019," "IN_WL 2020," "IN_WL 2021," "OP_WL 2018," "OP_WL 2019," "OP_WL 2020," "OP_WL 2021" datasets, providing a comprehensive snapshot of inpatient and outpatient trends from 2018 to 2021. These datasets encompass detailed information on over 600,000 patients, making it a robust source for our analysis.
The dataset was sourced from [PivotalStats]( https://pivotalstats.com/wp-content/uploads/2024/09/Data-Mapping-Bg.zip), ensuring reliable and credible information. Before diving into the analysis, the dataset was meticulously cleaned and preprocessed to handle missing values, correct inconsistencies, and standardize data entries across different fields. This thorough preparation allows us to conduct an accurate and insightful exploration of the inpatient and outpatient trends over the specified period.

---
### Tools
---

- Power BI Power Query Editor – Data Cleaning.
    - [Patient Data]( https://pivotalstats.com/wp-content/uploads/2024/09/Data-Mapping-Bg.zip)
- Power BI – Creating Reports.
- Microsoft Powerpoint – Creating Background Template.
- Microsoft Word – Creating Project Outline.

---
### Data Cleaning
---

In the initial data preparation phase, I performed the following tasks:
1. Data Loading and Inspection.
2. Handling Missing Values.
3. Data Cleaning and Formatting.

---
### Exploratory Data Analysis
---

EDA involving exploring the patient data to answer key questions, such as:
- How many patients does the hospital process annually?
- What are the gender trends by department?
- When are the peak inflow patient times?
- Which department receives the most traffic?
- How do current trends compare to the trends of the previous years?


---
### Data Analysis
---

- Concatenated the inpatient and outpatient data.
- Mapped concatinated data table to Mapping_Specialty table.
- Created DAX Measures:
   - ```Average Waiting List = AVERAGE(All_Data[Total])```
    - ```[Median Waiting List = MEDIAN(All_Data[Total])]```
    - ```[Avg/Med Wait List = SWITCH(VALUES('Calculation Method'[Calc Method]),"Average",[Average Waiting List],"Median",[Median Waiting List])]```
   - ```[PY Latest Month Wait List = CALCULATE( SUM(All_Data[Total]), VALUE(All_Data[Archive_Date]) =EDATE(MAX(All_Data[Archive_Date]), -12)]```
    - ```[Latest Month Wait List = CALCULATE(SUM(All_Data[Total]), All_Data[Archive_Date] = MAX(All_Data[Archive_Date]))]```
 
- Created an interactive Dashboard; showcasing highly customizeable visuals and metrics.
- Creaded custom visual templates in Powerpoint.

---
### Results
---

The analysis results are summarized as follows:
1. The **16-64 age group** is the most common age group of patients. 
2. The patient waitlist has increased from the previous year.
3. The most common patient type is **outpatient**.
4. The department that has the most patient traffic is the **orthopedic** department.

---
### Recommendations
---

Based on the analysis, we recommend the following actions:
1. Expand Orthopedic Services to Meet High Demand
Since the orthopedic department has the most patient traffic, it's essential to invest in this area to improve patient care and reduce wait times. Consider hiring additional orthopedic surgeons and support staff to handle the influx of patients. Upgrading equipment and facilities can enhance service quality. Implementing specialized clinics for common orthopedic issues—like joint replacements or sports injuries—can streamline patient flow. By bolstering this department, the hospital can better serve the 16-64 age group, who may be more prone to orthopedic problems due to active lifestyles or workplace injuries.

2. Optimize Outpatient Care and Reduce Waitlists
With outpatients being the most common patient type and the waitlist increasing from the previous year, it's crucial to streamline outpatient services. Implementing efficient scheduling systems can minimize bottlenecks. Incorporate telemedicine options for consultations and follow-ups to alleviate in-person appointment demand. Reviewing and adjusting staffing levels during peak times can improve throughput. Additionally, analyzing appointment no-show rates and launching reminder systems can ensure maximum utilization of available slots, effectively reducing the waitlist.

3. Develop Targeted Health Programs for the 16-64 Age Group
Since the majority of patients are within the 16-64 age bracket, tailoring services to their specific health needs can enhance patient satisfaction and outcomes. Launch preventative care programs focusing on lifestyle-related conditions prevalent in this age group, such as cardiovascular health, diabetes management, and mental health services. Collaborate with local businesses and community organizations to promote workplace wellness programs. Educational workshops and health screenings can foster community engagement and position the hospital as a proactive leader in health promotion.
By addressing these areas, the hospital can improve patient care efficiency, reduce wait times, and cater more effectively to its largest patient demographic. These strategies not only enhance the patient experience but also position the hospital to adapt to evolving healthcare demands.

---
### Limitations
---

This analysis faced limitations that could affect result interpretation:

One significant limitation is the completeness and accuracy of the data. While the datasets encompass a substantial number of patients over several years, there may be gaps or inconsistencies within the data. Missing values, incomplete records, or discrepancies in data entry across different departments and years could affect the reliability of the analysis. For instance, if certain patient demographics were not consistently recorded, this could skew the trends observed.

Another limitation is the scope of the data timeframe. The analysis covers data from 2018 to 2021, which may not capture long-term trends or recent changes beyond this period. Notably, the impact of global events like the COVID-19 pandemic, which began in late 2019, could have significantly influenced patient behaviors and hospital operations. The pandemic’s effects might have introduced anomalies or trends that are not representative of typical patterns, potentially affecting the generalizability of the results.

The analysis might also be limited by a lack of external context. Factors such as policy changes, economic shifts, population demographics, or regional health crises are not accounted for in the dataset but can have substantial impacts on inpatient and outpatient numbers. Without incorporating these external variables, it may be challenging to fully explain the underlying reasons for observed increases or decreases in patient care.

Additionally, there is the potential for selection bias. Since the data is sourced from a single hospital, the findings may not be generalizable to other hospitals or regions. The hospital's specific characteristics, such as its size, specialties, community served, and resources, could influence patient trends uniquely. Therefore, conclusions drawn might reflect local factors rather than industry-wide dynamics.

Moreover, the analysis focuses on quantitative data and lacks qualitative insights. Patient experiences, satisfaction levels, and staff feedback are not included but could provide valuable context to the trends observed. For example, an increase in outpatient numbers might be better understood alongside patient satisfaction surveys indicating preference for outpatient services over inpatient stays.

Lastly, there may be limitations due to changes in data recording practices over the years. Updates to data management systems, adjustments in how departments classify patients, or shifts in reporting protocols could introduce inconsistencies. Such changes might affect the continuity of data and, consequently, the accuracy of trend analysis.


---
### References
---

1. [Youtube](https://www.youtube.com/watch?v=G8ikAJele_s&t=852s)
2. [PivotalStats]( https://pivotalstats.com/wp-content/uploads/2024/09/Data-Mapping-Bg.zip)
